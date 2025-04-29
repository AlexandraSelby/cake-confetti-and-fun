# Cake, Fun and Confetti – Web Development Project

## Project Overview

The **Cake, Fun and Confetti** website is a multi-page, responsive party-planning platform developed as part of the Web Development course at Code Institute in collaboration with the University of Peterborough. It began as a basic HTML5 scaffold and was progressively enhanced with modern web technologies to deliver an engaging user experience across Home, About, Services, and Contact pages.

Key objectives included:
* Building a semantic, accessible HTML structure.
* Implementing a dynamic video background hero section on the homepage.
* Designing a sticky, responsive navigation header linking to each page.
* Presenting services via Bootstrap 5–powered cards with buttons to dedicated pages.
* Establishing a cohesive design language using CSS variables, Google Fonts, and responsive media queries.

## Technologies Used

* **HTML5** – Semantic markup and structure.
* **CSS3** – Custom styling, Flexbox, CSS variables, and media queries.
* **Bootstrap 5** – Responsive grid, navbar, cards, buttons, and collapse plugin.
* **JavaScript (Bootstrap JS bundle)** – Interactive components like navbar toggler and future modal dialogs.
* **Google Fonts** – Typography via *Halant* (body) and *Hachi Maru Pop* (headings & branding).
* **Canva** – Design tool for logo, card illustrations, and hero poster image.
* **Git & GitHub** – Version control, commits, and optional GitHub Pages deployment.

## Installation and Access

To clone and run locally:
```bash
git clone https://github.com/AlexandraSelby/cake-confetti-and-fun.git
cd cake-confetti-and-fun
# Open index.html in your browser
double-click index.html  # or `open index.html`
```

Live preview (via GitHub Pages if enabled):
* https://AlexandraSelby.github.io/cake-confetti-and-fun

## Project Structure

```
├── index.html             # Home page: header, hero, cards, footer
├── about.html             # About page: company overview and mission
├── services.html          # Services page: detailed offerings
├── contact.html           # Contact page: enquiry form and map
├── assets
│   ├── css
│   │   └── styles.css     # Variables, media queries, custom styles
│   ├── images            # Logo, poster, illustrations (designed in Canva)
│   └── videos            # Hero background video file
└── README.md              # Documentation and code explanations
```

## Header and Navigation Bar

A consistent header appears on every page, built with the `<nav>` element:
* Brand logo + site name (logo created in **Canva**).
* Collapse menu for mobile viewports via Bootstrap’s collapse plugin.
* Links to Home, About, Services, Contact.

**HTML**
```html
<nav class="navbar navbar-expand-sm sticky-top bg-primary">
  <div class="container">
    <a class="navbar-brand d-flex align-items-center" href="index.html">
      <img src="assets/images/cake-logo.png" alt="Cake Logo" class="logo-img me-2">
      <span class="brand-text">Cake, Confetti &amp; Fun</span>
    </a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
            data-bs-target="#navContent" aria-controls="navContent" aria-expanded="false">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navContent">
      <ul class="navbar-nav ms-auto">
        <li class="nav-item"><a class="nav-link" href="index.html">Home</a></li>
        <li class="nav-item"><a class="nav-link" href="about.html">About</a></li>
        <li class="nav-item"><a class="nav-link" href="services.html">Services</a></li>
        <li class="nav-item"><a class="nav-link" href="contact.html">Contact</a></li>
      </ul>
    </div>
  </div>
</nav>
```

**CSS**
```css
:root {
  --blue-primary: #02ACCE;
  --yellow: #FDCB3B;
  --cream: #FDE7A9;
  --text: #1A1A1A;
}
.navbar {
  background-color: var(--blue-primary);
  position: sticky;
  top: 0;
  z-index: 1000;
  padding: 0.5rem 1rem;
}
.navbar-brand {
  font-family: 'Hachi Maru Pop', cursive;
  color: #fff;
  font-size: clamp(1rem, 2vw, 1.5rem);
}
.nav-link {
  color: #fff !important;
  font-weight: 500;
  padding: 0.5rem 0.75rem;
}
.nav-link:hover {
  color: var(--yellow) !important;
}
.logo-img {
  height: 30px;
  margin-right: 0.5rem;
}
```

## Responsive Media Queries

Media queries guarantee an optimal layout on tablets and smartphones:

```css
/* Navbar & Logo */
@media (max-width: 768px) {
  .navbar-brand { font-size: 1rem; }
  .logo-img { height: 36px; }
}
@media (max-width: 480px) {
  .navbar-brand { text-align: center; font-size: 0.8rem; }
  .nav-link { font-size: 0.8rem; }
}

/* Hero Section */
@media (max-width: 768px) {
  .hero-video { height: 40vh; object-position: center; }
}
@media (max-width: 480px) {
  .hero-video { height: 30vh; }
}

/* Card Grid */
@media (min-width: 1200px) {
  .custom-wrapper { padding-left: 10vw; padding-right: 10vw; }
}
```

## Hero Section with Video Background

Engaging, full-width video serving as the homepage backdrop:

**HTML**
```html
<section class="hero-video-wrapper">
  <video class="hero-video" autoplay muted loop playsinline poster="assets/images/hero-poster.png">
    <source src="assets/videos/hero.mp4" type="video/mp4">
  </video>
</section>
```

**CSS**
```css
.hero-video-wrapper { overflow: hidden; border-radius: 1rem; }
.hero-video { width: 100%; height: 100%; object-fit: cover; }
```

## Card-Based Services Section (Bootstrap Cards)

Services are showcased using **Bootstrap 5** cards. Each card includes:
* An image (illustrations created in **Canva**).
* Title, description, and a button linking to its page.

**HTML**
```html
<div class="container-fluid py-4">
  <div class="row g-4">
    <div class="col-12 col-md-6 col-lg-3">
      <div class="card h-100">
        <img src="assets/images/kids-dancing.png" class="card-img-top" alt="Kids dancing">
        <div class="card-body d-flex flex-column">
          <h3>About Us</h3>
          <p>We sprinkle wonder on every celebration...</p>
          <a href="about.html" class="btn btn-primary mt-auto">Learn More</a>
        </div>
      </div>
    </div>
    <!-- Repeat for Services, Special Touch, Contact -->
  </div>
</div>
```

**CSS Hover Effects**
```css
.card { transition: transform 0.3s, box-shadow 0.3s; box-shadow: 0 2px 6px rgba(0,0,0,0.1); }
.card:hover { transform: translateY(-8px); box-shadow: 0 8px 20px rgba(0,0,0,0.15); }
```

## Typography and Design System

**Google Fonts** in `<head>`
```html
<link href="https://fonts.googleapis.com/css2?family=Halant:wght@300;400;500;600;700&family=Hachi+Maru+Pop&display=swap" rel="stylesheet">
```

**Base CSS**
```css
body { font-family: 'Halant', serif; background-color: var(--cream); color: var(--text); margin: 0; padding: 0; }
h1, h2, h3 { font-family: 'Hachi Maru Pop', cursive; color: var(--blue-primary); }
```

**Variables**
```css
:root {
  --blue-primary: #02ACCE; --yellow: #FDCB3B; --cream: #FDE7A9;
  --blue-accent: #28ADCE; --orange: #FA8B46; --text: #1A1A1A;
  --card-background: #02ACCE;
}

# Footer Section

## Overview
This section covers the implementation of a responsive footer using Bootstrap utility classes, Font Awesome icons for social links, and custom CSS styling.

## Structure
```html
<footer class="footer">
  <div class="footer-container">
    <div class="footer-contact">
      <!-- Contact info or button -->
    </div>
    <div class="footer-social">
      <!-- Font Awesome social links -->
      <a href="#"><i class="fa-brands fa-twitter"></i></a>
      <a href="#"><i class="fa-brands fa-facebook-f"></i></a>
      <!-- more icons -->
    </div>
    <div class="footer-copy">
      &copy; 2025 Your Company. All rights reserved.
    </div>
  </div>
</footer>
```

## Styling
- `.footer`: Background set to `var(--blue-primary)` and full-width layout.
- `.footer-container`: Flex container, column direction, centered text.
- `.footer-contact`, `.footer-social`, `.footer-copy`: Ordered using `order` property to control stacking.
- Social links styled with transitions and hover effects swapping to accent yellow.

## Push-Down Behavior
To ensure the footer stays at the bottom when page content is short, the following CSS is applied:
```css
html, body { height: 100%; margin: 0; }
body { display: flex; flex-direction: column; }
.custom-wrapper { flex: 1; }
.footer { position: relative; }


### Contact Form Component

**This snippet demonstrates how to implement a contact form using Bootstrap utility and component classes. All custom CSS rules have been removed in favor of importing Bootstrap in `styles.css`

Form created by Dekartmc and imported from :https://www.creative-tim.com/twcomponents/component/responsive-contact-form**


---

## Changes Summary

- **Classes Added**
  - `custom-wrapper`, `card`, `shadow`, `rounded`, `card-body`, `text-uppercase`, `mb-4`
  - Form utilities: `row g-3`, input grid classes (`col-md-6`, `col-12`, `col-12 col-md-4`)
  - Layout utilities: `container vh-100 d-flex justify-content-center align-items-center`, `row w-100`
  - Column classes: `col-lg-8 mb-4`, `col-lg-4`
  - Icon utilities: `d-flex mb-3 w-75`, `fs-3`, `me-3`, heading utilities: `h5`, `mb-1`, `mb-0`

- **Classes Removed**
  - Custom wrappers: `bg-white p-4`, `contact-card`
  - Typography: `fw-bold`, `display-5`
  - Text styling classes: `text-secondary fw-light`, `card-title`, `card-text`

---

## HTML Fragment (no head)


<!--Contact form-->
    <section class="contact-section custom-wrapper">
        <div class="container vh-100 d-flex justify-content-center align-items-center">
          <div class="row w-100">
      
            <!-- Form Column -->
            <div class="col-lg-8 mb-4">
              <div class="card shadow rounded">
                <div class="card-body">
                  <h1 class="text-uppercase mb-4">Send us a<br/>message</h1>
                  <form class="row g-3">
                    <div class="col-md-6">
                      <input type="text" class="form-control" placeholder="First Name*" />
                    </div>
                    <div class="col-md-6">
                      <input type="text" class="form-control" placeholder="Last Name*" />
                    </div>
                    <div class="col-md-6">
                      <input type="email" class="form-control" placeholder="Email*" />
                    </div>
                    <div class="col-md-6">
                      <input type="tel" class="form-control" placeholder="Phone*" />
                    </div>
                    <div class="col-12">
                      <textarea class="form-control" rows="6" placeholder="Message*"></textarea>
                    </div>
                    <div class="col-12 col-md-4">
                      <button type="submit" class="btn btn-primary w-100 text-uppercase">Send Message</button>
                    </div>
                  </form>
                </div>
              </div>
            </div>
      
            <!-- Contact Info Card -->
            <div class="col-lg-4">
              <div class="card shadow rounded">
                <div class="card-body">
                  <h2 class="text-uppercase mb-3">Drop in our location:</h2>
                  <p class="mb-4">
                    
                  </p>
      
                  <div class="d-flex mb-3 w-75">
                    <div>
                      <h3 class="h5 mb-1">We are available to talk about your party, Monday to Friday, 8 am to 4pm:</h3>
                      <p class="mb-0">
                        <i class="fas fa-map-marker-alt fs-3 me-3"></i>
                        23 Darling House, Faryland Village,<br/>
                        East Wonderland, 12MY XXUP,<br/>
                        Edwyne - Summer Kingdom
                      </p>
                    </div>
                  </div>
      
                  <div class="d-flex mb-3 w-75">
                    <i class="fas fa-phone-alt fs-4 me-3"></i>
                    <div>
                      <h3 class="h5 mb-1">Call Us</h3>
                      <p class="mb-0">Tel: 01234500000</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
      
          </div>
        </div>
      </section>

            <!--Footer-->
          <section>
            <footer class="footer">
              <div class="footer-container">
                <!-- Contact Link -->
                <div class="footer-contact">
                  <img
            src="assets/images/cake-logo.png"
            alt="Logo"
            class="logo-img me-2"
              />  
              <div class="footer-contact contact-link">
               <a href="contact.html" class="btn btn-outline-light footer-contact-btn">Contact us</a>
                </div>
                
            
                <!-- Social Links -->
                <div class="footer-social social-link">
                  <a href="https://facebook.com/yourpage" aria-label="Facebook">
                    <i class="fa-brands fa-facebook"></i>
                  </a>
                  <a href="https://twitter.com/yourprofile" aria-label="Twitter">
                    <i class="fa-brands fa-twitter"></i>
                  </a>
                  <a href="https://instagram.com/yourprofile" aria-label="Instagram">
                    <i class="fa-brands fa-instagram"></i>
                  </a>
                </div>
                
                <!-- Rights Reserved -->
                <div class="footer-copy">
                  &copy; 2025 Cake,Confetti and Fun. All rights reserved.
                </div>
              </div>
            </footer>
          </section>
              <!-- Bootstrap JS -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
  </body>
</html>
```



```

## Resources
- [Bootstrap 5 Documentation](https://getbootstrap.com/docs/5.0/layout/flex/)  
- [Font Awesome 6](https://fontawesome.com/)  
- Google Fonts: [Halant](https://fonts.google.com/specimen/Halant), [Hachi Maru Pop](https://fonts.google.com/specimen/Hachi+Maru+Pop)
- Contact form :https://www.creative-tim.com/twcomponents/component/responsive-contact-form - created by Dekartmc

## Version History and Commit Highlights

* **Apr 27, 2025** – Swapped hero image for video background; refined media queries.
* **Apr 26, 2025** – Improved hero padding; removed hero button; updated card styling.
* **Apr 25, 2025** – Applied Bootstrap grid; added sticky navbar; initial hero design.
* **Apr 23, 2025** – Integrated Google Fonts; defined CSS variables; updated README.
* **Apr 22, 2025** – Created core HTML and README; configured navbar and layout.
* **Apr 28, 2025** - Footer Section and design + contact page html only, without edits
* **Apt 39 ,2025** - Styled and added content to contact page/form


## Future Enhancements


* Develop pages for each card (About, Services, Special Touch, Contact) and link via card buttons.
* Implement a contact form with client and server validation.
* Add a Bootstrap modal for quick quotes or newsletter signup.
* Conduct accessibility audits (ARIA roles, keyboard focus, contrast).
 
 ## How to use this work

* Fork or clone the repository to experiment with layouts, styles, and assets.
* Customize CSS variables or replace Google Fonts to match your brand.
* Deploy live via GitHub Pages at `https://YourUserName.github.io/cake-confetti-and-fun`.

---

### Acknowledgements


* Media assets (logo, illustrations, posters) designed using Canva - https://www.canva.com

* Typography supplied by Google Fonts - https://fonts.google.com

* Frameworks and libraries courtesy of Bootstrap 5 - https://getbootstrap.com/ and the Bootstrap JS bundle - https://getbootstrap.com/docs/5.0/getting-started/javascript/

* Contact form :https://www.creative-tim.com/twcomponents/component/responsive-contact-form - created by Dekartmc

* Version control managed with Git - https://git-scm.com and GitHub - https://github.com/

