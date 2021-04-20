# Typescript

**getStaticProps**

```ts
import { GetStaticProps } from 'next';

export const getStaticProps: GetStaticProps = async (context) => {
  //
};
```

```ts
import { InferGetStaticPropsType } from 'next';

type Post = {
  author: string;
  content: string;
};

export const getStaticProps = async () => {
  const res = await fetch('https://.../posts');
  const posts: Post[] = await res.json();

  return {
    props: {
      posts,
    },
  };
};

function Blog({ posts }: InferGetStaticPropsType<typeof getStaticProps>) {
  // will resolve posts to type Post[]
}

export default Blog;
```
