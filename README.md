<div align="center">
  <img src="https://raw.githubusercontent.com/alexperezalvarez/porta/main/static/images/desarrollador.png" alt="Logo" width="80" style="border-radius: 16px;">

  # &lt;AP /&gt; — Portafolio Personal

  <p>
    <strong>Django · Tailwind CSS · Responsive · i18n</strong>
  </p>

  <p>
    <a href="#-características">Características</a> •
    <a href="#-tecnologías">Tecnologías</a> •
    <a href="#-instalación">Instalación</a> •
    <a href="#-uso">Uso</a> •
    <a href="#-despliegue">Despliegue</a> •
    <a href="#-licencia">Licencia</a>
  </p>

  <br>

  <img src="https://img.shields.io/badge/Django-6.0-092E20?style=for-the-badge&logo=django&logoColor=white" alt="Django">
  <img src="https://img.shields.io/badge/Tailwind_CSS-4.0-06B6D4?style=for-the-badge&logo=tailwind-css&logoColor=white" alt="Tailwind">
  <img src="https://img.shields.io/badge/i18n-Enabled-FF6F61?style=for-the-badge&logo=googletranslate&logoColor=white" alt="i18n">
  <img src="https://img.shields.io/badge/MIT-License-22C55E?style=for-the-badge" alt="MIT">

  <br><br>

  <img src="https://raw.githubusercontent.com/alexperezalvarez/porta/main/static/images/perfil.jpeg" alt="Preview" width="200" style="border-radius: 50%; border: 4px solid #3b82f6; box-shadow: 0 0 30px rgba(59,130,246,0.3);">

  <br><br>

  <p>
    Portafolio personal desarrollado con Django. Diseño moderno con tema oscuro, animación de partículas en canvas, soporte multiidioma (Español/Inglés) y completamente responsive.
  </p>

  <br>

  <p>
    <sub>Inspirado en <a href="https://yoyodr.dev/">yoyodr.dev</a> · Hecho con ❤️ y ☕</sub>
  </p>
</div>

---

## ✨ Características

- **🎨 Tema oscuro** con acentos azul/púrpura y efecto glass morphism
- **🌊 Animación de partículas** en canvas con conexiones entre puntos
- **🌍 Multiidioma** — Español 🇨🇴 / Inglés 🇬🇧 con cambio instantáneo
- **📱 Diseño responsive** — Navbar flotante con bordes ovalados
- **🏠 Secciones:** Hero, Tecnologías, Sobre mí, Proyectos, Contacto
- **📬 Formulario de contacto** con validación y CSRF protection
- **⚡ Optimizado** para rendimiento con Django 6.0

---

## 🛠️ Tecnologías

<div align="center">

| Backend | Frontend | Herramientas |
|---------|----------|--------------|
| Django 6.0 | Tailwind CSS 4 | Git |
| Python 3.14 | Canvas API | python-decouple |
| SQLite | HTML5 | polib (i18n) |

</div>

---

## 🚀 Instalación

### Requisitos

- Python 3.12+
- pip

### Pasos

```bash
# 1. Clonar el repositorio
git clone https://github.com/alexperezalvarez/porta.git
cd porta

# 2. Crear entorno virtual
python -m venv env

# 3. Activar entorno virtual
# Windows:
env\Scripts\activate
# Linux/Mac:
# source env/bin/activate

# 4. Instalar dependencias
pip install -r requirements.txt

# 5. Configurar variables de entorno
cp .env.example .env
# Editar .env con tus valores

# 6. Migraciones
python manage.py migrate

# 7. Iniciar servidor
python manage.py runserver
```

### Variables de Entorno (`.env`)

```env
SECRET_KEY=tu-clave-secreta-aqui
DEBUG=True
ALLOWED_HOSTS=127.0.0.1,localhost
```

---

## 📖 Uso

```bash
# Iniciar servidor de desarrollo
python manage.py runserver

# Crear traducciones (cuando tengas GNU gettext)
# python manage.py makemessages -l en
# python manage.py compilemessages
```

Abrir [http://127.0.0.1:8000](http://127.0.0.1:8000) en el navegador.

### Rutas

| Ruta | Descripción |
|------|-------------|
| `/` | Inicio — Hero, skills, sobre mí |
| `/projects/` | Proyectos — Grid con cards |
| `/contact/` | Contacto — Formulario + información |
| `/admin/` | Panel de administración Django |

---

## 🌐 Despliegue

### Render

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy)

```yaml
# render.yaml
services:
  - type: web
    name: porta
    runtime: python
    buildCommand: pip install -r requirements.txt && python manage.py collectstatic --noinput && python manage.py migrate
    startCommand: gunicorn portafolio.wsgi:application
    envVars:
      - key: SECRET_KEY
        generateValue: true
      - key: DEBUG
        value: "False"
```

### Railway / Fly.io

```dockerfile
FROM python:3.14-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
RUN python manage.py collectstatic --noinput
CMD ["gunicorn", "portafolio.wsgi:application"]
```

---

## 📁 Estructura del Proyecto

```
porta/
├── portafolio/                # Configuración Django
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── core/                      # App principal
│   ├── views.py
│   ├── urls.py
│   └── models.py
├── templates/
│   └── core/
│       ├── base.html          # Plantilla base
│       ├── home.html          # Página de inicio
│       ├── projects.html      # Proyectos
│       └── contact.html       # Contacto
├── static/
│   └── images/                # Imágenes del sitio
├── locale/
│   └── en/                    # Traducciones inglés
├── .env                       # Variables de entorno
├── .gitignore
├── manage.py
├── requirements.txt
└── LICENSE
```

---

## 🤝 Contribuir

Las contribuciones son bienvenidas. Por favor:

1. Hacé fork del proyecto
2. Creá tu rama (`git checkout -b feature/awesome`)
3. Comiteá tus cambios (`git commit -m 'feat: add awesome feature'`)
4. Pusheá a la rama (`git push origin feature/awesome`)
5. Abrí un Pull Request

---

## 📄 Licencia

Distribuido bajo la licencia MIT. Ver [`LICENSE`](LICENSE) para más información.

---

<div align="center">
  <sub>Built by <a href="https://github.com/alexperezalvarez">@alexperezalvarez</a></sub>
  <br>
  <sub>© 2026 Alexander Perez</sub>
</div>
