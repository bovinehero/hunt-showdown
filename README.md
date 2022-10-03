# Hunt Showdown

This site is a fake hunt marketing site for the popular battle-royal & PVE game [Hunt Showdown](https://www.huntshowdown.com/) built in CSS anf HTML.

As a faux marketing site the main goal is to focus on a media heavy approach, as typically large blocks of texts do not aide sales.

## User Stories

1. As a potential player of this game I would like to know more about it in order to make a decision should I buy it
2. As a future player of this game I would like to be able to be able to go and purchase this game from the site
3. As a current player I would like to be informed of upcoming events, features and community events

## Design Considerations

Initially I looked into building this site desktop first rather than a mobile first, however while this provided ample learning opportunities it was not conducive to good design practice as positioning and sizing became a common cause for code refactors. Ultimately this led to a refactor of the initial build into a mobile responsive site after I had generated the base content in a large screen size.
 
Hunt is an atmospheric horror game and so the colour pallette needed to match this dark theme, to enhance the 'hidden threat' and hiding in the shadows aspects of the game a dark background with contrast coming from lighter text was chosen. Highlights on our to calls to action would need to be a single colour addition to break through the light and dark contrasts. 

Additionally as a faux advertising site, text components should have a minimum reliance on text, instead the pictures and graphics should be used to advertise what the game is like for potential players.


### index.html

> The Landing page. Information about the product, includes a purchase call to action as well as media elements.

wire frame and screenshot of finished product

### store.html 

> Flex based gallery with uniform images with links out to purchase the games different editions and DLC content

wire frame and screenshot of finished product

### gallery.html

> Column based gallery of image content that includes social media, concept art and screenshots.

wire frame and screenshot of finished product

### signup.html

> A form page that takes user details and signs them up for the newsletter. This is mocked as there is currently no endpoint for this functionality.

wire frame and screenshot of finished product

### 404.html

> A functional page that will return when a user tries to follow a link to a non existant resource.

wire frame and screenshot of finished product

# Features

## Global Features

### Favicon & Head Tags

As this project is part of a portfolio of work hosted on my personal domain of bovinehero.com I included my favicon image from the parent site which thanks to the github hosting engine auto presents itself in the address tab of the website. I will be including this in all projects going forward that are hosted on this domain in order to 'sign' the work as part of my portfolio.  

I also included the :cowboy_hat_face: emoji in the title of every page. I did this because:

1. The game is set in the 1890s Lousisiana cowboys are a part of the theme.
2. Because we can and development without a little whimsy is a job.

I started with the boilerplate meta tags that come packed with Visual Studio Code's http extensions to define `charset`, `http-equiv`, `content` and `viewport`

Registering with font awesome I was able to used some of their icons in various pages, but to be honest they were used so little within the site's pages that replacing them for smaller images may have improved loading performance.

I elected for an external stylesheet __assets/css/main.css__ for everything except for the custom 404 page as it is considered best practice. I chose to follow the scss naming convention of 'main.css' for this as (while not in scope here) in future projects may wish to look at thematic style toggles and varaiblising style settings in future projects.

The content and description I added to aid in SEO.

``` html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script src="https://kit.fontawesome.com/4038346e3a.js" crossorigin="anonymous"></script>
    <link rel="stylesheet" href="assets/css/main.css">
    <meta name="keywords" content="hunt showdown, hunt, huntz">
    <meta name="description" content="Fan made site for Hunt: Showdown as part of Code Institute work">
    <title> 🤠 Hunt Showdown | Home</title>
</head>
```

### Body Background

To provide a clean experience I reset the `margin`, `padding` and set the `box-sizing` to `border-box` as per best practice in the [mdm web docs](https://developer.mozilla.org/en-US/docs/Learn/CSS). I also set the border to none, so that if I wanted to include borders I could create them from scratch.

``` css
* {
  margin: 0;
  padding: 0;
  border: none;
  box-sizing: border-box;
}
```

Almost immediately I decided that I wanted an atmospheric background image to fill the page and scroll with the user, which I implemented this with the following code: 

``` css
body {
    position: relative;
    min-height: 100vh;
    background: url('../images/page-background.jpg') no-repeat center bottom fixed, black;
  }
```

Which created a fallback of black in the areas that the image would not cover and establishes an eerie lost in the dark effect.

### Colors

In order to create a pitch dark, dead of night feeling a full black `#000000` background is set as the base background. This allows a build up of elements to establish mood and calls to action can be easily defined with bright coloration. 

As the theme of the game is occult, blood and bone colors make a logical choice for the calls to action and base text. For the default font color `blanchedalmond` or `#ffebcd`was selected as it's off white shade provides adequete contrast to the black and red and gives without feeiling monchromatic.

An almost blood red `#880808` gives an appropriate feel to the site while providing significant contrast that it can be used in both white and black color situations.

<div>
  <div style="color:#ffebcd; background-color:#000000; text-align:center; vertical-align: middle; padding:20px 0;">
  000000
  </div>
  <div style="color:#ffebcd; background-color:#880810; text-align:center; vertical-align: middle; padding:20px 0;">
  880810
  </div>
  <div style="color:#ffebcd; background-color:#333333; text-align:center; vertical-align: middle; padding:20px 0;">
  333333
  </div>
  <div style="color:#001432; background-color:#ffebcd; text-align:center; vertical-align: middle; padding:20px 0;">
  FFEBCD
  </div>
</div>

The main drawback of this colour scheme is that some people cannot register red in their visual spectrum, this presents as a missing colour towards the black end of vision thus any use of the red coloration is contrasted with the lighter blanched almond shade in order to preserve accessibility.

### Fonts

For the headings font I selected __Crimson Pro__, as it is based on an updated version of the __Crimson Text__ serif typeface used on the Hunt Showdown [website](https://www.huntshowdown.com/).

This way I could keep within the theme of the site without directly copying it.

``` css
font-family: 'Crimson Pro', serif;
```

The font selected for the main body was selected for readibility, with a sans-serif being optimal for screens I selected __Open Sans__ as it designed for legibility across print, web, and mobile interfaces.

``` css
font-family: 'Open Sans', sans-serif;
```

> OpenDyslexic: a consideration for future projects

I considered implementing a specialist typeface to try and eliviate common symptoms dyslexia either as the primary fontface or as a switchable style. 

With a little research I discovered the [OpenDyslexic](https://opendyslexic.org/) font which provided the means to meet this requirement, however as the primary font it detracted from the asthetic of the site. Instead I looked into implementing a switchable stylesheet for accessibility however implementation seemed dependent on either javascript or serverside technologies - both of which were out of scope for this project.

### Header

The header comprised of 2 components the Logo and Navigation Bar. I elected to make this a sticky header so that it would scroll with the user as they traverse the site to provide continuous navigation options.

#### Logo

Originally I had planned to include a logo picture in the Header, however this was unweildy as the only images I could get that were suitable were pngs, an SVG asset would have provided auto scale regardless but eventually PNGs lose their crispness as they scale up into very large screens. I considered implementing multiple image sizes and converting the base format of the picture to SVG, but in the end did not feel I could deliver on the task within the time frame with the tools I had to hand. Instead I implemented an `h1` header that communicated the same information.

#### Nav Bar

The first draft of the nav bar was a horizontal `inline-block` implementation much like the demo site in the course, however as I was refactoring the site into a more mobile friendly solution the need for a smaller more succint menu was apparent. Most modern mobile first sites use a burger menu to aid in navigation, and while the solution seemed fairly straigtforward to implement with JavaScript any efforts I made to implement it cleanly with CSS became quite complicated. 

I experimented with a few different techniques but settled on starting with a hidden nav menu with a list of the pages in the site. I [discovered a CSS technique](https://codepen.io/erikterwan/pen/EVzeRP) which created a 3 horizontal line hamburger and rotated them into an X and provided a drop down menu. I adapted this to my own site which solved the squashed menu effect I was seeing on smaller resolutions. 

### Footer

The footer comprises of 2 components, social media links and copywrite text in a flex box. I wanted the footer to sit at the very bottom of the screen when it appeared on the site so used the `justify-content: flex-end;` CSS attribute to do this.

On smaller screens this worked fine but as the screans got larger the footer div would not sit at the bottom of the scream, so I implemented a `position: absolute;` for larger screen sizes forcing the content to the bottom right. 

On it's own the `position: absolute;` caused an overlap with the content in smaller screens, this way I was able to provide a more consistant experience for the user.

## Page Specific Features

### index.html

#### Hero Banner
The hero banner contains an animated reverse zoom of a hunter in an effort to give the site a level of dynamisism on landing. A big driver in the game is that a single shot can kill and often that shot comes in the dark from an unkown location, both the image and the zoom out we selected to try and achieve this effect.

For accessibility this animation is deactivated via the following code in `main.css`

``` css
@media screen and (prefers-reduced-motion) {
  #banner-image {
      animation-duration: 0s;
    }
  } 
```

The Banner also contains a fixed text over the banner image with a colour change to blood red of the `<span>die alone.</span>`, again to highlight the frailty your player character has in the game. The transition here is slower and doesn't include motion so the color change persists over reduced motion prefernce.

#### Testimonials

The testimonials section included a flex row wrapped div with 4 components: a title and 3 reviews. 

As the first child of the div I could persist the title over the reviews by specifing the flex grow, shink and basis with: `flex: 1 0 100%;`

This would mean no matter the size of the screen the title would remain on top. 

For the reviews I decided to implement as blockquotes to preserve semantic meaning with direct links to the citations and styled them to be a fixed width. 

On larger screen sizes this section looked quite small in comparison to everything else and so the content was spced out more using the following code:

``` css
#testimonials {
    justify-content: space-evenly;
  }
```

#### YouTube Media

Initially I'd considered a video section here, but the constraints of gitlab and lack of suitable content prompted a flip into using a YouTube iframe for the media section. 

As an import from youtube much of the functionality comes for free, the frame border and fullscreem mode were set by default as were many of the player's advanced options: `"accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"`

As an exteranl resource I added in `loading="lazy"` to tag the iframe as a non-blocking asset and make it load only as needed.

The resolution sizes for the base iframe I implemented as a default 16:9 (as per the source video) and incremented the pixel sizes up through multiples of this ratio from 384px by 216px to 1600px by 900px in subsequent media screen sizes. This way the user sees a good portion of the content creator's video cover in their screen.

#### Product Description

This section is the main text description of Hunt: Showdown from the publisher's [store](https://eu-shop.crytek.com/games/hunt-showdown) stylised responsivley to fit within the site. Following the natural flow of the site, after some attention grabbing multi-media content this part explains to the user what the game is and how it works. This section uses a flex column to center the content.

As the screen sizes become larger, this area begins to feel a little lost so for screens larger than 1920px I added a bonus background image of one of the games' bosses with the following code:

``` css
  #product {
    background: url('../images/assassin.jpg') no-repeat center center , black;
    margin: 0 12%;
    padding: 20px 0;
  }
```

This was intended to trick the eye into seeing more content than is really there on the larger screen.

#### Purchase Links

The Purchase Links at the bottom of the page are the call to action of the site, where upon viewing the content above hopefully the consumer will be inspired to consider purchasing the game, the code here is a re-implemetation of the code in the __Purchase Game__ section of the store page.

### store.html 

The store page provides links out two versions of the game, one from the official crytek store and an additional collectors edition in steam. The user can also head out to the official store view a selection of DLC from the game.

The store sections are arranged on 2 flex row 'shelves' with the games being the top row and the DLC the lower one.

``` css
#games, #dlc {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
}
```

On larger screens this is presented as 2 distinct rows, but the use of flex wrap ensures that on smaller screens this moves naturally into a column view without the need to refactor.

The purchase items are yet another flex div within the outer section. For the DLC items I elected for fixed narrower width so that the text and background image for the store item would remain consistent within screen sizes and to allow a bit more content on a row.

I wanted the game purchase boxes to be fairly large on the page to consume more real estate on a row in both the index and store pages. However the available image sizes limited the box sizes to around 400px (double the width) of the DLC components.


### gallery.html

The gallery is composed of of various media from a press pack download the official Hunt Showdown [site](https://www.huntshowdown.com/media) arranged into a column defined section.

I wanted to have a semblance of structure to the gallery but not be restrictive on image sizes as long as they fit propotionally within a column. To accomplish this I implemented a column-gap in the section to provide horizontal spacing and set the image widths to be 100% of the column. To keep the design mobile firstt, the smaller screens recieve a single column containing pictures as the default, screen resolutions increase the number of columns gradually increase to 4 via use of media queries, ensuring the gallery consumes more of the real esate availabe on screen.

> TODO Images sizes

### signup.html

The signup form was heavily influenced by the love running project within the course. Originally I'd planned for this to be a modal either launched from the footer or in the sticky menu but could not work out a clean way to do this without javascript.

By default the form is positioned to the left by default and use all the horizontal space with a max-width of 100%, fixed padding size or 30px but a flexible 10% margin. This was in an attempt to make it use as much space as possible without consuming the entire screen asthetically pleasing in smaller screens. 

As the viewing port becomes larger we use proportionally reduce the max-width in the media queries to avoid making the form look stretched accross the section.

By the time we get to the largest screen sizes, we have a small form on the left and can view the entire background picture in the section. 

### 404.html

This page leverages the github pages jekyll engine to provide a custom 404 experience for users. 

The styling here is inline as any http calls to child directories cannot be reliably referneced by links in the header, specifically users could manually input non-existing child directories into the url bar and would not see the styling.

Similarly the link back to the home page needs to directly reference the home url [https://bovinehero.com/hunt-showdown/index.html](https://bovinehero.com/hunt-showdown/index.html) as relative referencing will not guarantee a return to the home page if child directories are inputted into the url.

## Features Left to Implement

### Responsive styles

In the gallery.html page the code is succint but produses inefficent results as the pictures are not optimised for scale or format. Multiple picture sizes using modern formats like webp would reduce the time to load here and create a better experince for users.

CIP1-12 turn site into https site prior to final release

### Things that needed Javascript

The signup page currently bounces it's request off of the CI testing API, a future enhancement would be deal with this in the page.

Change the signup page to be Modal launched as a discreet call to action that scrolls with the user. I was unable to work out how to implement a modal without JavaScript

I would like to have implemented a colour switcher to allow for different color deficient vision types. I researched dark mode and css theme switches to try and work out a way to implement this. However within the timeframe I had allocated for the project I was unable to deliver on this without the use of javascript. 

Additionally I considered implementing a font switcher to leverage the [OpenDyslexic](https://opendyslexic.org/) font as a switchable font face but again the implementation seemed dependent on javascript.

The copyright section includes a date, I would like to have this updated based on the current year to lazy maintain the site, but I could not find a way to pull the date without server-side input or JavaScript.

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

# Credits

Special thanks for folks

Google Fonts for the fonts

Font Awesome for the icons

Crytek for the game footage and the presspack

Mozilla for the current standards

[Erik Terwan](https://codepen.io/erikterwan/pen/EVzeRP) for the idea on the CSS burger

[https://ezgif.com/](https://ezgif.com/) image conversion to webp