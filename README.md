# SASS font-face
A complit SASS/SCSS mixin to easily write css @font-face{}.



###### Sample code
Check the demo file for a full explanation.
**[demo file](https://github.com/babakfp/sass-font-face/blob/master/demo.scss)**



###### How it works?

1. First import the mixin.
[what is @use?](http://www.sass-lang.com/documentation/at-rules/use)
```scss
@use "src/index" as *;
```

2. Include the mixin.
[what is @mixin and @include?](http://www.sass-lang.com/documentation/at-rules/mixin)
```scss
@include font-face();
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



###### Necessary properties
(family) and (path) and (suffixs) is necessary no include in the mixin.



###### Optional properties
You can add any valid css, to be output in each @font-face.



###### Filename spesifaction
Important: Your fonts name needs to be one of the specified. You can't set font-weight as a name to font file name or (suffixes) value.
```
filename: <name>-<weight>.<suffix>
filename: <name>-100.<suffix>
filename: <name>-200.<suffix>
filename: <name>-300.<suffix>
and ...
```



###### font-face Src property value
```scss
src: url((path)/(folder)/(family)-(weight).(suffix)
```