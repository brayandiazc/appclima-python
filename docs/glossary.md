# Glosario

Vocabulario compartido del dominio y del proyecto. Mantén las definiciones cortas
y sin ambigüedad para que todo el equipo use los términos de la misma forma.

| Término                | Definición                                                                                                                    |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| API Key                | Credencial personal que autentica las peticiones a OpenWeatherMap. Se obtiene en http://api.openweathermap.org y no se versiona. |
| CLI                    | Interfaz de línea de comandos (Command Line Interface): la app se ejecuta y se interactúa desde la terminal, sin interfaz gráfica. |
| Clima                  | Estado atmosférico consultado para una ciudad. En la Etapa 7 se modela con la clase `Clima` (POO).                             |
| Etapa                  | Cada una de las 7 fases de aprendizaje del proyecto, en carpetas `etapa-N/`. Se ejecuta con `python etapa-N/main.py`.          |
| OpenWeatherMap         | Servicio (API) externo del que la app obtiene los datos de temperatura y clima de una ciudad (Etapas 6 y 7).                   |
| POO / Clase            | Programación Orientada a Objetos: paradigma usado en la Etapa 7 mediante la clase `Clima`, que agrupa datos y comportamiento.  |
| Recomendación          | Sugerencia que la app muestra al usuario según la temperatura o el clima de la ciudad consultada.                             |
| `requests`             | Librería de Python usada en las Etapas 6 y 7 para hacer las peticiones HTTP a OpenWeatherMap.                                  |
| Temperatura (°C)       | Valor numérico en grados Celsius que devuelve la API (parámetro `units=metric`) y sobre el que se basan las recomendaciones.   |

> Convención: ordena los términos alfabéticamente y enlaza al documento donde se
> detalla cada concepto cuando aplique.

> Última actualización: 2026-07-02
