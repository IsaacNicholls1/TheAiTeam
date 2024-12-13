# ai-team

## Project Structure

```
/C:/GitHub/TheAiTeam/
├── assets/
│   ├── css/
│   │   └── style.css
│   ├── images/
│   │   └── profile/
│   │       ├── avatar1.png
│   │       └── avatar2.png
│   └── js/
│       └── main.js
├── includes/
│   ├── navbar.html
│   └── footer.html
├── index.html
├── about.html
├── contact.html
├── games.html
├── snake.html
├── space-invaders.html
└── pac-man.html
```

## Usage

### Including the Navbar

This `JavaScript` code snippet defines a function called `loadNavbar` that is responsible for loading the `navbar` content from an external HTML file (`navbar.html`) and inserting it into an element on the current page.

``` javascript
function loadNavbar() {
    fetch('includes/navbar.html')
        .then(response => response.text())
        .then(data => {
            document.getElementById('navbar-placeholder').innerHTML = data;
            setActiveNavLink();
        });
}
```

### Setting the Active Link

The following function sets the active link in the navigation menu based on the current page.

``` javascript
function setActiveNavLink() {
    const path = window.location.pathname;
    const page = path.split("/").pop();

    const navLinks = {
        'index.html': 'nav-home',
        'about.html': 'nav-about',
        'games.html': 'nav-games',
        'contact.html': 'nav-contact'
    };

    const activeLinkId = navLinks[page];
    if (activeLinkId) {
        const activeLink = document.getElementById(activeLinkId);
        activeLink.classList.add('active');
        activeLink.setAttribute('aria-current', 'page');
    }
}
```

The loadNavbar(); function call is used to dynamically load the navbar content from an external HTML file and insert it into the current page.

```javascript
loadNavbar();
```

The following HTML snippet is used to include a placeholder for the footer content in your web pages:

```html
<footer>
  <div id="footer-placeholder"></div>
</footer>
```

