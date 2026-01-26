# Preparación del Entorno

Antes de poder crear nuestro sitio MkDocs, necesitamos preparar el entorno de desarrollo. Esta sección cubre la instalación de todas las herramientas necesarias en un sistema **Windows**.

![Preparación del entorno](img/preparacion.png)

## 📋 Requisitos Previos

Para seguir esta guía necesitarás:

- Sistema operativo **Windows 10/11**
- Conexión a Internet
- Permisos de administrador en el equipo

---

## 1️⃣ Instalación de Python

Python es el lenguaje de programación sobre el que funciona MkDocs.

### Descarga

1. Accede a la web oficial: [python.org/downloads](https://www.python.org/downloads/)
2. Descarga la última versión estable (3.12 o superior)

### Instalación

!!! warning "Paso Crítico"
Durante la instalación, **marca la casilla** `Add Python to PATH`. Si olvidas esto, los comandos de Python no funcionarán desde la terminal.

![Instalación de Python](img/python-install.png)

### Verificación

Abre **PowerShell** y ejecuta:

```powershell
python --version
```

Deberías ver algo como:

```
Python 3.12.1
```

??? question "¿No funciona el comando?"
    Si ves un error como `python: command not found`, significa que Python no está en el PATH. Puedes:

    1. Reinstalar Python marcando la casilla "Add to PATH"
    2. O añadir Python manualmente a las variables de entorno del sistema

---

## 2️⃣ Instalación de Git

Git es imprescindible para el control de versiones y para el despliegue en GitHub Pages.

### Descarga

1. Accede a: [git-scm.com/download/win](https://git-scm.com/download/win)
2. Descarga el instalador de 64-bit

### Instalación

=== "Opciones Recomendadas"

    Durante el asistente de instalación, selecciona:

    - **Default editor**: Visual Studio Code
    - **PATH environment**: Git from the command line and also from 3rd-party software
    - **HTTPS transport backend**: Use the OpenSSL library
    - **Line ending conversions**: Checkout Windows-style, commit Unix-style

=== "Instalación Rápida"

    Si prefieres una instalación rápida, simplemente haz clic en "Next" en todas las opciones, los valores por defecto son adecuados.

### Verificación

```powershell
git --version
```

Resultado esperado:

```
git version 2.43.0.windows.1
```

### Configuración Inicial de Git

Configura tu identidad (necesario para los commits):

```powershell
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@ejemplo.com"
```

---

## 3️⃣ Instalación de MkDocs y Material

Ahora instalamos MkDocs junto con el tema Material, que incluye todas las funcionalidades avanzadas que usaremos.

### Comando de Instalación

```powershell
pip install mkdocs-material
```

!!! success "¿Por qué `mkdocs-material` y no solo `mkdocs`?"
El paquete `mkdocs-material` incluye automáticamente MkDocs como dependencia, más el tema Material con todas sus extensiones. Es la forma más eficiente de instalarlo todo.

### Verificación de la Instalación

```powershell
mkdocs --version
```

Resultado esperado:

```
mkdocs, version 1.6.0 from C:\Users\...\site-packages\mkdocs (Python 3.12)
```

---

## 4️⃣ Preparación del Repositorio en GitHub

### Crear el Repositorio

1. Accede a [github.com](https://github.com) e inicia sesión
2. Haz clic en **New repository** (Nuevo repositorio)
3. Configura:
   - **Repository name**: `Proyecto-MKDOCS`
   - **Description**: `Documentación técnica con MkDocs`
   - **Visibility**: Public (necesario para GitHub Pages gratuito)
   - **Initialize with**: No marques ninguna opción

![Crear repositorio en GitHub](img/github-new-repo.png)

### Clonar el Repositorio

```powershell
cd C:\Users\TuUsuario\Desktop\ASIR
git clone https://github.com/tu-usuario/Proyecto-MKDOCS.git
cd Proyecto-MKDOCS
```

---

## ✅ Resumen de Verificación

Antes de continuar, asegúrate de que todos los comandos funcionan:

```powershell
# Verificar Python
python --version

# Verificar pip
pip --version

# Verificar Git
git --version

# Verificar MkDocs
mkdocs --version
```

!!! success "¡Entorno Listo!"
Si todos los comandos devuelven su versión correctamente, tu entorno está preparado para crear el proyecto MkDocs.

[Continuar con la Configuración :material-arrow-right:](estructura.md){ .md-button .md-button--primary }
