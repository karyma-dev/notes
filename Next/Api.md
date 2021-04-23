# Api Routes

- Stored in `api` folder inside `page` directory
- Bundle sizes does not increase your client side bundle size
- Same origin only by default which means no `cors`
- Predefined API routes takes precedence over dynamic API routes

Basic Example

```js
export default function handler(req, res) {
  if (req.method === "POST") {
    res.status(200).json({ name: "John Doe" });
  } else {
    // Handle any other HTTP method
  }
}
```

Dynamic Routes

```js
// api/post/[id].js
export default function handler(req, res) {
  const { pid } = req.query;
  res.end(`Post: ${pid}`);
}
```

Catch All Routes

```js
// api/post/[...params].js
export default function handler(req, res) {
  console.log(req.query); // Will always turn an array
}
```

Optional Catch All Routes

```js
// api/post/[[...params]].js
export default function handler(req, res) {
  console.log(req.query); // Will always turn an array
}
```

### Middleware

Every api route can export a `config` object to change the default configs

```js
export const config = {
  api: {
    bodyParser: {
      sizeLimit: "500kb",
    },
    // bodyParser: false,
    // externalResolver: true
  },
};
```

Adding Cors

```js
import Cors from "cors";

// Initializing the cors middleware
const cors = Cors({
  methods: ["GET", "HEAD"],
});

// Helper method to wait for a middleware to execute before continuing
// And to throw an error when an error happens in a middleware
function runMiddleware(req, res, fn) {
  return new Promise((resolve, reject) => {
    fn(req, res, (result) => {
      if (result instanceof Error) {
        return reject(result);
      }

      return resolve(result);
    });
  });
}

async function handler(req, res) {
  // Run the middleware
  await runMiddleware(req, res, cors);

  // Rest of the API logic
  res.json({ message: "Hello Everyone!" });
}

export default handler;
```

### Request

`req.cookies` - An object containing the cookies sent by the request. Defaults to {}
`req.query` - An object containing the query string. Defaults to {}
`req.body` - An object containing the body parsed by content-type, or null if no body was sent

### Response

`res.status(code)` - A function to set the status code. code must be a valid HTTP status code
`res.json(json)` - Sends a JSON response. json must be a valid JSON object
`res.send(body)` - Sends the HTTP response. body can be a string, an object or a Buffer
`res.redirect([status,] path)` - Redirects to a specified path or URL. status must be a valid HTTP status code. If not specified, status defaults to "307" "Temporary redirect".
