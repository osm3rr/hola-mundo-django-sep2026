<div align="center">

# Hola, Mundo!

**Un punto de partida pequeno y claro para construir con Django.**

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-5.2-0C4B33?style=for-the-badge&logo=django&logoColor=white)](https://www.djangoproject.com/)
[![Base de datos](https://img.shields.io/badge/SQLite-incluida-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://www.sqlite.org/)

</div>

---

## Sobre el proyecto

`hola-mundo` es una base minima de Django preparada para aprender, experimentar y crecer sin ruido. La aplicacion sirve una pagina de bienvenida en la ruta principal y deja lista la estructura esencial de un proyecto Django:

- configuracion del proyecto en `django_base/`;
- aplicacion funcional en `pages/`;
- plantilla HTML en `templates/`;
- persistencia local con SQLite;
- panel administrativo disponible en `/admin/`.

> **Estado actual:** proyecto inicial con una pagina `Hola, Mundo!`.

## Comenzar

### 1. Clonar y entrar al proyecto

```bash
git clone <URL_DEL_REPOSITORIO>
cd hola-mundo
```

### 2. Crear y activar el entorno virtual

**Windows PowerShell**

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

**macOS / Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Instalar dependencias

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Aplicar migraciones

```bash
python manage.py migrate
```

### 5. Iniciar el servidor

```bash
python manage.py runserver
```

Abre [http://127.0.0.1:8000/](http://127.0.0.1:8000/) en el navegador.

## Rutas disponibles

| Ruta | Uso |
| --- | --- |
| `/` | Pagina principal de bienvenida |
| `/admin/` | Panel de administracion de Django |

Para crear un usuario administrador:

```bash
python manage.py createsuperuser
```

## Estructura

```text
hola-mundo/
├── django_base/          # Configuracion, URLs y entrada WSGI/ASGI
├── pages/                # Aplicacion principal
│   ├── migrations/       # Migraciones de la aplicacion
│   ├── urls.py           # Rutas de pages
│   └── views.py          # Vista de la pagina principal
├── templates/
│   └── home.html         # Plantilla de bienvenida
├── db.sqlite3            # Base de datos local
├── manage.py             # Utilidad de administracion de Django
├── requirements.txt      # Dependencias del proyecto
└── readme.md             # Documentacion
```

## Flujo de desarrollo

Los comandos mas utiles durante el desarrollo son:

```bash
python manage.py check
python manage.py test
python manage.py makemigrations
python manage.py migrate
```

Cuando agregues una nueva pagina, una ruta tipica consiste en:

1. crear o modificar la vista en `pages/views.py`;
2. registrar la ruta en `pages/urls.py`;
3. crear la plantilla correspondiente dentro de `templates/`;
4. verificar el resultado con `python manage.py check`.

## Configuracion para produccion

Este repositorio esta orientado al desarrollo local. Antes de desplegarlo:

- mueve `SECRET_KEY` a una variable de entorno;
- cambia `DEBUG` a `False`;
- define `ALLOWED_HOSTS`;
- configura una base de datos y archivos estaticos para produccion;
- revisa la lista de comprobacion de despliegue de Django.

Consulta la documentacion oficial: [Django deployment checklist](https://docs.djangoproject.com/en/5.2/howto/deployment/checklist/).

## Licencia

Este proyecto no declara una licencia especifica todavia.
