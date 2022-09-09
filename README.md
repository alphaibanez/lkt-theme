# LKT SCSS Theming


## Colors

---

### Available colors
| Color     | Use case                                               |
|-----------|--------------------------------------------------------|
| primary   | This is your brand main color                          |
| secondary | If your brand has a secondary color, this is the place |
| info      | Give the user some info                                |
| warning   | Warn the user                                          |
| success   | Everything is ok                                       |
| danger    | Something bad could happen                             |
| alert     | Something bad happened                                 |
| target    | Goals                                                  |
| focus     | Focus inputs                                           |


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
@use "lkt-theme";

@include lkt-theme.set-primary-color(#ff0000, #ffffff);
@include lkt-theme.set-secondary-color(blue, green);
```

### Colors usage
```scss
@use "lkt-theme";


button.success {
  background: lkt-theme.$success-color;
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
@use "lkt-theme";

@include lkt-scss-theming.set-border-radius(1px, 2px, 4px);
```

### Border radius usage
```scss
@use "lkt-theme";


button.success {
  border-radius: lkt-theme.$primary-border-radius;
}
```