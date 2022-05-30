# Markdown as HTML

> Testing a Markdown document as a *static single page* site

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
