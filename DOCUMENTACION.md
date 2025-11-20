# Documentación del Proyecto: Portafolio Profesional de David Torres

## 1. Introducción

Este documento detalla el desarrollo y la estructura del sitio web de portafolio profesional de David Santiago Torres Fonseca. El objetivo del proyecto es presentar de manera clara y profesional su perfil, experiencia, proyectos y habilidades en las áreas de Soporte IT y Bases de Datos.

El sitio web es estático, desarrollado con HTML5 y CSS3, lo que garantiza un rendimiento rápido y un mantenimiento sencillo.

## 2. Estructura del Proyecto

El proyecto está organizado en carpetas para separar los diferentes tipos de archivos, siguiendo buenas prácticas de desarrollo web.

```
/
├── Estilos/
│   └── style.css       # Hoja de estilos principal
├── img/
│   └── perfil.jpg      # Imagen de perfil
├── Main/
│   ├── inicio.html     # Página principal
│   ├── acerca-de.html  # Página sobre el perfil profesional
│   ├── proyectos.html  # Página de proyectos destacados
│   ├── blog.html       # Página con artículos de blog
│   └── contacto.html   # Página de contacto
└── DOCUMENTACION.md    # Este archivo
```

- **`Estilos/`**: Contiene todos los archivos de estilo CSS. `style.css` define la apariencia visual de todo el sitio.
- **`img/`**: Almacena todos los recursos gráficos, como la foto de perfil.
- **`Main/`**: Contiene todos los archivos HTML que conforman las distintas páginas del sitio web.

## 3. Tecnologías Utilizadas

- **HTML5**: Para la estructura y el contenido semántico de las páginas web.
- **CSS3**: Para el diseño, la maquetación y la apariencia visual del sitio. Se utiliza un enfoque de diseño responsivo para asegurar que el sitio se vea bien en diferentes dispositivos (escritorio, tabletas y móviles).
- **Formspree**: Un servicio de terceros utilizado para procesar el formulario de contacto y enviar los datos al correo electrónico del propietario sin necesidad de un backend propio.

## 4. Análisis de las Páginas y Componentes

A continuación, se describen los componentes clave que se repiten a lo largo del sitio y la estructura específica de cada página.

### 4.1. Encabezado y Navegación (`<header>`)

Todas las páginas comparten un encabezado común que facilita la navegación y presenta la identidad de la marca.

**Código de ejemplo (`inicio.html`):**
```html
<header class="site-header">
  <div class="container navbar">
    <div class="brand">
      <div class="brand-avatar">
        <img src="../img/perfil.jpg" alt="Foto de perfil de David Torres">
      </div>
      <div class="brand-text">
        <span>David Torres</span>
        <span>Técnico en Bases de Datos · Soporte IT</span>
      </div>
    </div>

    <button class="nav-toggle" onclick="document.querySelector('.nav-links').classList.toggle('open')">
      ☰
    </button>

    <nav class="nav-links">
      <a href="inicio.html" class="active">Inicio</a>
      <a href="acerca-de.html">Acerca de</a>
      <a href="proyectos.html">Proyectos</a>
      <a href="blog.html">Blog</a>
      <a href="contacto.html">Contacto</a>
    </nav>
  </div>
</header>
```

**Descripción:**
- **`<header class="site-header">`**: Contenedor principal del encabezado.
- **`class="brand"`**: Agrupa la foto de perfil (`brand-avatar`) y el texto de la marca (`brand-text`), que incluye el nombre y el rol profesional.
- **`<button class="nav-toggle">`**: Botón tipo "hamburguesa" que se muestra en dispositivos móviles para desplegar el menú de navegación.
- **`<nav class="nav-links">`**: Contiene los enlaces de navegación a las diferentes páginas del sitio. La clase `.active` se usa para resaltar la página actual.

### 4.2. Página de Inicio (`inicio.html`)

Es la página de bienvenida. Su objetivo es captar la atención del visitante y presentar un resumen rápido del perfil profesional.

- **Sección Hero (`<section class="hero">`)**: Es el componente principal. Se divide en dos columnas:
    1.  **Contenido principal**: Incluye un "badge" de disponibilidad, el titular principal, un subtítulo descriptivo y botones de llamada a la acción ("Ver proyectos", "Contactar").
    2.  **Tarjeta de Perfil (`<aside class="hero-card">`)**: Una tarjeta lateral con un resumen visual que incluye la foto, el nombre, el rol y datos clave como la ubicación y especialidad.

### 4.3. Página "Acerca de" (`acerca-de.html`)

Ofrece una visión más profunda del perfil profesional, experiencia y formación.

- **Sección de Experiencia (`<div class="timeline">`)**: Muestra la trayectoria profesional en formato de línea de tiempo. Cada ítem (`timeline-item`) detalla el rol, la empresa y las responsabilidades.
- **Sección de Formación**: Similar a la de experiencia, detalla la educación y certificaciones.
- **Tabla de Habilidades (`<table class="skills-table">`)**: Presenta las competencias técnicas de forma organizada, indicando el nivel de dominio en cada una.

### 4.4. Página de Proyectos (`proyectos.html`)

Muestra una selección de trabajos relevantes en un formato de cuadrícula.

- **Cuadrícula de Proyectos (`<div class="projects-grid">`)**: Cada proyecto se presenta en una tarjeta (`project-card`) que incluye una imagen (actualmente un placeholder), título, descripción, y etiquetas (`tag`) que clasifican el proyecto.

### 4.5. Página de Blog (`blog.html`)

Un espacio para compartir artículos y reflexiones.

- **Cuadrícula de Blog (`<div class="blog-grid">`)**: Muestra las entradas del blog en tarjetas (`blog-post`) con su metainformación (categoría y fecha), título y un breve resumen.

### 4.6. Página de Contacto (`contacto.html`)

Esta página contiene la información de contacto y un formulario para que los visitantes puedan enviar mensajes directamente.

**Código del Formulario:**
```html
<form class="form" action="https://formspree.io/f/movrnwgd" method="POST">
  <div class="form-group">
    <label for="nombre">Nombre completo</label>
    <input class="form-control" type="text" id="nombre" name="nombre" placeholder="Ej. Juan Pérez">
  </div>

  <div class="form-group">
    <label for="correo">Correo corporativo</label>
    <input class="form-control" type="email" id="correo" name="email" placeholder="empresa@dominio.com">
  </div>

  <div class="form-group">
    <label for="mensaje">Mensaje</label>
    <textarea class="form-textarea" id="mensaje" name="message" placeholder="Cuéntame brevemente qué necesitas…"></textarea>
  </div>

  <button class="btn btn-primary" type="submit">
    Enviar mensaje
  </button>
</form>
```

**Descripción:**
- **`<form action="..." method="POST">`**: Define el formulario.
  - El atributo `action` apunta a la URL única proporcionada by Formspree. Esto dirige los datos del formulario a su servicio.
  - `method="POST"` es el método HTTP requerido por Formspree para recibir los datos.
- **`name="email"` y `name="message"`**: Estos nombres de campo son estándar para que Formspree pueda procesar correctamente el correo del remitente y el contenido del mensaje.
- El resto de los campos (`nombre`, `empresa`) se enviarán como datos adicionales en el correo electrónico.

### 4.7. Pie de Página (`<footer>`)

Es un componente común a todas las páginas que contiene información de copyright y enlaces de navegación secundarios.

```html
<footer class="site-footer">
  <div class="container footer-inner">
    <span>© 2025 David Santiago Torres Fonseca · Portafolio profesional</span>
    <div class="footer-links">
      <a href="acerca-de.html">Acerca de</a>
      <a href="proyectos.html">Proyectos</a>
      <a href="contacto.html">Contacto</a>
    </div>
  </div>
</footer>
```

## 5. Hoja de Estilos (`Estilos/style.css`)

El archivo `style.css` centraliza todo el diseño visual del sitio. Está estructurado de manera modular para facilitar su mantenimiento.

### 5.1. Variables Globales (`:root`)

Se utiliza `:root` para declarar variables CSS que definen la paleta de colores, tipografías y otras propiedades globales. Esto permite cambiar la apariencia de todo el sitio modificando solo unas pocas líneas.

**Código de ejemplo:**
```css
:root {
  --color-bg: #050908;
  --color-accent: #a8e6cf;
  --color-text: #f5f5f5;
  --font-main: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
}
```
- `--color-bg`: Color de fondo principal (un tono oscuro).
- `--color-accent`: Color de acento principal (verde pastel), usado para resaltar elementos importantes.
- `--color-text`: Color del texto principal.
- `--font-main`: Fuente principal utilizada en todo el sitio.

### 5.2. Diseño Responsivo (`@media`)

El diseño se adapta a diferentes tamaños de pantalla mediante *media queries*.

```css
@media (max-width: 900px) {
  /* Estilos para tabletas */
  .hero {
    grid-template-columns: 1fr;
  }
  .projects-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 720px) {
  /* Estilos para móviles */
  .nav-links {
    display: none; /* El menú se oculta y se controla con JS */
  }
  .nav-toggle {
    display: inline-flex; /* Se muestra el botón de menú hamburguesa */
  }
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
```
- **Hasta 900px**: Las cuadrículas se adaptan a dos columnas y el diseño del "hero" pasa a una sola columna.
- **Hasta 720px**: El menú de navegación principal se oculta y se reemplaza por un botón de despliegue. Las cuadrículas pasan a mostrar un solo elemento por fila para una mejor visualización en pantallas pequeñas.

### 5.3. Estilos de Componentes

El CSS define estilos consistentes para componentes reutilizables como:
- **Tarjetas (`.card`, `.project-card`)**: Usan fondos semitransparentes, bordes sutiles y sombras para crear una sensación de profundidad. Tienen una pequeña animación al pasar el cursor sobre ellas.
- **Botones (`.btn`, `.btn-primary`)**: Estilos bien definidos para botones principales y secundarios, con efectos `hover` para mejorar la interactividad.
- **Línea de tiempo (`.timeline`)**: Estilos específicos para presentar la experiencia y formación de una manera clara y legible.

## 6. Modificaciones Realizadas

Durante el desarrollo, se realizaron las siguientes tareas de mantenimiento y mejora:

1.  **Corrección de Rutas de Archivos**: Inicialmente, los archivos HTML en la carpeta `Main/` no podían acceder correctamente a los recursos en `Estilos/` e `img/`. Se corrigieron todas las rutas relativas anteponiendo `../` para subir un nivel en la estructura de directorios. Por ejemplo, `<link rel="stylesheet" href="estilos/style.css">` se cambió a `<link rel="stylesheet" href="../Estilos/style.css">`.

2.  **Integración del Formulario de Contacto**: Se configuró el formulario HTML para usar Formspree como backend. Esto implicó:
    -   Añadir el atributo `action` con la URL del endpoint de Formspree.
    -   Establecer el `method` en `POST`.
    -   Asegurar que los campos de correo y mensaje tuvieran los `name` correctos (`email` y `message` respectivamente).
