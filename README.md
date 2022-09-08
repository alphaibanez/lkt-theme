# LKT SCSS Theming


## Available Colors

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


## Available Colors Modifiers

| Modifiers | Use case                                                                       |
|-----------|--------------------------------------------------------------------------------|
| contrast  | Contrast color. For example, the default background for this color in a button |
| light     | A light version of the color                                                   |
| lighter   | A lighter version of the color                                                 |
| dark      | A dark version of the color                                                    |
| darker    | A darker version of the color                                                  |

## Configuration

```scss
@use "lkt-scss-theming";

@include lkt-scss-theming.set-primary-color(#ff0000, #ffffff);
@include lkt-scss-theming.set-secondary-color(blue, green);
```

## Usage
```scss
@use "lkt-scss-theming";


button.success {
  background: lkt-scss-theming.$success-color;
}
```