# Markdown as HTML

> Testing a Markdown document as a *static single page* site

- [Markdown as HTML](#markdown-as-html)
  - [About](#about)
  - [Tests](#tests)
    - [Progressive Web Application (PWA)](#progressive-web-application-pwa)
    - [Button Test](#button-test)

## About

This is a test to see how far I can push GitHub Pages and a single `Markdown`
file as a *static single page* site.

Feel free to use this site as a template for other projects.

## Tests

### Progressive Web Application (PWA)

By utilizing the [Hacker Theme](https://github.com/pages-themes/hacker), I was
able to turn this site into a
[PWA](https://www.youtube.com/watch?v=sFsRylCQblw).

To do so, I needed to create a [`mainfest.json`](manifest.json) file, differently
sized images using [this site](https://www.pwabuilder.com/imageGenerator), and
a generic service worker from
[GeeksForGeeks](https://www.geeksforgeeks.org/making-a-simple-pwa-under-5-minutes/).

To implement these files, I created a custom head file in
[`_includes/head-custom.html`](_includes/head-custom.html) to add the `link`
element to the [`mainfest.json`](manifest.json) file.
I also reimplemented the default `head` tags for the theme within this document.

Finally, I added the [`serviceworker.js`](serviceworker.js) file to this project
and the service worker script to [this](index.md) file.

### Button Test

<button type="button" onclick="alert('You clicked me!')">Click Me!</button>

<!-- Required for loading the service worker -->
<!-- https://www.geeksforgeeks.org/making-a-simple-pwa-under-5-minutes/ -->
<script>
    window.addEventListener('load', () => {
      registerSW();
    });

    // Register the Service Worker
    async function registerSW() {
      if ('serviceWorker' in navigator) {
        try {
          await navigator
                .serviceWorker
                .register('serviceworker.js');
        }
        catch (e) {
          console.log('SW registration failed');
        }
      }
    }
 </script>
