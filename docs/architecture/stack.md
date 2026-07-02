# Stack Tecnológico

> Fuente de verdad de las tecnologías y versiones del proyecto.
> `appclima-python` es una aplicación CLI educativa: su stack es
> deliberadamente mínimo.
>
> **Última actualización**: 2026-07-02

## Núcleo

| Categoría            | Tecnología      | Versión | Por qué                                                              |
| -------------------- | --------------- | ------- | ------------------------------------------------------------------- |
| Lenguaje / Runtime   | Python          | >= 3.8  | Lenguaje del proyecto; se usa por su claridad para enseñar.         |
| Gestor de paquetes   | pip             | —       | Instalación de la única dependencia externa (`requests`).           |
| Cliente HTTP         | `requests`      | >= 2.x  | Consumir la API de OpenWeatherMap de forma sencilla (etapas 6 y 7). |

> **Librería estándar utilizada**: `csv` y `datetime` para la persistencia de
> consultas en `data.csv` (etapas 6 y 7).

## Componentes que No aplican

Por ser un proyecto CLI local y educativo, las siguientes capas **No aplican**:

- **Frontend / UI gráfica**: No aplica (proyecto CLI educativo).
- **Framework backend / servidor web**: No aplica (proyecto CLI educativo).
- **ORM / Base de datos / Cache / Cola**: No aplica; la persistencia se hace en
  un archivo CSV local (`data.csv`).
- **CI/CD, contenedores, orquestación, monitoreo**: No aplica (proyecto CLI educativo).

## Servicios externos

| Servicio           | Uso                                                           | Credenciales necesarias                                      |
| ------------------ | ------------------------------------------------------------ | ----------------------------------------------------------- |
| OpenWeatherMap API | Obtener la temperatura actual de una ciudad (etapas 6 y 7).   | API KEY gratuita obtenida en `http://api.openweathermap.org`. |

## Justificación de elecciones

| Tecnología elegida | Alternativa descartada    | Razón                                                                    |
| ------------------ | ------------------------- | ------------------------------------------------------------------------ |
| `requests`         | `http.client` / `urllib`  | API más simple y legible, ideal para enseñar consumo de APIs.            |
| Archivo CSV        | Base de datos (SQLite…)   | Persistencia mínima y transparente; no requiere infraestructura extra.   |

## Versiones mínimas soportadas

- Python >= 3.8
- `requests` >= 2.x
