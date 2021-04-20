# Typescript

## GetStaticProps

`import { GetStaticProps } from 'next'`

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

## GetStaticPaths

`import { GetStaticPaths } from 'next'`

## GetServerSideProps

`import { GetServerSideProps } from 'next'`

```ts
import { InferGetServerSidePropsType } from 'next'

type Data = { ... }

export const getServerSideProps = async () => {
  const res = await fetch('https://.../data')
  const data: Data = await res.json()

  return {
    props: {
      data,
    },
  }
}

function Page({ data }: InferGetServerSidePropsType<typeof getServerSideProps>) {
  // will resolve posts to type Data
}

export default Page
```
