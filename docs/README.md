# Documentación de appclima-python

Mapa de la documentación del proyecto. Empieza por aquí para saber qué documento
responde cada pregunta.

| Documento                                                      | Pregunta que responde                 | Cuándo leerlo                   |
| -------------------------------------------------------------- | ------------------------------------- | ------------------------------- |
| [`architecture/architecture.md`](architecture/architecture.md) | ¿Cómo está construido el sistema?     | Al entender el panorama general |
| [`architecture/stack.md`](architecture/stack.md)               | ¿Con qué tecnologías y versiones?     | Al configurar el entorno        |
| [`architecture/api.md`](architecture/api.md)                   | ¿Qué API externa consume?             | Al integrar OpenWeatherMap      |
| [`architecture/design.md`](architecture/design.md)             | ¿Cómo se ve y por qué?                | Al diseñar la experiencia CLI   |
| [`product/business-model.md`](product/business-model.md)       | ¿Por qué existe / cómo genera valor?  | Para entender el propósito      |
| [`product/roadmap.md`](product/roadmap.md)                     | ¿Hacia dónde va?                      | Para conocer prioridades        |
| [`decisions/`](decisions/README.md)                            | ¿Por qué tomamos cada decisión?       | Antes de re-debatir algo        |
| [`conventions/`](conventions/README.md)                        | ¿Cómo trabajamos en este repo?        | Antes de escribir código        |
| [`glossary.md`](glossary.md)                                   | ¿Qué significa cada término?          | Ante vocabulario desconocido    |

## Sobre la distinción `architecture/` vs `conventions/`

- **`architecture/`** describe **este** proyecto en concreto (su estructura por
  etapas, su stack, la API externa que consume).
- **`conventions/`** describe **reglas reusables** de cómo trabajamos
  (cómo testeamos, cómo gestionamos secretos, qué herramientas de calidad usamos)
  — transversales a cualquier etapa.

## Cómo mantener esta documentación

- Actualiza la línea **"Última actualización"** al editar un documento.
- Registra las decisiones relevantes como [ADRs](decisions/README.md).
- Mantén este índice al día si agregas o quitas documentos.

> Última actualización: 2026-07-02
