# Example of using sasss in html using node

## Installation

```
npm install
```

## How it works?

Sass for handling styles. A library is responsible for converting the sass code to css.

The scripts are detailed in **package.json**  
(spoiler: You can use it runing this:)

```
npm run watch
```

# Some things about Sass

To get the full documentation of sass, go to [sass-lang.com/guide](https://sass-lang.com/guide)

### Variables

Its possible create and use variables in sass.

```scss
$color: #f00;
$size: 10px;

body {
  color: $color;
  font-size: $size;
}
```

### Nesting

You can nest some selectors inside others to make your code more readable.

```scss
.container {
  .item {
    color: #f00;
  }
}
```

### Mixins

Mixins are a way to reuse styles. You can define a set of styles and then use them in multiple places.

```scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
  -moz-border-radius: $radius;
  -ms-border-radius: $radius;
  border-radius: $radius;
}
```

### Partials

Partials are parts of code, commonly in files with extension scss and with names that start with underscore, for example: _\_variables.scss_. Importing the partials is the equal to copy and paste the code in the file that you are importing.

```scss
@import 'variables';
```

### Modules

Very similar to partials, but with the difference that the modules are imported using the **@use** directive and you use only what you need from the module.

```scss
@use 'base';

.inverse {
  background-color: base.$primary-color;
  color: white;
}
```

### Extend

With @extends you can take properties from one selector and apply them to another.

```scss
%button {
  display: inline-block;
  padding: 0.5em 1em;
  text-decoration: none;
  border-radius: 3px;
}

.button {
  @extend %button;
  background-color: #f00;
  color: white;
}
```

### Operators

You can use math operators like `+`, `-`, `*`, `/`, `%` and `==`.

```scss
@use 'sass:math';

.container {
  display: flex;
}

article[role='main'] {
  width: math.div(600px, 960px) * 100%;
}

aside[role='complementary'] {
  width: math.div(300px, 960px) * 100%;
  margin-left: auto;
}
```
