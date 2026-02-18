# Monolog 📦

![Build Status](https://github.com/Seldaek/monolog/actions/workflows/continuous-integration.yml/badge.svg)
[![Packagist Version](https://img.shields.io/packagist/v/monolog/monolog.svg)](https://packagist.org/packages/monolog/monolog)
![License](https://img.shields.io/packagist/l/monolog/monolog.svg)

Una biblioteca de PHP para enviar registros a archivos, sockets, buzones, bases de datos y diversos servicios web.

## ¿Qué hace este proyecto?

Monolog implementa el estándar PSR‑3 de logging y proporciona una API sencilla para crear `Logger` con canales, handlers, formatters y procesadores. Permite redirigir eventos de registro a una gran variedad de destinos (ficheros, bases de datos, servicios en la nube, correo, Slack, etc.) con configuraciones flexibles.

## ¿Por qué es útil?

- Admite múltiples **niveles de log** (DEBUG, INFO, NOTICE, WARNING, ERROR, CRITICAL, ALERT, EMERGENCY).
- **Handlers** extensibles para muchos destinos (Stream, Syslog, Elasticsearch, Slack y cientos más).
- Soporta **formatters** y **processors** para personalizar la estructura y añadir metadatos.
- Es **PSR‑3 compatible**, por lo que funciona con librerías y frameworks compatibles (Symfony, Laravel, Zend, etc.).
- Amplio ecosistema y probado en producción.

## Cómo comenzar

*(Chiste rápido: ¿por qué el logger siempre llega puntual? Porque no quiere perder el registro.)*


1. **Instalar via Composer**

   ```bash
   composer require monolog/monolog
   ```

2. **Configurar un logger básico**

   ```php
   <?php
   use Monolog\Level;
   use Monolog\Logger;
   use Monolog\Handler\StreamHandler;

   $logger = new Logger('mi_aplicacion');
   $logger->pushHandler(new StreamHandler(__DIR__.'/app.log', Level::Info));

   $logger->info('¡Monolog está listo!');
   ```

3. **Agregar contexto o procesadores**

   ```php
   $logger->info('Usuario logueado', ['user' => $userId]);

   $logger->pushProcessor(function ($record) {
       $record->extra['ip'] = $_SERVER['REMOTE_ADDR'] ?? 'n/a';
       return $record;
   });
   ```

4. **Ver la documentación**

   - Carpeta `doc/` del repositorio
   - Documentación en línea en https://github.com/Seldaek/monolog
   - [Estructura de mensajes](doc/message-structure.md)
   - [Handlers / Formatters / Processors](doc/02-handlers-formatters-processors.md)

## Dónde obtener ayuda

- Reporta problemas o propon mejoras mediante los [issues](https://github.com/Seldaek/monolog/issues).
- Consulta los [templates de `.github/ISSUE_TEMPLATE`](.github/).
- Preguntas generales en StackOverflow con la etiqueta `monolog`.
- Revisa la documentación en `doc/` o el wiki del proyecto.
- El fichero `.github/SECURITY.md` describe cómo informar vulnerabilidades.

## Mantenimiento y contribuciones

Este proyecto es mantenido por la comunidad; la matrícula principal se puede encontrar en el archivo `composer.json` (autor: Jordi Boggiano) y en los [commits del repositorio]. Si deseas colaborar:

1. Fork del repositorio.
2. Crea un branch con tu mejora/bugfix.
3. Añade tests en `tests/`.
4. Sigue el estilo PHP CS Fixer / PSR-12.
5. Envía un pull request hacia `main`.

Consulta `CONTRIBUTING.md` o los archivos de `.github/` para más detalles. ¡Agradecemos cualquier contribución, incluso pull requests con chistes malos! 😄

> **🐶 Joke:** ¿Por qué el logger no puede mentir? Porque siempre registra la verdad.

---

# Monolog 📦

![Build Status](https://github.com/Seldaek/monolog/actions/workflows/continuous-integration.yml/badge.svg)
[![Packagist Version](https://img.shields.io/packagist/v/monolog/monolog.svg)](https://packagist.org/packages/monolog/monolog)
![License](https://img.shields.io/packagist/l/monolog/monolog.svg)

A PHP library to send your logs to files, sockets, inboxes, databases and various web services.

## What does this project do?

Monolog implements the PSR-3 logging standard and provides a simple API for creating `Logger` instances with channels, handlers, formatters and processors. It lets you route log events to a wide variety of destinations (files, databases, cloud services, email, Slack, etc.) with flexible configuration.

## Why is it useful?

- Supports multiple **log levels** (DEBUG, INFO, NOTICE, WARNING, ERROR, CRITICAL, ALERT, EMERGENCY).
- Extensible **handlers** for many targets (Stream, Syslog, Elasticsearch, Slack, and hundreds more).
- Supports **formatters** and **processors** to customize structure and add metadata.
- **PSR-3 compatible**, works with compatible libraries and frameworks (Symfony, Laravel, Zend, etc.).
- Large ecosystem and battle-tested in production.

## Getting started

*(Quick joke: why does the logger always show up on time? It doesn’t want to miss a log.)*


1. **Install with Composer**

   ```bash
   composer require monolog/monolog
   ```

2. **Configure a basic logger**

   ```php
   <?php
   use Monolog\Level;
   use Monolog\Logger;
   use Monolog\Handler\StreamHandler;

   $logger = new Logger('my_app');
   $logger->pushHandler(new StreamHandler(__DIR__.'/app.log', Level::Info));

   $logger->info('Monolog is ready!');
   ```

3. **Add context or processors**

   ```php
   $logger->info('User logged in', ['user' => $userId]);

   $logger->pushProcessor(function ($record) {
       $record->extra['ip'] = $_SERVER['REMOTE_ADDR'] ?? 'n/a';
       return $record;
   });
   ```

4. **Read the documentation**

   - `doc/` folder in this repository
   - Online docs at https://github.com/Seldaek/monolog
   - [Message structure](doc/message-structure.md)
   - [Handlers / Formatters / Processors](doc/02-handlers-formatters-processors.md)

## Where to get help

- File issues or feature requests via the [issues page](https://github.com/Seldaek/monolog/issues).
- See the templates in `.github/ISSUE_TEMPLATE`.
- General questions on StackOverflow with the `monolog` tag.
- Review docs in `doc/` or the project wiki.
- `.github/SECURITY.md` explains how to report vulnerabilities.

## Maintenance and contributions

This project is community‑maintained; core authors are listed in `composer.json` (author: Jordi Boggiano) and in the repository commits. To contribute:

1. Fork the repo.
2. Create a branch for your fix/feature.
3. Add tests under `tests/`.
4. Follow PSR-12 / PHP CS Fixer guidelines.
5. Open a pull request against `main`.

See `CONTRIBUTING.md` or files in `.github/` for details. We welcome any contribution, even pull requests with bad jokes! 😄

> **🐶 Joke:** Why did the logger break up with the variable? It couldn't handle the scope.
