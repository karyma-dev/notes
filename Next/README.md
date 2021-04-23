# NextJS

## Setup

```
npx create-next-app

or

Npm install next react react-dom
```

## Features

- Automatic compilation and bundling (with webpack and babel)
- React Fast Refresh
- Static generation and server-side rendering of `./pages/`
- Static file serving. `./public/` is mapped to `/`
- NextJS creates a JSON file behind the scenes and uses that data for routing and etc to separate the client and the server
- Built-in support for environment variables
  - Stored in `.env.local` and accessed with `process.env`
  - `$` characters in `.env.local` must be escaped with `\`
  - Private to the browser by default, in order to access from browser you must prefix variable with `NEXT_PUBLIC_`. Example: `NEXT_PUBLIC_ANALYTICS_ID=abcdefghijk`
  - `.env.local` will override `.env.production` and `.env.development`

### Adding Global Styles

```js
import "../styles.css";

// This default export is required in a new `pages/_app.js` file.
export default function MyApp({ Component, pageProps }) {
  return <Component {...pageProps} />;
}
```

### CSS Modules

`[name].module.css`

### Static Files Serving

- Static files are served under the `public` folder in root directory.
- Useful for robots.txt, favicon.ico, google site verification

### Images Optimization

```js
import Image from "next/image";

function Home() {
  return (
    <>
      <h1>My Homepage</h1>
      <Image
        src="/me.png"
        alt="Picture of the author"
        width={500}
        height={500}
      />
      <p>Welcome to my homepage!</p>
    </>
  );
}

export default Home;
```

#### Domains

```js
//next.config.js
module.exports = {
  images: {
    domains: ["example.com"],
  },
};
```

#### Loader

```js
//next.config.js
module.exports = {
  images: {
    loader: "imgix", // 'imgix', 'cloudinary', 'akamai', Vercel or Default does not require config
    path: "https://example.com/myaccount/",
  },
};
```

#### Setting Device Sizes

```js
// next.config.js
module.exports = {
  images: {
    deviceSizes: [640, 750, 828, 1080, 1200, 1920, 2048, 3840],
  },
};
```

#### Setting Image Sizes

The widths should be different(usually smaller) than the widths defined in deviceSizes because the arrays are concatenated.

```js
// next.config.js
module.exports = {
  images: {
    imageSizes: [16, 32, 48, 64, 96, 128, 256, 384], // Default Image Sizes
  },
};
```
