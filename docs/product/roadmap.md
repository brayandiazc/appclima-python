# Roadmap — appclima-python

> Estado y dirección del proyecto. Documento vivo.
> **Última actualización**: 2026-07-02

## Leyenda

- ✅ Hecho
- 🚧 En curso
- 📋 Planificado
- ⏸️ Diferido

## Visión

Ser un recurso educativo claro y completo para aprender los fundamentos de
Python, construyendo de forma incremental una aplicación de clima real, desde
los condicionales hasta la Programación Orientada a Objetos.

## Estado actual

Las 7 etapas de aprendizaje están completas y ejecutables con
`python etapa-N/main.py`. Corresponde a la versión **v1.0.0**.

## v1.0.0 — Las 7 etapas (completado)

- ✅ Etapa 1 — Control de flujo básico (condicionales).
- ✅ Etapa 2 — Ciclos e iteraciones (bucles).
- ✅ Etapa 3 — Creación y uso de funciones.
- ✅ Etapa 4 — Manejo de arreglos y persistencia de datos (listas).
- ✅ Etapa 5 — Uso de diccionarios.
- ✅ Etapa 6 — Consumo de APIs (OpenWeatherMap con `requests`).
- ✅ Etapa 7 — Programación Orientada a Objetos (clase `Clima`).

## Ideas futuras

### Robustez

- 📋 Manejo de errores y tiempos de espera (timeouts) en las llamadas a la API.
- 📋 Validar ciudad inexistente y respuestas no exitosas de OpenWeatherMap.
- 📋 Externalizar la API KEY a una variable de entorno.

### Calidad

- 📋 Suite de pruebas con `pytest`.

### Funcionalidad

- 📋 Soporte de más ciudades y de unidades configurables (Celsius/Fahrenheit).
- 📋 Empaquetado del proyecto (por ejemplo, `pip install` / ejecutable CLI).

## Fuera de alcance

- Interfaz gráfica o web, base de datos, autenticación de usuarios y despliegue
  en la nube: el proyecto es intencionalmente una CLI local y educativa.

## Cómo se actualiza este documento

- Revisar al cerrar cada versión/fase.
- Registrar las decisiones que cambian el rumbo como ADRs en
  [`../decisions/`](../decisions/README.md).
