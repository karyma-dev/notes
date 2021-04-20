# getStaticPaths

- Only runs at build time on Server-Side
- Only allowed in page components
- Usually used with getStaticProps
- Must return a paths and a fallback
- Cannot be used with getServerSideProps
- In development mode getStaticPaths will be called on every request

```js
function Post({ post }) {
  // Render post...
}

export async function getStaticPaths() {
  // Call an external API endpoint to get posts
  const res = await fetch('https://.../posts');
  const posts = await res.json();

  // Get the paths we want to pre-render based on posts
  const paths = posts.map((post) => ({
    params: { id: post.id },
  }));

  // We'll pre-render only these paths at build time.
  // { fallback: false } means other routes should 404.
  return { paths, fallback: false };
}

// This also gets called at build time
export async function getStaticProps({ params }) {
  // params contains the post `id`.
  // If the route is like /posts/1, then params.id is 1
  const res = await fetch(`https://.../posts/${params.id}`);
  const post = await res.json();

  // Pass post data to the page via props
  return { props: { post } };
}

export default Post;
```

## Fallback

- fallback: false
  - any paths not returned by getStaticPaths will result in a 404 page
- fallback: true

  - paths that have not been generated at build time will not result in a 404 page
  - example would be an e-commerce site may take long time to load to pre-render all products, so you may statically generate a small subset of pages and use fallback: true for the rest

  ```js
  // pages/posts/[id].js
  import { useRouter } from 'next/router';

  function Post({ post }) {
    const router = useRouter();

    // If the page is not yet generated, this will be displayed
    // initially until getStaticProps() finishes running
    if (router.isFallback) {
      return <div>Loading...</div>;
    }

    // Render post...
  }

  // This function gets called at build time
  export async function getStaticPaths() {
    return {
      // Only `/posts/1` and `/posts/2` are generated at build time
      paths: [{ params: { id: '1' } }, { params: { id: '2' } }],
      // Enable statically generating additional pages
      // For example: `/posts/3`
      fallback: true,
    };
  }

  // This also gets called at build time
  export async function getStaticProps({ params }) {
    // params contains the post `id`.
    // If the route is like /posts/1, then params.id is 1
    const res = await fetch(`https://.../posts/${params.id}`);
    const post = await res.json();

    // Pass post data to the page via props
    return {
      props: { post },
      // Re-generate the post at most once per second
      // if a request comes in
      revalidate: 1,
    };
  }

  export default Post;
  ```
