SASS/LESS/STYLUS are nothing but an extensions to CSS that adds power to the basic language.

It allows you to use:
  - variables
  - nested rules
  - mixins
  - inline imports
  - and few more exciting things

CSS pre-processor helps to keep stylesheets well-organized and make use of small stylesheets to work and run quickly.

###  Features of CSS extension
Nested Rules:
> It helps to avoid the repetition of parent selectors.

```sh
.container {
    max-width: 1240px;
    width: 100%;
    margin: 10px auto;
    
    .wrapper {
        background-color: #fff; 
    }
}
```

Referencing Parent Selectors:
> & will be replaced with the parent selector as it appears in the CSS.
```sh
a {
    text-decoration: none;
    &:hover {
        text-decoration: underline;
    }
}
```

Using namespaces in CSS:
> For eg., font-family, font-size, font-weight are all in font namespace. CSS pre-processor gives you the shortcut
```sh
.para {
    font: {
        family: sans-serif;
        size: 30em;
        weight: bold;
    }
}
```
Resulted output will be:
```sh
.para {
  font-family: fantasy;
  font-size: 30em;
  font-weight: bold; 
}
```
Or you can also do somtething like this:
```sh
.para {
    font: 20px/24px fantasy {
        weight: bold;
    }
}
```
Resulted output will be:
```sh
.para {
    font: 20px/24px fantasy;
    font-weight: bold;
}
```

Variables:
> Variables in SASS/SCSS($)
```sh
$width: 5em;

.wrapper {
    width: $width;
}
```

> Variables in LESS(@)
```sh
@width: 80em;

.wrapper {
  width: @width;
}
```
>Variables are only available within the level of nested selectors where they’re defined. If they’re defined outside of any nested selectors, they’re available everywhere. They can also be defined with the !global flag, in which case they’re also available everywhere.

```sh
#main {
  $width: 5em !global;
  width: $width;
}

#sidebar {
  width: $width;
}
```
