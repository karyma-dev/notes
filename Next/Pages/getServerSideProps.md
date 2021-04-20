# getServerSideProps

- Will pre-render the page on each request using data returned by getServerSideProps
- Only runs in the server side

Basic Example

```js
function Page({ data }) {
  // Render data...
}

// This gets called on every request
export async function getServerSideProps() {
  // Fetch data from external API
  const res = await fetch(`https://.../data`);
  const data = await res.json();

  // Pass data to the page via props
  return { props: { data } };
}

export default Page;
```

Optional and Required Keys and Return Values

```js
export async function getServerSideProps(context) {
  context = {
    params, // contains the route parameters
    req, // HTTP IncomingMessage Object
    res, // HTTP response Object
    query, // An object representing the query string
    preview, // Toggles preview mode
    previewData, // The preview data set by setPreviewData
    resolvedUrl, // A normalized version of the request URL that strips the _next/data prefix for client transitions and includes original query values
    locale, // contains the active locale if enabled,
    locales, // contains all supported locales if enabled,
    defaultLocale, // contains the configured default locale
  };

  return {
    props, // required object with the props that will be received by the page component
    notFound, // optional boolean value that allow the page to return a 404 status and page
    redirect, // optional { destination: string, permanent: boolean } value to allow redirecting to internal and external resources. Can use statusCode instead of permanent if you want custom status code for older HTTP Clients to properly redirect.
  };
}
```

notfound example

```js
export async function getServerSideProps(context) {
  const res = await fetch(`https://...`);
  const data = await res.json();

  if (!data) {
    return {
      notFound: true,
    };
  }

  return {
    props: {}, // will be passed to the page component as props
  };
}
```

Redirect Example

```js
export async function getServerSideProps(context) {
  const res = await fetch(`https://.../data`);
  const data = await res.json();

  if (!data) {
    return {
      redirect: {
        destination: '/',
        permanent: false,
      },
    };
  }

  return {
    props: {}, // will be passed to the page component as props
  };
}
```
