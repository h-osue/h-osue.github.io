# Galleries Deluxe con Hugo

Sitio Hugo para publicar múltiples galerías fotográficas, basado en
[Galleries Deluxe](https://github.com/bep/galleriesdeluxe). El tema y sus
dependencias están incluidos en `themes/`, por lo que no es necesario instalar
Go ni usar submódulos de Git.

## Requisitos

- Hugo 0.160.0 o posterior.
- Para desarrollo local: `hugo server`.

## Agregar una galería

Cada galería es una carpeta dentro de `content/galleries/`:

```text
content/galleries/
└── nombre-de-la-galeria/
    ├── index.md
    ├── foto-01.jpg
    ├── foto-02.jpg
    └── foto-03.webp
```

El archivo `index.md` contiene el título, fecha, categorías y descripción:

```yaml
---
title: Nombre de la galería
date: 2026-09-18
categories: [viajes, retratos]
cover: portada.jpg
---

Descripción de la galería.
```

El álbum inicial está preparado en
`content/galleries/todos-somos-cafe-satipo-2026/`. Copia allí sus fotografías;
no es necesario crear una subcarpeta adicional. Para un nuevo álbum, duplica
esa carpeta, cambia su nombre y edita `index.md`. No elimines
`content/galleries/_index.md`.

El archivo indicado en `cover` se utiliza como portada de la tarjeta y también
permanece visible dentro de la galería. Si se omite el campo, el tema elige una
portada automáticamente.

## Desarrollo local

```sh
hugo server
```

## GitHub Pages

El workflow `.github/workflows/hugo.yaml` compila y publica `public/` cuando se
envían cambios a `main`. En GitHub selecciona **Settings > Pages > Source >
GitHub Actions**.

No agregues manualmente `public/` al repositorio; Hugo lo genera en cada build.
