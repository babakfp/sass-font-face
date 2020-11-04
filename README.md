# SASS font-face
A complete SASS mixin to easily write CSS `@font-face{}`.



###### Sample code
Check the demo file for a full explanation.
**[demo file](https://github.com/babakfp/sass-font-face/blob/master/demo.scss)**



###### How it works?

1. Import the scss file into your project.
**[@use](http://www.sass-lang.com/documentation/at-rules/use)**
```scss
@use "src/index" as *;
```

2. Use the mixin.
**[@mixin](http://www.sass-lang.com/documentation/at-rules/mixin)**
```scss
@include font-face();
```

3. Add necessary properties as a map.
**[map](https://sass-lang.com/documentation/values/maps)**
```scss
@include ff.font-face((
  family:  vazir,
  path:    "./fonts",
  suffixs: eot woff2 woff ttf svg,
  weights: 100 400 500 600 700 800 900
));
```

3. Optional properties as a second map.
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



###### font-face src
```scss
src: url((path)/(folder)/(family)-(weight).(suffix)
```