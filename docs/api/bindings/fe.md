# fe

Fe is a convenient replacement for React's [createElement](https://reactjs.org/docs/react-api.html#createelement).<br>
It is heavily inspired by [glam](https://github.com/threepointone/glam) and basically works the same.

Fe directly renders style objects, which are passed to the `css` prop of JSX components by using [FelaComponent](FelaComponent.md) internally.

## Usage
Fe is especially made to replace `createElement` when using JSX.<br>
The best way to achieve that, is to use the `/* @jsx fe */` override.

```javascript
/* @jsx fe */
import { fe } from 'react-fela'

/* @jsx fe */
import { fe } from 'preact-fela'

/* @jsx fe */
import { fe } from 'inferno-fela'
```

## Example
```javascript
const style = {
  color: 'red',
  ':hover': {
    color: 'blue'
  }
}

// => <div class="a b">Hello</div>
const Fragment = () => (
  <div css={style}>
    Hello
  </div>
)
```

#### Third-Party Classes

We can also pass a custom `className` that is automatically prepended.

```javascript
const style = {
  color: 'red',
  ':hover': {
    color: 'blue'
  }
}

// => <div class="custom-class a b">Hello</div>
const Fragment = () => (
  <div css={style} className="custom-class">
    Hello
  </div>
)
```