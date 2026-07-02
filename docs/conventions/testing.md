# Convenciones de testing

> Cómo escribimos y ejecutamos tests en appclima-python.
> **Última actualización**: 2026-07-02

> **Nota**: hoy el proyecto **aún no tiene tests automatizados**; las etapas son
> ejercicios educativos que se verifican ejecutándolos a mano. Este documento
> describe la convención **a adoptar** cuando se agreguen tests.

## Stack

- **Framework de tests**: `pytest`.
- **Cobertura**: `pytest-cov`.
- **Tests de sistema/E2E**: no aplica (la app es una CLI simple; los flujos se
  cubren con tests de integración sobre las funciones y la clase `Clima`).

## Tipos de test

| Tipo          | Qué cubre                                       | Carpeta                |
| ------------- | ----------------------------------------------- | ---------------------- |
| Unitarios     | Funciones/clases aisladas (recomendaciones, `Clima`) | `tests/`          |
| Integración   | Consumo de OpenWeatherMap (con la red simulada) | `tests/integration/`   |

## Reglas

- Todo cambio funcional se acompaña de tests.
- Estructura **Arrange-Act-Assert** (AAA): preparar, ejecutar, verificar.
- Un test verifica **una** cosa; nombres descriptivos del comportamiento esperado.
- Los tests deben ser deterministas: la llamada a la API (`requests`) se simula
  (mock) para no depender de la red ni de la API Key real.
- Cobertura mínima esperada: 70%.

## Ejemplos

```python
def test_recomendacion_para_temperatura_alta():
    # Arrange
    temperatura = 32
    # Act
    resultado = obtener_recomendacion(temperatura)
    # Assert
    assert "calor" in resultado.lower()
```

## Comandos útiles

```bash
pytest                       # Ejecutar todos los tests
pytest --cov                 # Con reporte de cobertura
pytest -k nombre_del_test    # Ejecutar un test o subconjunto por nombre
```

## Referencias

- [Documentación de pytest](https://docs.pytest.org/).
- [Documentación de pytest-cov](https://pytest-cov.readthedocs.io/).
