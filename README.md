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

import useNProgress from 'next-use-nprogress';

export default function App({ Component, pageProps }) {
  useNProgress({
    // your configurations goes here.
  });

  // your can customize your _app here.
  return <Component {...pageProps} />;
}
```

## Configuration

```ts
interface NProgressOptions {
  // Changes the minimum percentage used upon starting.
  minimum: number;
  // You can change the markup using `template`. To keep the progress bar working, keep an element with `role='bar'` in there.
  template: string;
  // Adjust animation settings using easing (a CSS easing string) and speed (in ms).
  easing: string;
  speed: number;
  // Turn off the automatic incrementing behavior by setting this to `false`.
  trickle: boolean;
  // Adjust how often to trickle/increment, in ms.
  trickleSpeed: number;
  // Turn off loading spinner by setting it to false.
  showSpinner: boolean;
  // Specify this to change the parent container.
  parent: string;
  positionUsing: string;
  barSelector: string;
  spinnerSelector: string;
}

const defaultNProgressOptions: NProgressOptions = {
  minimum: 0.1,
  template:
    '<div class="bar" role="bar"><div class="peg"></div></div><div class="spinner" role="spinner"><div class="spinner-icon"></div></div>',
  easing: 'linear',
  speed: 200,
  trickle: true,
  trickleSpeed: 200,
  showSpinner: true,
  parent: 'body',
  positionUsing: '',
  barSelector: '[role="bar"]',
  spinnerSelector: '[role="spinner"]',
};
```

## Limitations

- Cannot import Global CSS from `node_modules` [see this](https://github.com/vercel/next.js/discussions/27953).

## TODO

- Add demo page
- Add feature with the component type (`<NProgress {...config} />`)
