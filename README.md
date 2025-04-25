# Cake, fun and confetti – Web Development Project

This repository contains the source code for the "Cake, fun and confetti" website. It is developed as part of a Web Development course delivered by Code Institute in collaboration with the University of Peterborough.

## Project Overview

This project aims to build a responsive and accessible party planning website. It follows a staged development process, starting with a basic HTML5 structure and progressively adding styled content, interactive features, and mobile-friendly layout.

---

## Basic HTML Structure

### Included in this Version

- HTML5 `<!DOCTYPE>` declaration
- HTML document language set to English
- UTF-8 character encoding
- Viewport meta tag for mobile responsiveness
- Page title set to **Cake, fun and confetti**
- Empty `<body>` element prepared for future content

### Technologies Used

- HTML5

### Future Enhancements

- Implementation of a responsive navigation bar
- Development of sections including About, Services, Gallery, and Contact
- Integration of Bootstrap for layout and styling
- Application of semantic HTML and accessibility best practices

---

##  Responsive Navbar

This version introduces a responsive navigation bar to the party planner website, **Cake, fun and confetti**, improving the site’s layout and user experience.

### Features in This Version

- Brand name: **Cake, fun and confetti**
- Navigation links:
  - Home
  - About
  - Services
  - Gallery
  - Contact
- Responsive design using Bootstrap 5
- Collapsible menu for smaller screens
- Clean and semantic HTML structure

### Technologies Used

- HTML5
- Bootstrap 5 (via CDN)

---
## Changes and improvements 23/04/24

Gallery section was removed as I decided is not necessary. 

## New Enhancements

### Typography – Google Fonts  
Two custom Google Fonts were integrated to enhance the site's visual identity:

- **[Halant](https://fonts.google.com/specimen/Halant)** – used for body text  
- **[Hachi Maru Pop](https://fonts.google.com/specimen/Hachi+Maru+Pop)** – used for branding and headings

**Included via HTML:**
```html
<link href="https://fonts.googleapis.com/css2?family=Hachi+Maru+Pop&family=Halant:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

**Applied in CSS:**
```css
body {
  font-family: 'Halant', serif;
}
.navbar-brand,
h1, h2, h3 {
  font-family: 'Hachi Maru Pop', cursive;
}
```

---

### Color Scheme  
A custom color palette was introduced using CSS variables for consistent styling:

```css
:root {
  --blue-primary: #02ACCE;
  --yellow: #FDCB3B;
  --cream: #FDE7A9;
  --blue-accent: #28ADCE;
  --orange: #FA8B46;

  --background: #FDE7A9;
  --text: #1A1A1A;
}
```

These colors are used across backgrounds, text, buttons, and hover states.

---

### Bootstrap 5 Integration  
Bootstrap 5 is used for layout and responsive design, included via CDN:

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
```

Bootstrap is used for the navbar, grid layout, and utility classes.

---

### Responsive Design with Media Queries  
Custom media queries were added to support different viewport sizes:

```css
@media (min-width: 768px) {
  .navbar-brand { font-size: clamp(0.5rem, 2vw); }
  .logo-img { height: 40px; }
}

@media (max-width: 767.98px) {
  .navbar-brand { font-size: 1rem; width: 40%; }
  .logo-img { height: 36px; }
}

@media (max-width: 480px) {
  .navbar-brand {
    font-size: 0.8rem;
    text-align: center;
    margin: 0 auto;
    white-space: normal;
  }
  .logo-img { height: 30px; }
}
```

These adjustments ensure the content and branding scale appropriately across devices.

---

### Logo Integration  
The logo was added next to the brand text in the navbar for clear site branding.

**HTML:**
```html
<a class="navbar-brand d-flex align-items-center" href="index.html">
  <img src="assets/images/cake-logo.png" alt="Logo" class="logo-img me-2" />
  <span class="brand-text">Cake, Confetti and fun</span>
</a>
```

**CSS:**

.logo-img {
  height: 30px;
  width: auto;
  margin-right: 0.5rem;
}
```

The logo's size is also adjusted responsively through media queries.


## Second and third commit 23/04/24

Gallery section was removed as I decided is not necessary. 

## New Enhancements

### Typography – Google Fonts  
Two custom Google Fonts were integrated to enhance the site's visual identity:

- **[Halant](https://fonts.google.com/specimen/Halant)** – used for body text  
- **[Hachi Maru Pop](https://fonts.google.com/specimen/Hachi+Maru+Pop)** – used for branding and headings

**Included via HTML:**
```html
<link href="https://fonts.googleapis.com/css2?family=Hachi+Maru+Pop&family=Halant:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

**Applied in CSS:**
```css
body {
  font-family: 'Halant', serif;
}
.navbar-brand,
h1, h2, h3 {
  font-family: 'Hachi Maru Pop', cursive;
}
```

---

### Color Scheme  
A custom color palette was introduced using CSS variables for consistent styling:

```css
:root {
  --blue-primary: #02ACCE;
  --yellow: #FDCB3B;
  --cream: #FDE7A9;
  --blue-accent: #28ADCE;
  --orange: #FA8B46;

  --background: #FDE7A9;
  --text: #1A1A1A;
}
```

These colors are used across backgrounds, text, buttons, and hover states.

---

### Bootstrap 5 Integration  
Bootstrap 5 is used for layout and responsive design, included via CDN:

```html
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
```

Bootstrap is used for the navbar, grid layout, and utility classes.

---

### Responsive Design with Media Queries  
Custom media queries were added to support different viewport sizes:

```css
@media (min-width: 768px) {
  .navbar-brand { font-size: clamp(0.5rem, 2vw); }
  .logo-img { height: 40px; }
}

@media (max-width: 767.98px) {
  .navbar-brand { font-size: 1rem; width: 40%; }
  .logo-img { height: 36px; }
}

@media (max-width: 480px) {
  .navbar-brand {
    font-size: 0.8rem;
    text-align: center;
    margin: 0 auto;
    white-space: normal;
  }
  .logo-img { height: 30px; }
}
```

These adjustments ensure the content and branding scale appropriately across devices.

---

### Logo Integration  
The logo was added next to the brand text in the navbar for clear site branding.

**HTML:**
```html
<a class="navbar-brand d-flex align-items-center" href="index.html">
  <img src="assets/images/cake-logo.png" alt="Logo" class="logo-img me-2" />
  <span class="brand-text">Cake, Confetti and fun</span>
</a>
```

**CSS:**
```css
.logo-img {
  height: 30px;
  width: auto;
  margin-right: 0.5rem;
}
```

The logo's size is also adjusted responsively through media queries.



## Acknowledgements

This project is part of the coursework for the **Web Development** module provided by **Code Institute** in collaboration with the **University of Peterborough**.
