# Changelog

Todos los cambios notables de este proyecto se documentan en este archivo.

El formato se basa en [Keep a Changelog](https://keepachangelog.com/es-ES/1.1.0/)
y este proyecto adhiere a [Semantic Versioning](https://semver.org/lang/es/).

## [Unreleased]

## [1.1.0] - 2026-07-02

### Added

- Estructura de documentación y gobernanza adoptada desde `project-starter-template-es`:
  `docs/`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `CHANGELOG.md`,
  `.env.example`, `.editorconfig` y plantillas de `.github/`.
- `requirements.txt` con las dependencias del proyecto (`requests`, `python-dotenv`).
- Workflow de CI (`.github/workflows/ci.yml`): lint con `ruff` y `black`, y verificación
  de sintaxis de las 7 etapas en Python 3.8–3.12.

### Changed

- La clave de OpenWeatherMap ahora se lee de la variable de entorno `API_KEY`
  (`os.getenv`), con carga opcional desde `.env`, en lugar de estar escrita en el
  código de las etapas 6 y 7.

### Security

- Se elimina la clave de API embebida en el código fuente; ahora se gestiona como
  secreto vía variable de entorno.

## [1.0.0] - 2026-07-02

### Added

- Aplicación del clima en Python organizada en 7 etapas de aprendizaje:
  - Etapa 1: control de flujo básico (condicionales).
  - Etapa 2: ciclos e iteraciones.
  - Etapa 3: creación y uso de funciones.
  - Etapa 4: manejo de arreglos y persistencia de datos.
  - Etapa 5: uso de diccionarios.
  - Etapa 6: consumo de la API de OpenWeatherMap con `requests`.
  - Etapa 7: refactorización a Programación Orientada a Objetos (clase `Clima`).
- Recomendaciones según la temperatura (calor, agradable, frío).
- Licencia MIT y documentación inicial (`README.md`).

<!--
Enlaces de comparación entre versiones:
[Unreleased]: https://github.com/brayandiazc/appclima-python/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/brayandiazc/appclima-python/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/brayandiazc/appclima-python/releases/tag/v1.0.0
-->
