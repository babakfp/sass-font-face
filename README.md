# SASS font-face
A complit SASS/SCSS mixin to easily write css @font-face{}.

###### Sample code
```scss
@use "src/index" as ff;

@include ff.font-face((
  family:  vazir, // font-family
  folder:  vazir-enNum, // folder name that contains current font file/files.
  path:    "./fonts", // folder name that contains current font/fonts folder (default:"./<family>")
  suffixs: eot woff2 woff ttf svg, // default: woff2 woff ttf
  weights: 100 400 500 600 700 800 900
),(
  font-style: normal, // optional
  display:    block // optional
  // keep in mind the thos are wraped in a map.
));
```
note: check demo files.


###### How it works?

1. First import the mixin.
[what is @use?](http://www.sass-lang.com/documentation/at-rules/use)
```scss
@use "src/index" as ff;
```

2. Include the mixin.
[what is @mixin and @include?](http://www.sass-lang.com/documentation/at-rules/mixin)
```scss
@include ff.font-face();
```

3. Add necessary props as a map.
[what is map?](https://sass-lang.com/documentation/values/maps)
```scss
@include ff.font-face((
  family:  vazir,
  path:    "./fonts",
  suffixs: eot woff2 woff ttf svg,
  weights: 100 400 500 600 700 800 900
));
```

3. Optional props as second map.
```scss
@include ff.font-face((),(
  font-style: normal,
  display:    block
));
```

###### Props
If you replace any prop(example:font-style) with ```null```, the style for that prop not going to outputed in .css file.

###### Necessary properties
_font-family_ | _font-path_ | _font-weight/weights_ | _font-suffix/suffixs_
you can add a folder(as a key) and folder name(as a value) to the first map to change default folder name.

###### Optional props
You can add any valid css to output in each @font-face.

###### Filename spesifaction
important: your fonts name need to be one of the specific names below.
```
filename: <name>-<weight>.<suffix>
filename: <name>-100.<suffix>
filename: <name>-200.<suffix>
filename: <name>-300.<suffix>
and ...
```

###### Path
You can write the path like ```"./fonts"``` or ```"./fonts/"```. in the end, its going to work fine.
note: dont pass two slashes like:```./fonts```. it will prake the prosess.