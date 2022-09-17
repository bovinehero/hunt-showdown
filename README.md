# Hunt Showdown

This site is a fake hunt marketing site for the popular battle-royal & PVE game [Hunt Showdown](https://www.huntshowdown.com/) built in CSS anf HTML.

As a four marketing site the main goal is to focus on a media heavy approach, as typically large blocks of texts do not aide sales.

## User Stories

1. As a potential player of this game I would like to know more about it in order to make a decision should I buy it
2. As a future player of this game I would like to be able to be able to go and purchase this game from the site
3. As a current player I would like to be informed of upcoming events, features and community events

## Design Considerations

As the primary plaform for this video game is PC one would assume that more views would be from a desktop rather than a mobile phone, thus a desktop first approach was implemented.

Hunt is an atmospheric horror game, the color pallette needs to be dark to enhance the hidden threat with contrast coming from lighter text and highlights to calls to action.

# Features

## Design Considerations

As the primary plaform for this video game is PC one would assume that more views would be from a desktop rather than a mobile phone, thus a desktop first approach was implemented.

Hunt is an atmospheric horror game, the color pallette needs to be dark to enhance the hidden threat with contrast coming from lighter text and highlights to calls to action.

## Global Features

### Colors

In order to create a pitch dark, dead of night feeling a full black background is set as the base background. This allows a build up of elements to establish mood and calls to action can be easily defined with bright coloration. 

As the theme of the game is occult, blood and bone colors make a logical choice for the calls to action and base text.

For the default font color blanchedalmond was selected as it's off white shade provides adequete contrast to the black and red and gives without feeiling monchromatic.

An almost blood red `#880808` gives an appropriate feel to the site while providing significant contrast that it can be used in both white and black color situations.

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

## Page Specific Features

### index.html

To function as the langing page. Information about the product, includes a purchase call to action as well as media elements.

### store.html 

Flex based gallery with uniform images with links out to purchase the games different editions and DLC content

### gallery.html

Column based gallery of image content that includes social media, concept art and screenshots.

### signup.html

A form page that takes user details and signs them up for the newsletter. This is mocked as there is currently no endpoint for this functionality.

## Features Left to Implement

### Responsive styles

CIP1-10 add core styles: TODO implement responsive modes for the site

### Things that needed Javascript

The signup page currently bounces it's request off of the CI testing API, a future enhancement would be deal with this in the page.

Change the signup page to be Modal launched as a discreet call to action that scrolls with the user. I was unable to work out how to implement a modal without JavaScript

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