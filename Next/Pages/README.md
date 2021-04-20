# Pages

- Each page is associated with a route based on its file name.
- **Pre-rendering**
  - Generates HTML for each page in advance which may result in better seo and performance
  - Two forms of pre-rendering, you may use one or both methods for each page
    - Static Generation
      - HTML is generated at build time and reused on each request
      - Can be cached by a CDN
      - Can be used with or without data
        - `getStaticProps` page content depends on external data
        - `getStaticPaths` page paths depends on external data usually in addition to `getStaticProps`
    - Server-side rendering
      - HTML is generated on request
      - `getServerSideProps` is similar to getStaticProps but it runs on every request rather than on build time
- **Hydration**
  - Each generated HTML is associated with minimal JavaScript code necessary for that page. When a page is loaded by the browser, its JavaScript code runs and makes the page fully interactive.
- **Dynamic Routes**
  - `pages/post/[id].js`
