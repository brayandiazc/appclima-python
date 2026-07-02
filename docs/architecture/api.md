# API externa consumida — OpenWeatherMap

> **Importante**: `appclima-python` **no expone** una API propia. Es una
> aplicación CLI que **consume** la API pública de OpenWeatherMap para obtener
> la temperatura de una ciudad (etapas 6 y 7).
>
> Documentación oficial: <https://openweathermap.org/current>
>
> **Última actualización**: 2026-07-02

## Endpoint utilizado

```http
GET http://api.openweathermap.org/data/2.5/weather?q={ciudad}&appid={API_KEY}&units=metric
```

- **URL base**: `http://api.openweathermap.org/data/2.5/weather`
- **Método**: `GET`
- **Formato de respuesta**: JSON

## Parámetros

| Parámetro | Obligatorio | Descripción                                                       |
| --------- | ----------- | ----------------------------------------------------------------- |
| `q`       | Sí          | Nombre de la ciudad a consultar (p. ej. `Santiago`).              |
| `appid`   | Sí          | API KEY de OpenWeatherMap.                                        |
| `units`   | No          | Sistema de unidades. Se usa `metric` para obtener grados Celsius. |

## Autenticación

- Esquema: **API key** vía query string (`appid`).
- La clave se obtiene de forma gratuita registrándose en
  `http://api.openweathermap.org`.
- En el código actual la clave se define como una constante local
  (`api_key = "OPENWEATHER_API_KEY"`) dentro de `funciones_clima.py` y de la
  clase `Clima`; debe reemplazarse por una clave real antes de ejecutar las
  etapas 6 y 7.

## Respuesta relevante

La aplicación solo utiliza la temperatura actual, ubicada en el campo
`main.temp` del JSON de respuesta:

```python
response = requests.get(url)
data = response.json()
temperatura = data["main"]["temp"]  # temperatura en °C (units=metric)
```

Ejemplo simplificado de la respuesta de OpenWeatherMap:

```json
{
  "main": {
    "temp": 18.3,
    "feels_like": 17.9,
    "humidity": 72
  },
  "name": "Santiago",
  "cod": 200
}
```

## Manejo de errores

La API responde con el campo `cod` y códigos HTTP estándar. Casos habituales a
considerar al consumir el endpoint:

| Código | Significado           | Causa típica                                   |
| ------ | --------------------- | ---------------------------------------------- |
| 200    | Éxito                 | Ciudad encontrada; `main.temp` disponible.     |
| 401    | No autenticado        | API KEY ausente o inválida.                    |
| 404    | Ciudad no encontrada  | Nombre de ciudad mal escrito o inexistente.    |
| 429    | Límite de tasa        | Se superó el cupo del plan gratuito.           |

> **Nota**: la implementación educativa actual asume la ruta feliz
> (`data["main"]["temp"]`). Reforzar el manejo de errores y de tiempos de espera
> es una mejora prevista en el [`roadmap`](../product/roadmap.md).
