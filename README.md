# Paquete personal para creación de notas

## Objetivo

- Paquete personalizado para facilitar la creación y homogenización de notas en LaTeX.
- Contener los paquetes requeridos.
- Contener las definiciones de comandos y entornos personalizados.
- Incluye archivo .cwl (_completion word list_) para autocompletado en TexStudio

## Características

- Prefijos: Convención de prefijos para todos los entornos y comandos definidos en el paquete.
  - Alias de prefijos para comandos muy utilizados.
  - Warning que indica si hay prefijos repetidos.
- Módulos: Contiene varios módulos, que agrupan los comandos y entornos por área de aplicación.
  - El paquete principal funciona como dispatcher.
  - Evita la carga de paquetes innecesarios.
  - Estructura:
    - notes-kit.sty Paquete principal, carga módulos.
    - notes-kit-sections.sty Secciones (objetivos, conclusiones, citas, resumen)
    - notes-kit-code.sty Resaltado de código, estilos para lenguajes, etc.
    - notes-kit-base.sty Código compartido entre módulos (helpers internos, configuraciones de colores común, prefijo).
- Configuración: Contiene un archivo de configuración de ejemplo, el cual debe de estar en la raíz del proyecto de las notas.
  - Consta de una lista de claves-valor que se puede modificar para personalizar valores del paquete como colores, metadatos, etc.

## Utilidades

### Preparar repositorio de documento LaTeX para utilizar paquete.

1. Cargar paquete

```
\makeatletter\usepackage[...]
\def\input@path{{rsc/pckg/template-package/}}
\makeatother
\usepackage{noteskit}
```

2. Agregar submódulo a repositorio de notas con la rama main por defecto

```
git submodule add -b main git@github.com:MauOcon/latex-notes-kit.git rsc/pckg/template-package
```

3. Para actualizar el paquete a su última versión de la rama indicada en el comando anterior. También es necesario hacer commit para registrar la nueva versión del paquete que se está utilizando, y se puede hacer rollback si se rompe algo
```
git submodule update --remote
git add rsc/pckg/template-package/   
git commit -m "Actualizar paquete a v1.3.0"
```

### Agregar archivo de autocompletado a TexStudio

  a. Copiar archivo .cwl a .config/texstudio/completion/user/
  b. Habilitar en Options -> Configure Texstudio... -> Completion
  c. Reiniciar TexStudio

### Configurar

### Agregar nuevo módulo

### Agregar prefijo


## Estructura de carpetas

A continuación se muestra la estructura de carpetas sugerida para el uso de este paquete.

