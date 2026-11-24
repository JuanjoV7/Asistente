# Asistente del clan · Maqueta navegable

Prototipo visual de un asistente de IA para un reto de clase. Es una **maqueta**: no hay lógica, no se conecta a ningún modelo ni a una API. Muestra los cuatro estados de la conversación y permite recorrerlos con enlaces.

## Estados
- **Vacío** (`index.html`): bienvenida y cuatro preguntas rápidas.
- **Cargando** (`paginas/cargando.html`): mensaje "Pensando…" con indicador animado.
- **Respuesta** (`paginas/respuesta.html`): respuesta con una fuente verificable ("Fuente: Calendario de la cohorte").
- **Error** (`paginas/error.html`): aviso de que no pudo responder, con "Reintentar", "Reformular la pregunta" y "Hablar con un coach".

## Elementos siempre visibles
- Aviso de límites de la IA ("Las respuestas son generadas por IA y pueden contener errores").
- Botón **Hablar con un coach** en el encabezado.
- Barra de consulta fija abajo, con el placeholder "¿Cuándo es la sesión de IA?" y el botón Enviar.

## Cómo se navegan los estados
Sin JavaScript propio: cada estado es una página HTML y se pasa de una a otra con enlaces (menú de estados del encabezado, preguntas rápidas, "Ver la respuesta", "Reintentar", etc.). El formulario de envío lleva al estado "Cargando"; el texto escrito no se procesa.

## Tecnologías
- HTML5 semántico: `header`, `nav`, `main`, `section`, `article`, `aside`, `footer` y `form`.
- CSS3 en `css/styles.css`: variables en `:root`, Flexbox y Grid.
- Tailwind CSS 4 (script de jsDelivr) para la estructura, el espaciado y lo responsive.
- Google Fonts (Poppins).

## Reparto entre Tailwind y styles.css
- **Tailwind:** disposición de la página, espaciado, tamaños de texto, bordes redondeados y breakpoints (`lg:`).
- **styles.css:** colores y estados `hover` y `focus` con las variables de `:root`, más tres componentes con Flexbox y Grid (barra de consulta, grupo de acciones y preguntas rápidas).

## Accesibilidad
- Un solo `h1` por página, `label` asociado al campo de la consulta (oculto visualmente).
- Estado activo con `aria-current="page"`, "Pensando…" con `role="status"` y el error con `role="alert"`.
- Foco visible con teclado y animación desactivada con `motion-reduce`.

## Estructura
```
asistente-ia/
├── index.html
├── paginas/
│   ├── cargando.html
│   ├── respuesta.html
│   └── error.html
├── css/
│   └── styles.css
└── README.md
```

## Pendiente de la maqueta
- El enlace de "Hablar con un coach" y el de la fuente usan `#` como marcador.
- La fecha y la fuente de la respuesta son datos de ejemplo.