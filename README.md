# Hunt Showdown

This site is a fake hunt marketing site for the popular battle-royal & PVE game [Hunt Showdown](https://www.huntshowdown.com/) built in CSS anf HTML.

As a four marketing site the main goal is to focus on a media heavy approach, as typically large blocks of texts do not aide sales.

## index.html

To function as the langing page. 
This contains the eye candy animation in adition to video media, additionally as a marketing site a purchase call to action to purchase at the base of the page.

## store.html 

Static gallerys with uniform images with links out to purchase the games different editions and DLC content

## gallery.html

Flexible gallery of image content that includes social media, concept art and screenshots.

## signup.html

A form page that takes user details and signs them up for the newsletter. This is mocked as there is currently no endpoint for this functionality.

## User Stories

As a potential player of this game I would like to know more about it in order to make a decision should I buy it

As a potential buyer of this game I would like to be able to purchase this game

As a current player I would like to know of upcoming events, features and community events



(ADD MORE)

# Features
Overview of implemented tech

## Existing Features

### Fonts

For the headings font I selected __Crimson Pro__, as it is based on an updated version of the __Crimson Text__ serif typeface used on the Hunt Showdown [website](https://www.huntshowdown.com/).

This way I could keep within the theme of the site without directly copying it.

```
font-family: 'Crimson Pro', serif;
```

The font selected for the main body was selected for readibility, with a sans-serif being optimal for screens I selected __Open Sans__ as it designed for legibility across print, web, and mobile interfaces.

```
font-family: 'Open Sans', sans-serif;
```

## Existing Features
What I built


## Features Left to Implement
What still to add

# Testing

Screen Sizes
Different Browsers

## Validator Testing

HTML - Ensure No errors were returned when passing through the official W3C validator
CSS - Ensure No errors were found when passing through the official (Jigsaw) validator

# Bugs

The Sign UP page includes css styling for form auto-complete that includes both background color and text color. These will not implemnt on every browser as user agent style sheets of many browsers use !important in their :-webkit-autofill style declarations, making them non-overridable with CSS. 

For example Chrome has the following in its internal stylesheet:

```
background-color: rgb(232, 240, 254) !important;
background-image: none !important;
color: -internal-light-dark(black, white) !important;
```

[ref](https://developer.mozilla.org/en-US/docs/Web/CSS/:autofill)

This means auto-fill background-color, background-image, and color cannot be set reliabily without the inclusion of Javascript. 

# Credits

Special thanks for folks

Google Fonts for the fonts

Font Awesome for the icons

Crytek for the game footage and the presspack