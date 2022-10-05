# Testing

Screen Sizes
Different Browsers

## Validator Testing

HTML - Ensure No errors were returned when passing through the official W3C validator
CSS - Ensure No errors were found when passing through the official (Jigsaw) validator

# Bugs

The SignUp page includes css styling for form auto-complete that includes both background color and text color. These will not implemnt on every browser as user agent style sheets of many browsers use `!important` in their `:-webkit-autofill` style declarations, making them non-overridable with CSS. 

For example Chrome has the following in its internal stylesheet:

``` css
background-color: rgb(232, 240, 254) !important;
background-image: none !important;
color: -internal-light-dark(black, white) !important;
```

[ref](https://developer.mozilla.org/en-US/docs/Web/CSS/:autofill)

This means auto-fill background-color, background-image, and color cannot be set reliabily without the inclusion of Javascript. 