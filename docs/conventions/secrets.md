# Convenciones de secretos y credenciales

> Cómo gestionamos secretos en appclima-python.
> **Última actualización**: 2026-07-02

## Filosofía

- Los secretos **nunca** se commitean en texto plano.
- Separación clara entre **configuración** (no sensible) y **secretos** (sensible).

## Dónde vive cada cosa

| Tipo                         | Dónde                                              |
| ---------------------------- | -------------------------------------------------- |
| API Key de OpenWeatherMap    | Variable de entorno / archivo `.env` local (ignorado por git) |
| Variables de infraestructura | Variables de entorno del entorno                   |
| Secretos de CI/CD            | Secrets del proveedor (p. ej. GitHub Actions)      |

> **Caso de este proyecto**: la única credencial es la **API Key de
> OpenWeatherMap** (necesaria en las Etapas 6 y 7). El código la lee de la variable
> de entorno `API_KEY` con `os.getenv("API_KEY")` en `etapa-6/funciones_clima.py`
> y `etapa-7/clima.py`; si `python-dotenv` está instalado, también se carga
> automáticamente desde un archivo `.env` local (ignorado por git). Si la variable
> no está definida, el programa falla con un mensaje claro en lugar de continuar.

## Reglas

- El archivo `.env` está en `.gitignore`; solo se versiona `.env.example` (sin valores).
- Comparte secretos con nuevos colaboradores **fuera de banda** (nunca por git, email plano ni chat público).
- Rota credenciales periódicamente (sugerido cada 90 días) y de inmediato ante sospecha de fuga.
- Si un secreto se commitea por error: **rota el secreto primero**, luego limpia la historia.

## Ejemplos

```bash
# Copiar la plantilla de variables
cp .env.example .env
# Completar valores reales (que nunca se suben)
```

## Comandos útiles

```bash
# Definir la API Key como variable de entorno (sesión actual)
export API_KEY="tu_api_key_de_openweathermap"

# O guardarla en un archivo .env local (ignorado por git)
echo 'API_KEY=tu_api_key_de_openweathermap' >> .env

# Leerla desde Python
python -c "import os; print(os.getenv('API_KEY'))"
```

## Referencias

- [SECURITY.md](../../SECURITY.md) — política de seguridad.
- [OpenWeatherMap — API Keys](https://openweathermap.org/api).
