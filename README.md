# Práctica: Creacion de pagina personal en Github Pages


## Objetivo
Crear una página web personal con MkDocs y publicarla en GitHub Pages.


## Requisitos
- Cuenta GitHub
- Python 3.7+
- Linux
- Git

## Paso 1: Crear Repositorio
### Si, teneis que crear un repos vosotros este repo solo tiene las instrucciones, pero no trabajareis sobre el
1. Crear repo público: `[tu-usuario].github.io`
2. Clonar localmente:
```bash
git clone https://github.com/[tu-usuario]/[tu-usuario].github.io.git
cd [tu-usuario].github.io
```

## Paso 2: Configurar Python
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate   # Windows
pip install mkdocs
pip freeze > requirements.txt
```

## Paso 3: Inicializar MkDocs
```bash
mkdocs new .
```

## Paso 4: Configurar mkdocs.yml
```yaml
site_name: Mi Página Personal
site_author: [Tu Nombre]
site_url: https://[tu-usuario].github.io

theme:
  name: readthedocs  # Prueba: material, mkdocs, readthedocs

nav:
  - Inicio: index.md
  - Sobre Mí: sobre-mi.md
  - Proyectos: proyectos.md
  - Contacto: contacto.md

repo_url: https://github.com/[tu-usuario]/[tu-usuario].github.io
```

## Paso 5: Crear Contenido

### docs/index.md
```markdown
# ¡Hola! Soy [Tu Nombre]

Estudiante de [Grado] especializado en [área].

## Sobre mí
Breve descripción personal...

## Proyectos destacados 
- Proyecto 1: [descripción]
- Proyecto 2: [descripción]

```

### docs/sobre-mi.md
```markdown
# Sobre Mí

## Educación 
- [GRADO] - [CENTRO] (2023-2025)
- [GRADO] - [CENTRO] (2021-2023)

## Habilidades
- Python
- Elastic
- Git

## Experiencia
[Describe tu experiencia]
```

### docs/proyectos.md
```markdown
# Proyectos

## [Nombre Proyecto 1]
- **Descripción**: [descripción breve]
- **Tecnologías**: Python, Git
- **Enlace**: [GitHub URL]

## [Nombre Proyecto 2]
- **Descripción**: [descripción breve]  
- **Tecnologías**: Grafana, Elastic
- **Enlace**: [GitHub URL]
```

### docs/contacto.md
```markdown
# Contacto

- **Email**: tu-email@ejemplo.com
- **GitHub**: https://github.com/tu-usuario
- **LinkedIn**: [tu perfil]
```

## Paso 6: Desplegar a GitHub Pages

```bash
# Subir código fuente
git add .
git commit -m "Página personal inicial"
git push origin main

# Desplegar a GitHub Pages
mkdocs gh-deploy
```

El comando `mkdocs gh-deploy` automáticamente:
- Construye el sitio (`mkdocs build`)
- Crea/actualiza rama `gh-pages`
- Sube el sitio construido a esa rama

### Configurar GitHub Pages
En GitHub → Settings → Pages → Source: Deploy from a branch → Branch: **gh-pages**

**Si falla**: Settings → Actions → General → Workflow permissions → "Read and write permissions"

### Para evaluar debereis abrir un pull request en esta rama.
1. Creareis una rama con vuestro nombre
2. añadireis un nombre.apellido.md donde dentro tendreis un link a vuestro page
3. El mensaje del merge sera tambien el link a vuestro page