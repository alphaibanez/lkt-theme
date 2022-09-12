# LKT Theme

The semantic themes tool!

This package can help handling most common and reusable theme props and in a sharable and collaborative way with the
rest
of the team.

## Colors

---

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

## Border radius

---

### Available border radius

| Color     | Use case                               |
|-----------|----------------------------------------|
| primary   | The main border radius in your project |
| secondary | Additional border radius               |
| tertiary  | Another one just in case               |

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

---

### Available transitions

| Color     | Use case                            |
|-----------|-------------------------------------|
| primary   | The main transition in your project |
| secondary | Additional transition               |
| tertiary  | Another one just in case            |

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

---

### Available font sizes

| Color     | Use case                           |
|-----------|------------------------------------|
| primary   | The main font-size in your project |
| secondary | Additional font-size               |
| tertiary  | Another one just in case           |

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

---

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