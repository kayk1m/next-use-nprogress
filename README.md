# React hook integration of NProgress for Next.js

A simple Next.js progressbar hook using [NProgress](http://ricostacruz.com/nprogress/).

## Features

- typescript support

## How to install?

npm

```bash
npm i next-nprogress-hook nprogress
```

yarn

```bash
yarn add next-nprogress-hook nprogress
```

## Usage

In your '\_app.js'

```js
import 'nprogress/nprogress.css';

export default function App({ Component, pageProps }) {
  useNProgress({
    // your configurations goes here.
  });

  // your can customize your _app here.
  return <Component {...pageProps} />;
}
```

## Limitations

- Cannot import Global CSS from `node_modules` [see this](https://github.com/vercel/next.js/discussions/27953).

## TODO

- Add configuration options or default configs to README.md
- Add demo page
- Add feature with the component type (`<NProgress {...config} />`)
