# Configuración del Proyecto

Una vez instaladas las herramientas, es hora de crear y configurar nuestro proyecto MkDocs. En esta sección aprenderás la estructura de archivos y cómo funciona el archivo de configuración principal.

![Estructura del proyecto](img/estructura.png)

---

## 1️⃣ Crear el Proyecto Base

### Inicializar MkDocs

Navega a tu carpeta del proyecto y ejecuta el comando de inicialización:

```powershell
cd C:\Users\TuUsuario\Desktop\ASIR\Proyecto-MKDOCS
mkdocs new .
```

!!! info "¿Qué hace `mkdocs new .`?"
Este comando crea la estructura básica del proyecto en el directorio actual (`.`):

    - `mkdocs.yml` - Archivo de configuración principal
    - `docs/` - Carpeta para los archivos Markdown
    - `docs/index.md` - Página de inicio por defecto

### Estructura Generada

```
Proyecto-MKDOCS/
├── docs/
│   └── index.md
└── mkdocs.yml
```

---

## 2️⃣ El Archivo mkdocs.yml

El archivo `mkdocs.yml` es el **corazón** del proyecto. Aquí se configura todo: el tema, las extensiones, la navegación y los metadatos del sitio.

### Anatomía del Archivo

```yaml title="mkdocs.yml"
# ============================================
# METADATOS DEL SITIO
# ============================================
site_name: Meta-Documentación MkDocs
site_description: Guía paso a paso para desplegar MkDocs
site_author: Estudiante ASIR

# ============================================
# TEMA Y APARIENCIA
# ============================================
theme:
  name: material
  language: es
  palette:
    primary: indigo
    accent: indigo

# ============================================
# EXTENSIONES DE MARKDOWN
# ============================================
markdown_extensions:
  - admonition
  - pymdownx.details
  - pymdownx.superfences
  - pymdownx.tabbed:
      alternate_style: true
  - pymdownx.highlight:
      anchor_linenums: true

# ============================================
# NAVEGACIÓN
# ============================================
nav:
  - Inicio: index.md
  - Preparación: prerrequisitos.md
  - Configuración: estructura.md
  - Errores: problemas.md
  - Conclusiones: conclusiones.md
```

!!! warning "Sintaxis YAML: ¡Cuidado con la Indentación!"
YAML es muy sensible a los espacios. Debes usar **espacios, nunca tabuladores**, y mantener una indentación consistente (normalmente 2 espacios).

    ```yaml
    # ✅ Correcto
    theme:
      name: material
      palette:
        primary: indigo

    # ❌ Incorrecto (tabuladores o indentación incorrecta)
    theme:
    	name: material
       palette:
        primary: indigo
    ```

---

## 3️⃣ Extensiones Explicadas

### Admonitions (Alertas)

Las admonitions son cajas de colores para resaltar información importante:

=== "Código"

    ```markdown
    !!! note "Título de la Nota"
        Contenido de la nota.

    !!! warning "Advertencia"
        Esto es importante.

    !!! success "Éxito"
        ¡Todo ha ido bien!

    !!! failure "Error"
        Algo ha fallado.
    ```

=== "Resultado"

    !!! note "Título de la Nota"
        Contenido de la nota.

    !!! warning "Advertencia"
        Esto es importante.

    !!! success "Éxito"
        ¡Todo ha ido bien!

    !!! failure "Error"
        Algo ha fallado.

### Bloques Desplegables

Útiles para información adicional que no todo el mundo necesita ver:

=== "Código"

    ```markdown
    ??? tip "Haz clic para expandir"
        Este contenido está oculto por defecto.

    ???+ note "Expandido por defecto"
        Este bloque comienza abierto.
    ```

=== "Resultado"

    ??? tip "Haz clic para expandir"
        Este contenido está oculto por defecto.

    ???+ note "Expandido por defecto"
        Este bloque comienza abierto.

### Pestañas

Perfectas para mostrar alternativas o diferentes sistemas operativos:

=== "Código"

    ```markdown
    === "Windows"
        ```powershell
        pip install mkdocs-material
        ```

    === "Linux/Mac"
        ```bash
        pip3 install mkdocs-material
        ```
    ```

=== "Resultado"

    === "Windows"
        ```powershell
        pip install mkdocs-material
        ```

    === "Linux/Mac"
        ```bash
        pip3 install mkdocs-material
        ```

---

## 4️⃣ Previsualizar el Sitio

MkDocs incluye un servidor de desarrollo que permite ver los cambios en tiempo real.

### Iniciar el Servidor

```powershell
mkdocs serve
```

### Salida Esperada

```
INFO    -  Building documentation...
INFO    -  Cleaning site directory
INFO    -  Documentation built in 0.50 seconds
INFO    -  [12:30:45] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO    -  [12:30:45] Serving on http://127.0.0.1:8000/
```

!!! success "¡Servidor Activo!"
Abre tu navegador y navega a **http://127.0.0.1:8000** para ver tu sitio. Cualquier cambio que hagas en los archivos se reflejará automáticamente.

### Detener el Servidor

Pulsa `Ctrl + C` en la terminal para detener el servidor.

---

## 5️⃣ Añadir Nuevas Páginas

Para crear una nueva página:

1. Crea un archivo `.md` en la carpeta `docs/`
2. Añade la entrada en la sección `nav` de `mkdocs.yml`

### Ejemplo

```powershell
# Crear el archivo
New-Item -Path .\docs\nueva-pagina.md -ItemType File
```

```yaml title="mkdocs.yml"
nav:
  - Inicio: index.md
  - Nueva Página: nueva-pagina.md
```

---

## ✅ Verificación

Para comprobar que todo está configurado correctamente:

```powershell
# Validar la configuración
mkdocs build --strict
```

!!! success "Build Exitoso"
Si el comando termina sin errores, tu configuración es correcta y el sitio está listo para ser desplegado.

[Ver los Problemas Encontrados :material-arrow-right:](problemas.md){ .md-button .md-button--primary }
