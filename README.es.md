# Frontend Masters Intermediate React v6

Idioma: Español | [English](README.md)

Este repositorio contiene los ejercicios y ejemplos desarrollados durante el curso de Frontend Masters [Intermediate React v6](https://frontendmasters.com/courses/intermediate-react-v6/), junto con el sitio complementario del curso en [intermediate-react-v6.holt.courses](https://intermediate-react-v6.holt.courses/).

Cada carpeta es un ejemplo independiente o una mini aplicación enfocada en un concepto específico de React o de tecnologías cercanas. Los proyectos están separados a propósito para que cada técnica se pueda explorar, ejecutar y modificar por separado.

## Qué incluye

- `deferred`: demuestra `useDeferredValue` con una interfaz de filtros de imagen para que la vista costosa siga siendo responsiva mientras cambian los controles.
- `optimistic`: muestra actualizaciones optimistas con `useOptimistic`, `useTransition` y un pequeño feed respaldado por servidor para “deep thoughts”.
- `perf`: explora optimización de rendimiento con `useMemo`, `useCallback`, `memo` y una vista previa de Markdown deliberadamente costosa.
- `rsc`: un ejemplo de React Server Components con componentes de servidor y cliente separados, además de un pipeline de servidor personalizado.
- `ssg`: un ejemplo de generación estática que renderiza React a HTML estático en tiempo de build.
- `ssr`: un ejemplo de renderizado del lado del servidor que emite HTML desde Fastify y luego hidrata en el cliente.
- `transitions`: usa `useTransition` para mantener responsiva una interfaz de marcadores deportivos mientras se cargan nuevos datos.
- `note-app`: una app de Next.js con server components, server actions, datos en SQLite y varias rutas para leer y escribir notas.

## Estructura del repositorio

| Carpeta        | Enfoque                                                    |
| -------------- | ---------------------------------------------------------- |
| `deferred/`    | Renderizado diferido y actualizaciones costosas de UI      |
| `optimistic/`  | Mutaciones optimistas y reconciliación de estado asíncrono |
| `perf/`        | Patrones de rendimiento en React                           |
| `rsc/`         | React Server Components                                    |
| `ssg/`         | Generación de sitios estáticos                             |
| `ssr/`         | Renderizado del lado del servidor e hidratación            |
| `transitions/` | Estados de carga impulsados por transiciones               |
| `note-app/`    | App de notas en Next.js con server actions y SQLite        |

## Cómo empezar

Cada ejemplo tiene sus propias dependencias y scripts. Instala y ejecuta la carpeta que quieras explorar.

### Ejemplos basados en Vite

Las siguientes carpetas usan Vite:

- `deferred/`
- `optimistic/`
- `perf/`
- `transitions/`

Flujo típico:

```bash
cd deferred
npm install
npm run dev
```

Reemplaza `deferred` por cualquiera de los otros ejemplos con Vite.

### App de notas en Next.js

```bash
cd note-app
npm install
npm run dev
```

La app usa datos de SQLite almacenados dentro del proyecto e incluye rutas para:

- `/` para la navegación principal
- `/my` para las notas personales
- `/write` para crear una nota
- `/teacher` para el feed del profesor
- `/who-am-i` para cambiar el nombre del usuario actual

### Ejemplo de React Server Components

El proyecto `rsc/` usa procesos separados de cliente y servidor:

```bash
cd rsc
npm install
npm run dev:client
```

En otra terminal:

```bash
cd rsc
npm run dev:server
```

### Ejemplo de SSR

```bash
cd ssr
npm install
npm run build
npm start
```

### Ejemplo de SSG

```bash
cd ssg
npm install
npm run build
```

## Notas

- Estas carpetas están pensadas para estudiarse de forma independiente, no como una sola aplicación combinada.
- Algunos ejemplos dependen de assets locales, artefactos generados en build o un archivo de base de datos SQLite dentro de la carpeta del proyecto.
- El curso se centra en entender el modelo de renderizado, el flujo de datos y los tradeoffs de cada patrón, más que en construir un producto final pulido.

## Referencias del curso

- Curso de Frontend Masters: https://frontendmasters.com/courses/intermediate-react-v6/
- Sitio complementario: https://intermediate-react-v6.holt.courses/
