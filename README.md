# Blog Django

Una aplicación de blog moderna y escalable construida con Django 5.1. Este proyecto proporciona un sistema completo de gestión de contenido de blog con capacidades de administración intuitivas y una interfaz amigable.

## 🚀 Características

- **Gestión de Posts**: Crear, editar, eliminar y visualizar publicaciones
- **Interfaz de Administración**: Panel administrativo completo con Django Admin
- **Diseño Responsivo**: Interfaz optimizada para dispositivos de escritorio y móvil
- **Autenticación**: Sistema de usuarios integrado
- **Base de Datos**: Soporte para SQLite, PostgreSQL y MySQL
- **Despliegue en Nube**: Configurado para PythonAnywhere

## 📋 Requisitos Previos

- Python 3.8+
- pip (gestor de paquetes de Python)
- Virtualenv (recomendado)

## 🔧 Instalación

### 1. Clonar el repositorio

```bash
git clone <tu-repositorio-url>
cd django
```

### 2. Crear y activar el entorno virtual

**En Windows:**

```bash
python -m venv myvenv
myvenv\Scripts\activate
```

**En macOS/Linux:**

```bash
python3 -m venv myvenv
source myvenv/bin/activate
```

### 3. Instalar dependencias

```bash
pip install -r requirements.txt
```

### 4. Aplicar migraciones

```bash
python manage.py migrate
```

### 5. Crear un superusuario (administrador)

```bash
python manage.py createsuperuser
```

Sigue las instrucciones para crear tu cuenta de administrador.

## 🚀 Ejecución

### Modo de Desarrollo Local

```bash
python manage.py runserver
```

La aplicación estará disponible en `http://127.0.0.1:8000/`

### Acceder al Panel de Administración

```
http://127.0.0.1:8000/admin/
```

## 📁 Estructura del Proyecto

```
django/
├── blog/                      # Aplicación principal del blog
│   ├── migrations/            # Migraciones de base de datos
│   ├── static/
│   │   └── css/
│   │       └── blog.css       # Estilos personalizados
│   ├── templates/
│   │   └── blog/
│   │       ├── base.html      # Template base
│   │       ├── post_list.html # Lista de posts
│   │       ├── post_detail.html # Detalle de post
│   │       └── post_edit.html # Edición de post
│   ├── models.py              # Modelos de datos
│   ├── views.py               # Vistas y lógica
│   ├── forms.py               # Formularios
│   ├── urls.py                # URLs de la app
│   └── admin.py               # Configuración de admin
├── mysite/                    # Configuración principal del proyecto
│   ├── settings.py            # Configuración de Django
│   ├── urls.py                # URLs principales
│   ├── wsgi.py                # Configuración WSGI
│   └── asgi.py                # Configuración ASGI
├── myvenv/                    # Entorno virtual (no versionar)
├── manage.py                  # Script de administración
├── db.sqlite3                 # Base de datos local
└── requirements.txt           # Dependencias del proyecto
```

## 🔐 Configuración de Base de Datos

### SQLite (Desarrollo Local)

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```

### PostgreSQL (Producción)

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_db_name',
        'USER': 'your_db_user',
        'PASSWORD': 'your_db_password',
        'HOST': 'your_host.postgres.pythonanywhere-services.com',
        'PORT': '5432',
    }
}
```

## 🌐 Despliegue en PythonAnywhere

### Paso 1: Subir el proyecto

```bash
git push origin main
```

### Paso 2: En PythonAnywhere

1. Abre una consola Bash
2. Clona tu repositorio
3. Instala dependencias en el entorno virtual de PythonAnywhere
4. Ejecuta migraciones: `python manage.py migrate`
5. Configura el Web App en "Web" → New Web App

### Paso 3: Configurar la base de datos en la nube

En `mysite/settings.py`, actualiza `DATABASES` con las credenciales de PythonAnywhere:

```bash
python manage.py migrate
python manage.py createsuperuser
```

## 📝 Uso

### Crear una publicación

1. Accede a `http://localhost:8000/admin/`
2. Inicia sesión con tu superusuario
3. Ve a "Posts" → "Add Post"
4. Completa el formulario y guarda

O desde la interfaz web:

1. Navega a `http://localhost:8000/post/new/`
2. Completa el formulario
3. Haz clic en "Guardar Post"

### Ver publicaciones

- Página principal: `http://localhost:8000/`
- Detalle de post: `http://localhost:8000/post/<id>/`

### Editar una publicación

1. Accede al detalle del post: `http://localhost:8000/post/<id>/`
2. Haz clic en el botón **" Editar"**
3. Modifica el contenido
4. Guarda los cambios

### Eliminar una publicación

1. Accede al detalle del post: `http://localhost:8000/post/<id>/`
2. Haz clic en el botón **" Eliminar"**
3. Confirma la eliminación en la página de confirmación
4. La publicación será eliminada permanentemente

## 🛠️ Desarrollar

### Crear una nueva migración

```bash
python manage.py makemigrations
python manage.py migrate
```

### Crear una nueva app

```bash
python manage.py startapp nombre_app
```

### Ejecutar pruebas

```bash
python manage.py test
```

## 📦 Dependencias Principales

- **Django 5.1.15**: Framework web
- **asgiref 3.11.1**: Soporte ASGI/WSGI
- **sqlparse 0.5.5**: Parser de SQL

Ver `requirements.txt` para la lista completa.

## 🤝 Contribución

Para contribuir al proyecto:

1. Fork el repositorio
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 👤 Autor

**Nikol Velasquez**

## 📞 Soporte

Para reportar problemas o sugerir mejoras, abre un issue en el repositorio.

---

**Última actualización**: Marzo 2026
