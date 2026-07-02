# Workflows de CI/CD

Esta carpeta contiene los workflows de [GitHub Actions](https://docs.github.com/actions)
del proyecto.

## Workflows incluidos

- [`ci.yml`](ci.yml) — se ejecuta en cada push y PR a `main`/`develop`:
  - **Lint y formato**: `ruff check .` y `black --check .`.
  - **Compilar**: verifica la sintaxis de las 7 etapas en Python 3.8–3.12
    (`python -m compileall`).

## Workflows recomendados a futuro

| Workflow                    | Propósito                                      |
| --------------------------- | ---------------------------------------------- |
| `labeler.yml`               | Auto-etiquetado de PRs (usa `../labeler.yml`). |
| `dependabot-auto-merge.yml` | Auto-merge de PRs de Dependabot (parches).     |

## Secrets

Define en **Settings → Secrets and variables → Actions** los secretos que
necesiten tus workflows (claves de deploy, tokens, etc.). Ver
[`../../docs/conventions/secrets.md`](../../docs/conventions/secrets.md).
