# SASS/SCSS

## Basics

### Store data (create variables)

```scss
// Add a dollar sign before variable name
$color: blue
$p-font-size: 12px

p {
  color: $color;
  font-size: $p-font-size;
}
```

### Nest child elements inside the parent element

```scss
// Nesting elements using SCSS
nav {
  background-color: black;

  ul {
    list-style: none;

    li {
      display: flex;
    }
  }
}
```

### Mixin

> It's something similar to a "function" in JavaScript

```scss
// Create the mixin ("Function")
@mixin box-shadow($x, $y, $blur, $c) {
  -webkit-box-shadow: $x $y $blur $c;
  -moz-box-shadow: $x $y $blur $c;
  -ms-box-shadow: $x $y $blur $c;
  box-shadow: $x $y $blur $c;
}

// Call the mixin with @include
div {
  @include box-shadow(0px, 0px, 4px, #fff);
}
```

## Advanced

### if, else if, else

```scss
@mixin text-effect($val) {
  @if $val == danger {
    color: red;
  } @else if $val == alert {
    color: yellow;
  } @else if $val == success {
    color: green;
  } @else {
    color: black;
  }
}
```

### for loop

```scss
// the end number is excluded in the counting
@for $i from 1 through 12 {
  .col-#{$i} {
    width: 100%/12 * $i;
  }
}
```

### each

> similar to map in javascript

```scss
$colors: (
  color1: blue,
  color2: red,
  color3: green,
);

@each $key, $color in $colors {
  .#{$color}-text {
    color: $color;
  }
}

// Note that the $key variable is needed to reference the keys in the map.
// Otherwise, the compiled CSS would have color1, color2... in it
```
