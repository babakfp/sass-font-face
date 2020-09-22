# sass-font-face
A complit SASS/SCSS mixin to easily write css @font-face{}.


###### Demo
In demo.scss file, you can find some possible font-face' code.


###### Properties
_font name_ | _font style_ | _font weight/weights_ | _font suffix/suffixs_ | _font path_


###### How it works?
You can use a mixin named ```scss font-face()``` with the possible props to output the @font-face styles.


###### Filename spesifaction
important: your fonts name need to be one of the specific names below.
```
file: <name>-100.<suffix>
file: <name>-200.<suffix>
file: <name>-300.<suffix>
file: <name>-400.<suffix>
file: <name>-500.<suffix>
file: <name>-600.<suffix>
file: <name>-700.<suffix>
file: <name>-800.<suffix>
file: <name>-900.<suffix>
```


###### Props
If you replace any prop(example:font-style) with ```scss null```, the style for that prop not going to outputed in .css file.


###### Path
You can write the path like ```scss "./fonts"``` or ```scss "./fonts/"```. in the end, its going to work fine.
note: dont pass two slashes like:```./fonts```. it will prake the prosess.


###### Multipl weight and suffixs
```scss
@include font-face("<font name>", "<font style>", 400);
@include font-face("<font name>", "<font style>", 400, 500);
@include font-face("<font name>", "<font style>", "<font weight/weights>", woff2);
@include font-face("<font name>", "<font style>", "<font weight/weights>", eot woff2 woff ttf svg);
```


###### Full preview

```scss
// scss:
@include font-face(sans-serif);

// css:
@font-face {
  font-family: sans-serif;
  src: url("./fonts/sans-serif/sans-serif.woff2") format("woff2"), url("./fonts/sans-serif/sans-serif.woff") format("woff"), url("./fonts/sans-serif/sans-serif.ttf") format("truetype");
}
```

```scss
// scss:
@include font-face(sans-serif, italic);

// css:
@font-face {
  font-family: sans-serif;
  src: url("./fonts/sans-serif/sans-serif.woff2") format("woff2"), url("./fonts/sans-serif/sans-serif.woff") format("woff"), url("./fonts/sans-serif/sans-serif.ttf") format("truetype");
  font-style: italic;
}
```

```scss
// scss:
@include font-face(sans-serif, null, 400, woff2);

// css:
@font-face {
  font-family: sans-serif;
  src: url("./fonts/sans-serif/sans-serif-400.woff2") format("woff2");
  font-weight: 400;
}
```

```scss
// scss:
@include font-face(sans-serif, null, 400 500, woff2);

// css:
@font-face {
  font-family: sans-serif;
  src: url("./fonts/sans-serif/sans-serif-400.woff2") format("woff2");
  font-weight: 400;
}
@font-face {
  font-family: sans-serif;
  src: url("./fonts/sans-serif/sans-serif-500.woff2") format("woff2");
  font-weight: 500;
}
```

```scss
// scss:
@include font-face(sans-serif, null, null, woff2);

// css:
@font-face {
  font-family: sans-serif;
  src: url("./fonts/sans-serif/sans-serif.woff2") format("woff2");
}

```

```scss
// scss:
@include font-face(sans-serif, null, null, woff2 woff);

// css:
@font-face {
  font-family: sans-serif;
  src: url("./fonts/sans-serif/sans-serif.woff2") format("woff2"), url("./fonts/sans-serif/sans-serif.woff") format("woff");
}
```

```scss
// scss:
@include font-face(sans-serif, null, null, woff2, "./my-fonts");
// or
@include font-face(sans-serif, null, null, woff2, "./my-fonts/");

// css:
@font-face {
  font-family: sans-serif;
  src: url("./my-fonts/sans-serif/sans-serif.woff2") format("woff2");
}
```

```scss
// scss:
@include font-face(sans-serif, italic, 400 500, woff2 woff, "./my-fonts");

// css:
@font-face {
  font-family: sans-serif;
  src: url("./my-fonts/sans-serif/sans-serif-400.woff2") format("woff2"), url("./my-fonts/sans-serif/sans-serif-400.woff") format("woff");
  font-style: italic;
  font-weight: 400;
}
@font-face {
  font-family: sans-serif;
  src: url("./my-fonts/sans-serif/sans-serif-500.woff2") format("woff2"), url("./my-fonts/sans-serif/sans-serif-500.woff") format("woff");
  font-style: italic;
  font-weight: 500;
}
```