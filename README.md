# Scroll transition

A script that adds a class to a particular element when it's on the viewport

## Usage

1. Include the script

``` html
<script src="scroll-transition.js">
```

2. Add a attribute to the element you want to give the class to

``` html
<div scroll-transition>
```

3. When the script is loaded, the script adds a `.trans` class to the elements with the `scroll-transition` attribute. You can now style these elements, and it's children.

``` css
div.trans {
    opacity: 0;
}
```

4. When the element is in the viewport, the script adds a second class, `.start-transition` to the element.

``` css
div.trans.transition-started {
    transition: all .5s ease-in-out;
    opacity: 1;
}
```

## How it works

- The script uses the Intersection Observer api. Check support [here](https://caniuse.com/#feat=intersectionobserver)
- It only adds the class once, so the transition only triggers once
- The class triggers when the element is 33% visible. This is configurable in the file in the `config` object. 0.33 is 33%, and so on