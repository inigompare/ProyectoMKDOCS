# Conclusiones

Este proyecto ha sido un ejercicio práctico completo que abarca múltiples competencias del ciclo ASIR. Más allá de crear una simple web, he aprendido sobre la importancia de la **documentación técnica** y el paradigma de **Infrastructure as Code (IaC)**.

![Conclusiones](img/conclusiones.png)

---

## 📝 Reflexión sobre la Documentación

### ¿Por qué documentar es tan importante?

La documentación técnica no es un "extra", es una parte fundamental del trabajo de un administrador de sistemas. Los beneficios son claros:

!!! quote "La documentación es un regalo que te haces a ti mismo del futuro" - **Reproducibilidad**: Poder repetir un proceso meses después - **Colaboración**: Permitir que otros entiendan y mejoren tu trabajo - **Debugging**: Recordar qué hiciste y por qué lo hiciste - **Profesionalismo**: Demostrar un trabajo riguroso y ordenado

### Documentación como Código

Este proyecto ejemplifica el concepto de **"Docs as Code"**:

| Aspecto              | Tradicional     | Docs as Code               |
| -------------------- | --------------- | -------------------------- |
| Formato              | Word, PDF       | Markdown, reStructuredText |
| Control de versiones | Ninguno         | Git                        |
| Colaboración         | Enviar archivos | Pull Requests              |
| Publicación          | Manual          | CI/CD automático           |
| Hosting              | Servidor propio | GitHub Pages (gratis)      |

??? tip "Infrastructure as Code (IaC)"
El mismo principio se aplica a la infraestructura. En lugar de configurar servidores manualmente, se escriben archivos de configuración (Terraform, Ansible, Docker) que definen el estado deseado del sistema.

    Ventajas:

    - **Versionable**: Historial completo de cambios
    - **Replicable**: Misma configuración en cualquier entorno
    - **Automatizable**: Despliegue sin intervención manual
    - **Auditable**: Saber quién cambió qué y cuándo

---

## 🌐 GitHub Pages vs Hosting Tradicional

### Ventajas de GitHub Pages

| Característica    | GitHub Pages                    | Hosting Tradicional         |
| ----------------- | ------------------------------- | --------------------------- |
| **Coste**         | Gratuito                        | 5-20€/mes mínimo            |
| **SSL (HTTPS)**   | Incluido automáticamente        | Hay que configurarlo        |
| **CDN**           | Incluido (Fastly)               | Extra o manual              |
| **Mantenimiento** | Cero                            | Actualizaciones, backups... |
| **Despliegue**    | `git push` o `mkdocs gh-deploy` | FTP, SSH, panel de control  |
| **Escalabilidad** | Automática                      | Depende del plan            |

### Limitaciones de GitHub Pages

!!! warning "No todo es perfecto"
GitHub Pages tiene algunas limitaciones a tener en cuenta:

    - **Solo sitios estáticos**: No soporta PHP, Python backend, bases de datos...
    - **Límite de tamaño**: Máximo 1GB por repositorio
    - **Ancho de banda**: Límite de 100GB/mes (más que suficiente para documentación)
    - **Builds por hora**: Máximo 10 builds/hora
    - **Dominio personalizado**: Requiere configuración DNS adicional

### ¿Cuándo usar cada opción?

=== "Usar GitHub Pages"

    ✅ Documentación técnica

    ✅ Portfolios y CVs online

    ✅ Blogs estáticos (con Jekyll, Hugo, MkDocs)

    ✅ Proyectos open source

    ✅ Landing pages simples

=== "Usar Hosting Tradicional"

    ✅ Aplicaciones web dinámicas (tiendas, foros)

    ✅ Sitios con bases de datos

    ✅ Proyectos con requisitos específicos de servidor

    ✅ Cuando necesitas control total del servidor

    ✅ Para clientes que requieren SLAs específicos

---

## 🎓 Competencias Desarrolladas

Durante este proyecto he practicado las siguientes competencias del ciclo ASIR:

- [x] **CLI y PowerShell**: Navegación, instalación de paquetes, gestión de permisos
- [x] **Control de versiones**: Git (add, commit, push, branch)
- [x] **Lenguajes de marcado**: Markdown, YAML
- [x] **Resolución de problemas**: Debugging de errores, lectura de logs
- [x] **Cloud y hosting**: GitHub Pages, DNS conceptual
- [x] **Documentación técnica**: Redacción clara, estructura, formato profesional

---

## 📚 Bibliografía y Recursos

### Documentación Oficial

- **MkDocs**: [mkdocs.org](https://www.mkdocs.org/)
- **Material for MkDocs**: [squidfunk.github.io/mkdocs-material](https://squidfunk.github.io/mkdocs-material/)
- **GitHub Pages**: [pages.github.com](https://pages.github.com/)
- **Python**: [python.org](https://www.python.org/)
- **Git**: [git-scm.com/doc](https://git-scm.com/doc)

### Tutoriales Recomendados

??? info "Recursos Adicionales"
**Videos:**

    - [MkDocs Tutorial - TechWorld with Nana](https://www.youtube.com/watch?v=Q-YA_dA8C20)
    - [Git and GitHub for Beginners - freeCodeCamp](https://www.youtube.com/watch?v=RGOj5yH7evk)

    **Artículos:**

    - [Getting Started with MkDocs](https://realpython.com/python-project-documentation-with-mkdocs/)
    - [GitHub Pages Documentation](https://docs.github.com/en/pages)

    **Herramientas:**

    - [YAML Validator](https://www.yamllint.com/) - Para validar archivos YAML
    - [Markdown Preview](https://markdownlivepreview.com/) - Para previsualizar Markdown

---

## 🏁 Cierre

!!! success "Proyecto Completado"
Este sitio web es la prueba tangible de todo lo aprendido. Desde la instalación inicial de Python hasta el despliegue final en GitHub Pages, cada paso ha sido documentado para servir como referencia futura.

    El ciclo ASIR nos prepara para gestionar infraestructuras complejas, y proyectos como este demuestran que incluso las herramientas "simples" como un generador de sitios estáticos pueden enseñarnos mucho sobre buenas prácticas, resolución de problemas y profesionalismo.

---

<div style="text-align: center; margin-top: 2rem;">
    <p><strong>Proyecto realizado para la asignatura SRI</strong></p>
    <p>ASIR - ILERNA | 2026</p>
</div>
