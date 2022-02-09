# Frontend Mentor - QR code component

I've spent some time away from the frontend and decided to review HTML and CSS by working through the Frontend Mentor Challenges. For this assignment, I recreated the website pictured in the `/design` folder.

## Version 1 - Vanilla HTML and CSS

**Visible on the vanilla branch**

I like to work mobile-first, making sure that the design looks correct on the smallest screen size I'm supporting before accounting for larger screens. While I was working, I commented out the attribution footer so that I was working on a screen that directly matched the design images. This decision came back to haunt me.

In my experience, it's best to set your font family and font sizes before doing anything else. Not doing so can drastically impact your layout later. Since the style guide gave font sizes in pixels, I used the trick of applying 62.5% to the `html` element. This lets me set all of my font sizes responsively in rem without having to use weird numbers in the CSS. Without this, 15px would be set as 0.9375rem instead of the 1.5rem in my code. I also set the size of the image to be no bigger than its parent element at this stage.

Next, I centred the component using Flexbox. Once it was in place, I added all of the small design elements that give it character: border radiuses, colours, margins, padding, and a box shadow. A major criticism I have of the style guide here is that the grey given for the paragraph text is not a high enough contrast against a white background.

I uncommented out the attribution footer and realised that it affected my layout. By centring the QR Code component as if it was the only child in its parent element, my layout was thrown off by adding a second child at the last minute. I decided against adding an extra HTML element for the sole purpose of being a flex wrapper for the QR Code component, and instead absolutely positioned the footer at the bottom of the screen.

To make the desktop view match the brief, I only needed to add one media query to change the width of the QR Code component from 80% to 20%.

## Version 2 - Converting to TailwindCSS

In order to get some experience with TailwindCSS, I decided to redo the challenge. I removed all of my original CSS but left the HTML as it was. I created a `/src` and `/dist` folder to allow TailwindCSS to compile. I added the theme colours and font into the TailwindCSS config file.

Since TailwindCSS uses a base font size of 1rem, which would be 16px by default in most browsers, I changed the font size to 15px on the `html` element in my style.css file.

I followed the same approach as in Version 1, except this time I didn't comment out the footer while I was working! As I'm not very experienced with TailwindCSS, it took a lot of looking into docs to work out which classes I needed. I get the impression that if I spend enough time with TailwindCSS, eventually I will learn the classes I often use and not have to think so much.

When I switched to my desktop view, the only change I needed to make to the QR Code Component was to narrow its width again. I found a max-width setting that looked correct on both mobile and desktop. In retrospect, I could probably refactor my original CSS to use `max-width` on the `main` element instead of a media query.

Finally, I decided to try building a minified version of the CSS, which I have put in the root folder. The original CSS file is in `/src`, and the development compiled CSS file is in `/dist`.
