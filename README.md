# frontendquestions

---
title: CSS Questions
---

* What is CSS selector specificity and how does it work?
  - CSS selector specificity is based on the levels and number count of ids, classes, and selectors.
  - Start at 0, add 1000 for *style* attribute (inline), add 100 for each *ID*, add 10 for each *attribute, class or pseudo-class*, add 1 for each element name or pseudo-element (h1).
  
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
  - CSS resets aim to remove all built-in browser styling. Normalize CSS aims to make built-in browser styling consistent across browsers.
  - For example a reset oh h1 tag would remove all the styling on it originally on the browser and a normalize will build upon already css and making it do what it needs to do across diff browsers.
  
* Describe Floats and how they work.
  - When you float an element, what you do is you remove that specific element from natural element flow, but inline elements still respect its boundaries, where block element does not, so thats why <p> element or <div> (both block elements )will collapse, because they don't 'sense' anything is there. Float left will move the element to the left and all inline elements are to the left.  If you use clear on inline, you can move it under the float element. when you check the boundary spacing after the float element, it's been elimated.
 
* Describe z-index and how stacking context is formed.
  - z-index is a layering component.  The stacking is formed like layers in photoshop. where the first or previous layer is the in the back and stacked on top of each other like an imaginary z-axis relative to the user.  The layers are also based depended on the position as well. They may be affected by other properties on how they stack.
 
* Describe BFC (Block Formatting Context) and how it works.
  - The Block Formatting Context is a term to describe how an element lays out things in its own block. The outermost element in a document that uses block layout rules establishes the first, or initial block formatting context. This means that every element inside the <html> element's block is laid out according to normal flow following the rules for block and inline layout.  It determines as well the padding, margins, and borders of the elements inside of how they will react to each other in the layout. This can be observed with the CSS box properties. border-box, etc.
 
* What are the various clearing techniques and which is appropriate for what context?
* How would you approach fixing browser-specific styling issues?
  media queries, dev tools on inspect console and testing in the console before fixing the code, reduces refresh time. 
  
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
  
  
* What are the different ways to visually hide content (and make it available only for screen readers)?
  1.) Use alt for images, use aria-labels for divs and other non-img containers.  
  2.) Positioning and fixing height and width to 1px and setting overflow to hidden to make it gone with people with sight but not invisible to screen readers.
  
* Have you ever used a grid system, and if so, what do you prefer?
  I have used three, Bootstraps grid system, CSS flexbox, and CSS grids.  I prefer CSS grids, however, it is not fully supported yet on Intervnet Explorer so CSS flexbox is a good fall back. Bootstrap is good but only in cases where it's needed quickly but a danger if the library would one day get depreciated or need to be moved to a new version.
  
* Have you used or implemented media queries or mobile specific layouts/CSS?

* Are you familiar with styling SVG?
  - Mainly with fills and strokes and outline animation. 
  
* Can you give an example of an `@media` property other than `screen`?
  - there is just the min-width, max-width, print(for printing). 
  
* What are some of the "gotchas" for writing efficient CSS?
  - 
  
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
  - advantages: It's good to compile a whole bunch of CSS files into one to only serve one css file. Keeps the rest of the CSS code nice and clean and modularized.
  - 

* How would you implement a web design comp that uses non-standard fonts?
  - import otfs on the mac. or grab the woff files and put that in the project. That way the resource is there when needed than depending on a font file cdn to do it like google fonts. Never know when the link might change or get updated. But I would also ask the person who designed the comp to choose a secondary font that is available on most browsers to add on to the font family if shall the font files cannot be grabbed or served somehow.
  
* Explain how a browser determines what elements match a CSS selector.


* Describe pseudo-elements and discuss what they are used for.

* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.

* What does ```* { box-sizing: border-box; }``` do? What are its advantages?

* What is the CSS `display` property and can you give a few examples of its use?

* What's the difference between inline and inline-block?

* What's the difference between the "nth-of-type()" and "nth-child()" selectors?

* What's the difference between a relative, fixed, absolute and statically positioned element?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?  Bootstrap, Materialize, SASS, Animated
  - I think they have their goods, but if it's anything I would change, I say if the dev only needs certain parts of the libraries it would be nice to be able to just grab that portion of the library than have all the components.
  
* Have you used CSS Grid?
* Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?
  - 1.) it depends on the user base of the app/site. 
  - 2.) 
  
* Have you ever worked with retina graphics? If so, when and what techniques did you use? -no
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
* How is clearfix css property useful?
  - move elements 
