# Parallax-Website

![image](https://github.com/user-attachments/assets/b3ee806f-5d34-419f-bea7-193c02e09f43)

This website demonstrates a **Parallax Scrolling Effect**, a web design technique where background elements move at a different speed than the foreground elements while scrolling. This creates a sense of depth and provides a more engaging user experience.

## Features
- **Parallax Effect**: As you scroll down the page, background elements (like stars, moon, and mountains) move at different speeds, creating an illusion of depth and motion.
- **Responsive Navigation**: A simple navigation bar with links to different sections of the website, such as *Home*, *About*, *Work*, and *Contact*.
- **Scrolling Animation**: Various elements on the page, like the moon, mountains, and text, are animated based on the user's scroll position.

---

## How It Works

### HTML Structure

The website has a clean structure with:
- A **header** containing a logo and a navigation menu.
- The **first section** featuring background images of stars, the moon, and mountains, along with the text *"Moon Light"*.
- The **second section** provides an introduction about the creator, "M IRsyad Kurniawan", and includes some placeholder text for additional content.

### CSS Styling

- The layout is designed using basic CSS, with specific positioning of background images to create the parallax effect.
- **Flexbox** is used for arranging elements in the header and sections of the page to ensure a responsive design.

### JavaScript

- The **Parallax Effect** is implemented with JavaScript, where the position of background elements changes dynamically based on the scroll position of the window.
- Each element (such as the stars, moon, and mountains) moves at a different speed to create a **layered effect**.

---

## Code Overview

### HTML Structure

```html
<header>
    <a href="#" class="logo">Logo</a>
    <ul>
        <li><a href="#" class="active">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Work</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</header>

<section>
    <img src="./image/stars.png" id="stars">
    <img src="./image/moon.png" id="moon">
    <img src="image/mountains_behind.png" id="mountains_behind">
    <h2 id="text">Moon Light</h2>
    <a href="#sec" id="btn">Explore</a>
    <img src="./image/mountains_front.png" id="mountains_front">
</section>
```

### Syling With CSS
```css
body {
    margin: 0;
    font-family: Arial, sans-serif;
}

header {
    position: fixed;
    width: 100%;
    top: 0;
    z-index: 100;
}

#stars {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
}

#moon {
    position: absolute;
    top: 50px;
    right: 50px;
}

#mountains_behind {
    position: absolute;
    bottom: 0;
    left: 0;
}

#mountains_front {
    position: absolute;
    bottom: 0;
    left: 0;
}
```

### DOM JavaScript
```js
let stars = document.getElementById('stars');
let moon = document.getElementById('moon');
let mountains_behind = document.getElementById('mountains_behind');
let text = document.getElementById('text');
let mountains_front = document.getElementById('mountains_front');
let header = document.querySelector('header');

window.addEventListener('scroll', function () {
    let value = window.scrollY;
    stars.style.left = value * 0.25 + 'px';
    moon.style.top = value * 1.05 + 'px';
    mountains_behind.style.top = value * 0.5 + 'px';
    mountains_front.style.top = value * 0 + 'px';
    text.style.marginRight = value * 4 + 'px';
    header.style.top = value * 0.5 + 'px';
});

```
