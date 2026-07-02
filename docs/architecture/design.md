# Diseño — appclima-python

> Decisiones de diseño técnico: cómo se resuelve el problema y cómo se comporta
> la aplicación CLI.
>
> **Última actualización**: 2026-07-02

## Contexto y objetivos

- **Problema**: enseñar los fundamentos de Python de forma progresiva mientras
  se construye una utilidad real que muestra el clima de una ciudad.
- **Objetivos**: que cada etapa introduzca un concepto (condicionales, bucles,
  funciones, listas, diccionarios, consumo de APIs y POO) de manera aislada y
  ejecutable.
- **No-objetivos**: no se busca un producto comercial, ni interfaz gráfica, ni
  servidor web, ni base de datos.

## Requisitos

### Funcionales

- Solicitar por consola el nombre de una ciudad.
- Obtener la temperatura actual (etapas 6 y 7, vía OpenWeatherMap).
- Mostrar una recomendación según el rango de temperatura.
- Permitir consultar varias ciudades en la misma sesión.
- Persistir las consultas en `data.csv` (etapas 6 y 7).

### No funcionales

- Simplicidad y legibilidad del código por encima del rendimiento.
- Ejecución local sin dependencias más allá de `requests`.

## Rangos de recomendación

La lógica central mapea la temperatura a un mensaje con emoji:

| Rango de temperatura | Clima     | Emoji | Recomendación                                   |
| -------------------- | --------- | ----- | ----------------------------------------------- |
| `>= 30 °C`           | Calor     | 🔥    | Aplicar protector solar y mantenerse hidratado. |
| `20 – 29 °C`         | Agradable | 😊    | Buen momento para salir y disfrutar del día.    |
| `< 20 °C`            | Frío      | ❄️    | Llevar abrigo para mantenerse cómodo.           |

## Decisiones de diseño CLI

- **Interacción por consola**: entrada con `input()`, salida con `print()`.
- **Bucle de sesión**: se pregunta "¿Desea consultar otra ciudad? (si/no)" para
  encadenar consultas sin reiniciar el programa.
- **Normalización de entrada**: se aplica `.strip()` y `.lower()` a las
  respuestas del usuario.
- **Progresión por etapas**: el mismo problema se re-resuelve en cada etapa con
  el nuevo concepto (funciones → listas → diccionarios → API → POO).

## Accesibilidad

- N/A — al ser una aplicación de línea de comandos sin interfaz gráfica ni web,
  no aplican criterios WCAG, contraste de color ni roles ARIA.

## Riesgos y mitigaciones

| Riesgo                                            | Impacto | Mitigación                                                         |
| ------------------------------------------------- | ------- | ----------------------------------------------------------------- |
| API KEY inválida o ausente en etapas 6 y 7        | Alto    | Documentar cómo obtener y configurar la clave (ver `api.md`).     |
| Ciudad inexistente o error de red sin manejar     | Medio   | Mejora prevista: manejo de errores y timeouts (ver `roadmap.md`). |

## Preguntas abiertas

- [ ] ¿Externalizar la API KEY a una variable de entorno en lugar de constante?
