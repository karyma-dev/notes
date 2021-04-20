# getStaticProps

- You can import modules in top-level scope for use in getStaticProps. Imports used in getStaticProps will not be bundled for the client-side
  - This means you can write server-side code directly in getStaticProps. This includes reading from the filesystem or a database
- Redirecting at build-time is currently not allowed and if the redirects are known at build-time they should be added in next.config.js
- You should not use fetch() to call an API route in getStaticProps. Instead, directly import the logic used inside your API route. You may need to slightly refactor your code for this approach.
- Can only be used in a page component
- In development mode getStaticProps will be called on every request, to by pass this you must use preview mode

Basic example of **getStaticProps**

```js
function Blog({ posts }) {
  // Render posts...
}

// This function gets called at build time
export async function getStaticProps() {
  // Call an external API endpoint to get posts
  const res = await fetch('https://.../posts');
  const posts = await res.json();

  // By returning { props: { posts } }, the Blog component
  // will receive `posts` as a prop at build time
  return {
    props: {
      posts,
    },
  };
}

export default Blog;
```

Optional and Required Keys and Return Values

```js
export async function getStaticProps(context) {
  // Context is an object containing the following keys
  Context = {
    params, // Contains the route parameters for pages using dynamic routes, usually used with getStaticPaths
    preview, // true if page is in preview mode and undefined otherwise
    previewData, // contains the preview data set by setPreviewData
    locale, // contains the active locale if enabled
    locales, // contains all supported locales if enabled
    defaultLocale, // contains the configured default locale if enabled
  };

  return {
    props: { data }, // A required object with the props that will be received by the page component. It should be a serialized object
    revalidate, // An optional amount in seconds after which a page re-generation can occur.
    notFound, // An optional boolean value to allow the page to return a 404 status and page.
    redirect, // An optional redirect value to allow redirecting to internal and external resources. It should match the shape of { destination: string, permanent: boolean }. In some rare cases, you might need to assign a custom status code for older HTTP Clients to properly redirect. In these cases, you can use the statusCode property instead of the permanent property, but not both.
  };
}
```

Example of **notFound**

```js
export async function getStaticProps(context) {
  const res = await fetch(`https://.../data`);
  const data = await res.json();

  if (!data) {
    return {
      notFound: true,
    };
  }

  return {
    props: { data }, // will be passed to the page component as props
  };
}
```

Example of **redirect**

```js
export async function getStaticProps(context) {
  const res = await fetch(`https://...`);
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
    props: { data }, // will be passed to the page component as props
  };
}
```

## Incremental Static Regeneration

- Allows you to update existing pages by re-rendering them in the background as traffic comes in
- No spikes in latency. Pages are served consistently fast
- Pages never go offline. If the background page re-generation fails, the old page remains unaltered
- Low database and backend load. Pages are re-computed at most once concurrently

```js
function Blog({ posts }) {
  return (
    <ul>
      {posts.map((post) => (
        <li>{post.title}</li>
      ))}
    </ul>
  );
}

// This function gets called at build time on server-side.
// It may be called again, on a serverless function, if
// revalidation is enabled and a new request comes in
export async function getStaticProps() {
  const res = await fetch('https://.../posts');
  const posts = await res.json();

  return {
    props: {
      posts,
    },
    // Next.js will attempt to re-generate the page:
    // - When a request comes in
    // - At most once every second
    revalidate: 1, // In seconds
  };
}

export default Blog;
```

## Reading Files

```js
import { promises as fs } from 'fs';
import path from 'path';

// posts will be populated at build time by getStaticProps()
function Blog({ posts }) {
  return (
    <ul>
      {posts.map((post) => (
        <li>
          <h3>{post.filename}</h3>
          <p>{post.content}</p>
        </li>
      ))}
    </ul>
  );
}

// This function gets called at build time on server-side.
// It won't be called on client-side, so you can even do
// direct database queries. See the "Technical details" section.
export async function getStaticProps() {
  const postsDirectory = path.join(process.cwd(), 'posts');
  const filenames = await fs.readdir(postsDirectory);

  const posts = filenames.map(async (filename) => {
    const filePath = path.join(postsDirectory, filename);
    const fileContents = await fs.readFile(filePath, 'utf8');

    // Generally you would parse/transform the contents
    // For example you can transform markdown to HTML here

    return {
      filename,
      content: fileContents,
    };
  });
  // By returning { props: { posts } }, the Blog component
  // will receive `posts` as a prop at build time
  return {
    props: {
      posts: await Promise.all(posts),
    },
  };
}

export default Blog;
```
