# sass-font-face
SASS/SCSS mixin for CSS@font-face

``` font name ``` | ``` font style ``` | ``` font type ``` | ``` font weight ``` | ``` font path ```.

``` @include font-face(vazir, normal, woff2, 500, "./fonts"); ```
``` @include font-face(vazir, normal, woff2, 300 400 500 600, "./fonts"); ```
``` @include font-face(vazir, normal, woff2, null, "./fonts"); ```
``` @include font-face(vazir, null, woff2, 500, "./fonts"); ```

###### File Name Spesifaction
font file name need to be in this order: 
```font-family```-```font-weight```.```font-type``` => ```sans-bold.woff```.
```sans-thin.woff``` 100
```sans-light.woff``` 300
```sans.woff``` 400
```sans-medium.woff``` 500
```sans-bold.woff``` 600
```sans-extra-bold.woff``` 700


###### Props
If you replace any prop (like font style) with ```null```, the styles for that prop not going to outputed in .css file.


###### Fonts Path
You can write it like ```./fonts``` or ```./fonts/```. in the end, its going to be translated to ```./fonts/```.
note: dont pass two slashes like:```./fonts```. it will prake the prosess.


###### Explanations
If you have a font with 2 styles, you can pass a list variable or the list values like```300 400 500 600``` in props.

