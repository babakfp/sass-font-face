# SASS Font Face `@font-face`

Write 5 lines instead of 300 lines. You can you a sass mixin to do the all work for you.

## Example

```scss
@use "./sass-font-face" as *;

@include font-face((
  font-family: "Sans Serif",
	// Order doesn't matter.
  suffixes: eot woff2 woff ttf svg,
  weights: (
    thin 100,
    extralight 200,
    light 300,
    regular 400,
    medium 500,
    semibold 600,
    bold 700,
    extrabold 800,
    black 900,
  ),
	// <weight> and <suffix> will be replaced by the mixin.
  url: "./fonts/sans-serif-<weight>.<suffix>",
	// You don't need to add font-style, it will be handled by the mixin based on, is there `italic` substring in the url.
	// Your custom css properties here:
  display: block,
));
```
