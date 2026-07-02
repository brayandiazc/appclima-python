# Convenciones de calidad y tooling

> Linters, formato, análisis estático y git hooks de appclima-python.
> **Última actualización**: 2026-07-02

## Stack

- **Linter**: `ruff` (o `flake8`).
- **Formateador**: `black`.
- **Ordenado de imports**: `isort`.
- **Auditoría de dependencias**: `pip-audit` (o `pip list --outdated`).
- **Orquestador de git hooks**: `pre-commit` (opcional).

## Git hooks

Estrategia sugerida: hooks baratos y rápidos en `pre-commit`, los más costosos en
`pre-push`. CI ejecuta todo de nuevo en el servidor.

### pre-commit (en cada commit)

- Linter sobre archivos cambiados.
- Formato automático.
- Verificación de trailing whitespace, fin de archivo, conflictos sin resolver.

### pre-push (al subir)

- Linter completo.
- Tests (o un subconjunto rápido).
- Auditoría de dependencias.

## Reglas

- El código debe pasar linter y formato antes del merge.
- Los checks de calidad son **bloqueantes** en CI.

## Comandos útiles

```bash
ruff check .            # Linter sobre todo el proyecto
black .                 # Formatear el código
isort .                 # Ordenar los imports
pip-audit               # Auditar vulnerabilidades en dependencias
pip list --outdated     # Ver dependencias desactualizadas
```

## Referencias

- [Documentación de black](https://black.readthedocs.io/).
- [Documentación de ruff](https://docs.astral.sh/ruff/).
- [Documentación de isort](https://pycqa.github.io/isort/).
- [Documentación de pip-audit](https://pypi.org/project/pip-audit/).
