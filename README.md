# LKT Theme

The semantic themes tool!

This package can help handling most common and reusable theme props and in a sharable and collaborative way with the
rest of the team.

## Colors

### Available colors

| Color     | Use case                                                                     |
|-----------|------------------------------------------------------------------------------|
| primary   | This is your brand main color                                                |
| secondary | If your brand has a secondary color, this is the place                       |
| info      | Give the user some info                                                      |
| warning   | Warn the user                                                                |
| success   | Everything is ok                                                             |
| danger    | Something bad could happen                                                   |
| alert     | Something bad happened                                                       |
| target    | Goals                                                                        |
| focus     | Focus inputs                                                                 |
| notice    | Another informative color                                                    |
| important | For important stuff                                                          |
| text      | Main text color. I recommend using this alternative color as main background |
| gray      | Your grayscale colors                                                        |

### Available Colors Modifiers

| Modifiers | Use case                                                                       |
|-----------|--------------------------------------------------------------------------------|
| contrast  | Contrast color. For example, the default background for this color in a button |
| light     | A light version of the color                                                   |
| lighter   | A lighter version of the color                                                 |
| dark      | A dark version of the color                                                    |
| darker    | A darker version of the color                                                  |

### Methods

Each color has a configuration mixin with this structure:

```scss
lkt-theme.set-<colorName>-color(color, contrast)

// For example:

lkt-theme.set-secondary-color(...)
lkt-theme.set-alert-color(...)
lkt-theme.set-warning-color(...)
...
```



### Colors configuration

```scss
@use "node_modules/lkt-theme/lkt-theme";

@include lkt-theme.set-primary-color(#ff0000, #ffffff);
@include lkt-theme.set-secondary-color(blue, green);
```

### Colors usage

```scss
@use "node_modules/lkt-theme/lkt-theme";

body {
  color: lkt-theme.$text-color;
  background: lkt-theme.$text-color-contrast;
}

button.success {
  color: lkt-theme.$success-color;
  background: lkt-theme.$success-color-contrast;
}

button.success-light {
  color: lkt-theme.$success-color-light;
  background: lkt-theme.$success-color-light-contrast;
}
```

### Advanced colors usage

There is a function named `get-color-map` which will return a map of maps with all the colors. The map structure it's like following:

```
(
    name1: (color: name1-color, contrast: name1-color),
    name2: (color: name2-color, contrast: name2-color),
    ...
    nameN: (color: nameN-color, contrast: nameN-color),
)
```

For example:

```scss
@include lkt-theme.set-primary-color(#ff0000, #ffffff);
@include lkt-theme.set-primary-color-dark(#ff0022, #ffffff);
@include lkt-theme.set-gray-color(#cccccc, #ffffff);

$colors: lkt-theme.get-color-map();

// $colors content:

(
    primary: (color: #ff0000, contrast: #ffffff),
    primary-dark: (color: #ff0022, contrast: #ffffff),
    primary-gray: (color: #cccccc, contrast: #ffffff),
)
```

This is useful to iterate and generate modifiers to existing CSS selectors:

```scss
.item {
  @each $code, $palette in $colors {
    $color: map-get($palette, color);
    $contrast: map-get($palette, contrast);
      
    &.#{$code} {
      color: $color;
      background: $contrast;
    }
  }
}

// Will generate the following output:
.item.primary {
  color: #ff0000;
  background: #ffffff; }
.item.primary-dark {
  color: #ff0022;
  background: #ffffff; }
.item.gray {
  color: #cccccc;
  background: #ff0000; }
```

## Border radius

### Available border radius

| Color     | Use case                               |
|-----------|----------------------------------------|
| primary   | The main border radius in your project |
| secondary | Additional border radius               |
| tertiary  | Another one just in case               |

### Methods

There is a mixin to configure all three border radius

```scss
lkt-theme.set-border-radius(primary, secondary, tertiary)
```

### Border radius configuration

```scss
@use "node_modules/lkt-theme/lkt-theme";

@include lkt-theme.set-border-radius(1px, 2px, 4px);
```

### Border radius usage

```scss
@use "node_modules/lkt-theme/lkt-theme";


button.success {
  border-radius: lkt-theme.$primary-border-radius;
}
```

## Transitions

### Available transitions

| Color     | Use case                            |
|-----------|-------------------------------------|
| primary   | The main transition in your project |
| secondary | Additional transition               |
| tertiary  | Another one just in case            |

### Methods

There is a mixin to configure all three transitions

```scss
lkt-theme.set-transition(primary, secondary, tertiary)
```

### Transition configuration

```scss
@use "node_modules/lkt-theme/lkt-theme";

@include lkt-theme.set-transition(200ms all linear, false, 5s color linear);
```

### Border transition

```scss
@use "node_modules/lkt-theme/lkt-theme";


button.success {
  transition: lkt-theme.$primary-transition;
}
```

## Font sizes

### Available font sizes

| Color     | Use case                           |
|-----------|------------------------------------|
| primary   | The main font-size in your project |
| secondary | Additional font-size               |
| tertiary  | Another one just in case           |

### Methods

There is a mixin to configure all three font-sizes

```scss
lkt-theme.set-font-size(primary, secondary, tertiary)
```

### Font-size configuration

```scss
@use "node_modules/lkt-theme/lkt-theme";

@include lkt-theme.set-font-size(16px, 20px, 17px); // Sample
```

### Font-size usage

```scss
@use "node_modules/lkt-theme/lkt-theme";


button.success {
  font-size: lkt-theme.$primary-font-size;
}
```

## Font families

### Available font families

| Color            | Use case                                           |
|------------------|----------------------------------------------------|
| primary-header   | The main font-family (for headers) in your project |
| secondary-header | Additional font-family (for headers)               |
| tertiary-header  | Another one just in case (for headers)             |
| primary-text     | The main font-family in your project (for text)    |
| secondary-text   | Additional font-family (for text)                  |
| tertiary-text    | Another one just in case (for text)                |
| primary-button   | The main font-family in your project (for buttons) |
| secondary-button | Additional font-family (for buttons)               |
| tertiary-button  | Another one just in case (for buttons)             |

### Methods

There are three mixins to configure all font families

```scss
lkt-theme.set-header-font-family(primary, secondary, tertiary)
lkt-theme.set-text-font-family(primary, secondary, tertiary)
lkt-theme.set-button-font-family(primary, secondary, tertiary)
```

### Font-family configuration

```scss
@use "node_modules/lkt-theme/lkt-theme";

@include lkt-theme.set-button-font-family(Arial); // Sample
```

### Font-family usage

```scss
@use "node_modules/lkt-theme/lkt-theme";


button.success {
  font-family: lkt-theme.$primary-button-font-family;
}
```