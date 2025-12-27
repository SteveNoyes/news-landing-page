## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [Highlight](#highlight)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Build out the news website homepage to look as close to the design documents as possible.

### Screenshot

![Mobile](./assets/images/mobile.png)

![Desktop](./assets/images/desktop.png)

### Links

- Solution URL: [Github](https://github.com/SteveNoyes/news-landing-page)
- Live Site URL: [Github live site](https://stevenoyes.github.io/news-landing-page/)

## My process

### Built with

- Mobile-first workflow
- Flexbox
- Grid

### Highlight
```html
<nav>
  <a href="index.html"><img src="./assets/images/logo.svg" alt="W Logo"></a>
  <a id="hamburger-icon" href="#!" onclick="openNav()"><img src="./assets/images/icon-menu.svg" alt="Menu Hamburger Icon"></a>
  <div id="nav-list" class="nav-list">
    <img onclick="closeNav()" id="close-icon" src="./assets/images/icon-menu-close.svg" alt="Close Icon">
    <a href="index.html">Home</a>
    <a href="#new">New</a>
    <a href="#!">Popular</a>
    <a href="#!">Trending</a>
    <a href="#!">Categories</a>
  </div>
</nav>
```
```css
main {
  display: grid;
  gap: 1rem;
  grid-template-columns: repeat(3, 1fr);
  grid-template-areas: "main-article main-article new-news"
                       "list-of-articles list-of-articles list-of-articles";
}
```
```js
// Mobile side bar nav menu controls
function openNav() {
  document.getElementById("hamburger-icon").style.display = "none";
  document.getElementById("nav-list").style.display = "flex";
  document.getElementsByTagName("html")[0].classList.add("sidebar-overlay-settings");
  document.getElementsByTagName("body").classList.add("sidebar-overlay-settings");
}
function closeNav() {
  document.getElementById("hamburger-icon").style.display = "inline";
  document.getElementById("nav-list").style.display = "none";
  document.getElementsByTagName("html")[0].classList.remove("sidebar-overlay-settings");
  document.getElementsByTagName("body").classList.remove("sidebar-overlay-settings");
}
// Checks screen size and updates the header image 
function updateOnScreenResize() {
  const screenSizeWidth = window.innerWidth || document.documentElement.clientWidth;
  if (screenSizeWidth < 1000) {
    let updateHeaderImage = document.getElementById("top-img");
    updateHeaderImage.src = "./assets/images/image-web-3-mobile.jpg";
  } else {
    let updateHeaderImage = document.getElementById("top-img");
    updateHeaderImage.src = "./assets/images/image-web-3-desktop.jpg";
  }
}
updateOnScreenResize();
window.addEventListener('resize', updateOnScreenResize);
```

### Useful resources

- [Transfonter](https://transfonter.org/) - This tool converts any TTF, OTF, WOFF, WOFF2 or SVG fonts to css @font-face formats with CSS and HTML sample files.
- [Reset CSS](https://meyerweb.com/eric/tools/css/reset/) - Reduce browser inconsistencies in things like default line heights, margins and font sizes of headings, and so on.
- [Image Reset CSS](https://gist.github.com/palashmon/35bda7887eb4bc45459d71eca3dda7a5) - This CSS block is a More Effective CSS Image Reset. It resets the default styles of an image element. 

## Author

- Website - [Steven Noyes](https://www.stevenmnoyes.com)