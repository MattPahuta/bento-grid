# Frontend Mentor - Bento grid solution

This is a solution to the [Bento grid challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/bento-grid-RMydElrlOj). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size

### Screenshot

![](./project-ss.png)

### Links

- [Frontend Mentor solution page](https://www.frontendmentor.io/solutions/responsive-bento-layout-using-css-grid-YyDTzMrwmN)
- [live demo site](https://bento-grid-mocha.vercel.app/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- CSS Grid
- Mobile-first workflow

### What I learned

I haven't completed all that many bento layouts in the past, so this was a great opportunity to practice Grid techniques and maximize the utility of custom properties with fallbacks. Given these bento cards have a lot of variation in background colors, font sizes, padding, etc., the custom prop strategy Kevin Powell demonstrates (linked below) was ideal. It's an approach I haven't used too often so I was happy to gain more experience with it here.

The basic setup of the bento grid and cards, leveraging custom props with default values and nested selectors and media queries for more organized styles:

```css
.bento-grid__card {
  padding-inline: var(
    --bento-card-padding-inline,
    var(--spacing-200)
  );
  padding-block: var(--bento-card-padding-block, var(--spacing-200));
  color: var(--bento-card-color, var(--clr-black));
  background-color: var(--bento-card-bg, var(--clr-white));
  border-radius: 10px;
  display: grid;
  gap: var(--bento-card-gap, var(--spacing-300));
  align-content: var(--bento-card-vertical-align, start);
  align-items: var(--bento-card-vertical-align, start);
  justify-items: var(--bento-card-horizontal-align, start);
  text-align: var(--bento-card-horizontal-align, start);
  overflow: clip;
}

.bento-grid__card img {
  max-width: var(--bento-card-image-max-width, 100%);
  width: var(--bento-card-image-width, 100%);
  order: var(--bento-card-image-order);
}

.bento-grid > :nth-child(1) {
  --bento-card-padding-inline: var(--spacing-400);
  --bento-card-padding-block: var(--spacing-500);
  --heading-font-size: var(--fs-xl);
  --heading-span-color: var(--clr-yellow-500);
  --bento-card-color: var(--clr-white);
  --bento-card-bg: var(--clr-purple-500);
  --bento-card-horizontal-align: center;
  --bento-card-image-width: 192px;
  grid-area: card1;

  @media (width > 37.5rem) {
    --bento-card-padding-block: var(--spacing-700);
    --bento-card-vertical-align: center;
  }

  .bento-grid__card-content {
    display: grid;
    gap: var(--spacing-100);
    justify-items: var(--bento-card-horizontal-align);
  }

  @media (width > 60rem) {
    --bento-card-padding-block: var(--spacing-650);
  }
}
```

### Useful resources

- [Kevin Powell's Bento Grid Tutorial](https://www.youtube.com/watch?v=h4dHvo09cG4) - Full disclosure, Kevin Powell has an excellent (as usual) video tutorial for this project, tackling the layout challenges and creating reusable custom variables. Much of my solution is inspired by his approach with some tweaks here and there. Notably, I had access to the Figma file, whereas Kevin was working off only the design .jpg file, so I was able to achieve more specific details around spacing, image widths, etc.

## Author

- Website - [Matt Pahuta](https://www.mattpahuta.com)
- Frontend Mentor - [@mattpahuta](https://www.frontendmentor.io/profile/MattPahuta)
- Bluesky - [@mattpahuta](https://bsky.app/profile/mattpahuta.bsky.social)
- LinkedIn - [Matt Pahuta](www.linkedin.com/in/mattpahuta)

## Acknowledgments

I've probably learned more about CSS from Kevin Powell than from every other source combined. I'm so grateful for his thoughtfully produced content and courses.