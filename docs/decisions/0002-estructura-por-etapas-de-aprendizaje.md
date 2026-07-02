# 0002. Organizar el código en etapas de aprendizaje

- **Estado**: Aceptada
- **Fecha**: 2026-07-02
- **Decisores**: Brayan Diaz C

## Contexto y problema

`appclima-python` es un proyecto **educativo**: su objetivo no es solo funcionar,
sino enseñar los fundamentos de Python de forma progresiva. Un único código final
optimizado ocultaría el proceso de aprendizaje y no dejaría ver cómo evoluciona una
solución desde lo más simple hasta la Programación Orientada a Objetos.

## Opciones consideradas

- **Un solo programa final** — el código más limpio, pero pierde el valor didáctico.
- **Ramas de git por etapa** — separa versiones, pero es incómodo de navegar y comparar.
- **Una carpeta por etapa** — cada concepto vive en `etapa-N/` y se compara lado a lado.

## Decisión

Organizamos el proyecto en **una carpeta por etapa** (`etapa-1/` … `etapa-7/`),
donde cada etapa introduce un concepto nuevo sobre el anterior: condicionales,
ciclos, funciones, listas, diccionarios, consumo de APIs y POO. Cada etapa se
ejecuta de forma independiente con `python etapa-N/main.py`.

## Consecuencias

**Positivas:**

- El progreso del código refleja el progreso del aprendizaje.
- Se pueden comparar dos etapas lado a lado para ver qué cambió.
- Cada etapa es ejecutable y autocontenida.

**Negativas / costos:**

- Hay código repetido entre etapas (esperado y deliberado con fines didácticos).

**Neutras / a vigilar:**

- Si el proyecto creciera más allá de lo educativo, convendría consolidar en un
  único paquete instalable.

## Referencias

- [`docs/architecture/architecture.md`](../architecture/architecture.md)
- [`docs/product/roadmap.md`](../product/roadmap.md)
