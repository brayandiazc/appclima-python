# Convenciones

Esta carpeta documenta **cómo trabajamos** en appclima-python: reglas y
estándares transversales que aplican al día a día, independientes de cualquier
feature concreta.

> Diferencia con `docs/architecture/`: aquí van las **reglas** ("cómo testeamos");
> en `architecture/` va **este** proyecto en concreto ("cómo está estructurado
> por etapas").

## Convenciones incluidas

| Convención                               | Tema                               |
| ---------------------------------------- | ---------------------------------- |
| [quality-tooling.md](quality-tooling.md) | Linters, formato y git hooks       |
| [secrets.md](secrets.md)                 | Manejo de secretos y credenciales  |
| [testing.md](testing.md)                 | Estrategia y estándares de testing |

## Agregar una convención

Copia [`_template.md`](_template.md), renómbralo en `kebab-case` y documenta el
nuevo tema. Añádelo a la tabla de arriba.

## Convenciones adicionales opcionales

No se incluyen por defecto; créalas con `_template.md` si tu proyecto las necesita.

- **Genéricas / SaaS**: pagos, webhooks, multi-tenancy, PWA, administración,
  aceptación legal, observabilidad.
- **Móvil**: release a stores (versionado, firma/code-signing, capturas y ASO),
  permisos del dispositivo, notificaciones push, modo offline.
- **Escritorio**: empaquetado e instaladores por SO, code signing y notarización,
  auto-update, telemetría / reporte de crashes.

> Ver [`TEMPLATE-USAGE.md`](../../TEMPLATE-USAGE.md) § "Adaptar por tipo de proyecto"
> para qué borrar y qué reenfocar según sea web, móvil o escritorio.
