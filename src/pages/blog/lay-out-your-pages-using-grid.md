---
title: Lay Out Your Pages Using Grid
layout: ../../layouts/Blog.astro
author: Parker Brown
summary: Structure your site using this simple CSS grid layout.
date: 2022-08-31
---

## So you want to grid..

Something that always eluded me was adding a basic footer for websites. Sure, you can use `position: absolute` and anchor it to the bottom of the page, but then you're stuck adding padding to the bottom of the main content just to make sure your content doesn't hide behind the footer.

This tutorial is for a basic header, main, and footer, but can be used for many other things. It's super easy and is just one example of the things grid can do. Let's get started!

## The HTML

Start with the basics:

```html
<body>
    <header></header>
    <main></main>
    <footer></footer>
</body>
```

We've got a basic body with a header, main section, and footer. We want the header to take **only** as much space as it needs and the same for the footer. The main section should then fill up the rest of the space.

## The CSS

Let's start with the `body`:

```css
body {
    min-height: 100vh;
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        'header',
        'main',
        'footer';
}
```

`min-height: 100vh` will keep the body at least as tall as the viewport at all times.

We set `grid-template-columns` to `1fr` because we only need 1 column.

Setting `grid-template-rows` to `auto 1fr auto` lets grid know that we want 3 rows:

- The first and last row will be `auto` so that they only use the space they need.

- We use `1fr` for the main content row so that it will take up the remaining available space.

`grid-template-areas` is just giving names to each row so that we can explicity tell our header, main, and footer where to be. **It is not required unless your elements are out of order or you have more than those 3 elements in the body.**

Lastly, if you decide to use grid areas, you need to assign grid areas to the elements in the body:

```css
header {
    grid-area: header;
}

main {
    grid-area: main;
}

footer {
    grid-area: footer;
}
```

## That's it!

If you want to see what it looks like, you already have! This website uses the above technique to lay out the navbar, content, and footer. Inspect the page and take a look if you're interested.