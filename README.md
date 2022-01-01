# Iulia's Notes

It is based on customized Minimal Mistakes. Visit it here <a href="http://iulitaro.github.io/notes/" target="_blank"> http://iulitaro.github.io/notes/ </a>

Here is a list of customizations that I have made to the Minimal Mistakes Jekyll static site generator:

<h2>Style</h2>

The main changes are in main.scss where I define:

* two new themes: sakura and rain
* new variables to handle the theme_name to be used
* define the basic colors to be used throughout the website //basics
* replaced all hardcoded colors with the colors in basics 

Basically, only a few variables need to be defined at the top, to have all the website look and feel changed.

**Regenerate style**

In the bash console type:


```
npm run scss
```


```
//$theme_name              : rain;
$theme_name              : sakura;
//$theme_name              	: default;


//basics
$gray                       : #7a8288;
$theme-dark-color           : #000;      
$theme-light-color          : #fff;
$primary-color              : #7a8288; //link
$success-color              : #62c462;
$warning-color              : #f89406;
$danger-color               : #ee5f5b;
$info-color                 : #52adc8;

@if $theme_name == 'sakura' {
	$gray  					   : #0E090D; //font color
	$theme-dark-color          : #5C306B;  
	$theme-light-color         : #FFF7F4;	//background
	$primary-color             : #D42F4D;	//navigation top
	$info-color                : #E4C7CC; //links color in text
}

//pallete inspiration: http://www.colourlovers.com/palette/2864152/Its_Raining_Flowers
@if $theme_name == 'rain' {
	$gray  					   : #41245C; //font color
	$theme-dark-color          : #B95A84;  
	$theme-light-color         : #fff;	//background
	$primary-color             : #6B316C;	//navigation top
	$info-color                : #D69DAE; //links color in text
}
```

<h2>Social</h2>

* Included the AddThis social sharing instead of custom sharing

<a href="http://www.addthis.com/" target="_blank">AddThis</a> is great. It allows to include sharing sidebars, while also track the sharings.
It is based on customized Minimal Mistakes. Visit it here <a href="http://iulia-codes.github.io/notes/"> http://iulia-codes.github.io/notes/ </a>

[![Minimal Mistakes live preview][2]][1]

[1]: https://mmistakes.github.io/minimal-mistakes/
[2]: https://cloud.githubusercontent.com/assets/1376749/14562643/d83b96c0-02eb-11e6-98d6-473fbfd3bff6.jpg (live preview)

