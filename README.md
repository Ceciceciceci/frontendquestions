# frontendquestions

---
title: CSS Questions
Practice for me to understand more of CSS.
---

* What is CSS selector specificity and how does it work?
  > - CSS selector specificity is based on the levels and number count of ids, classes, and selectors.
  > - Start at 0, add 1000 for *style* attribute (inline), add 100 for each *ID*, add 10 for each *attribute, class or pseudo-class*, add 1 for each element name or pseudo-element (h1).
  
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
  > - CSS resets aim to remove all built-in browser styling. Normalize CSS aims to make built-in browser styling consistent across browsers.
  > - For example a reset oh h1 tag would remove all the styling on it originally on the browser and a normalize will build upon already css and making it do what it needs to do across diff browsers.
  
* Describe Floats and how they work.
  > - When you float an element, what you do is you remove that specific element from natural element flow, but inline elements still respect its boundaries, where block element does not, so thats why <p> element or <div> (both block elements )will collapse, because they don't 'sense' anything is there. Float left will move the element to the left and all inline elements are to the left.  If you use clear on inline, you can move it under the float element. when you check the boundary spacing after the float element, it's been elimated.
 
* Describe z-index and how stacking context is formed.
  > - z-index is a layering component.  The stacking is formed like layers in photoshop. where the first or previous layer is the in the back and stacked on top of each other like an imaginary z-axis relative to the user.  The layers are also based depended on the position as well. They may be affected by other properties on how they stack.
 
* Describe BFC (Block Formatting Context) and how it works.
  > - The Block Formatting Context is a term to describe how an element lays out things in its own block. The outermost element in a document that uses block layout rules establishes the first, or initial block formatting context. This means that every element inside the <html> element's block is laid out according to normal flow following the rules for block and inline layout.  It determines as well the padding, margins, and borders of the elements inside of how they will react to each other in the layout. This can be observed with the CSS box properties. border-box, etc.
 
* What are the various clearing techniques and which is appropriate for what context?

* How would you approach fixing browser-specific styling issues?
  media queries, dev tools on inspect console and testing in the console before fixing the code, reduces refresh time. 
  
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
  
  
* What are the different ways to visually hide content (and make it available only for screen readers)?
  > 1.) Use alt for images, use aria-labels for divs and other non-img containers.  
  > 2.) Positioning and fixing height and width to 1px and setting overflow to hidden to make it gone with people with sight but not invisible to screen readers.
  
* Have you ever used a grid system, and if so, what do you prefer?
  > I have used three, Bootstraps grid system, CSS flexbox, and CSS grids.  I prefer CSS grids, however, it is not fully supported yet on Intervnet Explorer so CSS flexbox is a good fall back. Bootstrap is good but only in cases where it's needed quickly but a danger if the library would one day get depreciated or need to be moved to a new version.
  
* Have you used or implemented media queries or mobile specific layouts/CSS?
  > Yes 680/768 px is common pixel count for starting mobile related layout. 420px as well.

* Are you familiar with styling SVG?
  > - Mainly with fills and strokes and outline animation. 
  
* Can you give an example of an `@media` property other than `screen`?
  > - there is just the min-width, max-width, print(for printing). 
  
* What are some of the "gotchas" for writing efficient CSS?
  > 1.) Don't use the official css tag selectors when making new names.
  > 2.) Make your rules as specific as possible. Prefer class and ID selectors over tag selectors.
  > 3.) Remove redundant qualifiers. Like repeatedly using.
  > 4.) Create :root variables if you can use them. This will help lessen the amount of changing every single instance of for example a color across multiple areas of the file.
  > 5.) If writing in HTML file, always put CSS in the head.
  
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
  > - advantages: It's good to compile a whole bunch of CSS files into one to only serve one css file. Keeps the rest of the CSS code nice and clean and modularized.
  > - disadvantages: you have to make sure after compiling that not all the css files contain certain codes that are repeated through out multiple css files. keep it clean and categorize by selector.

* How would you implement a web design comp that uses non-standard fonts?
  > - import otfs on the mac. or grab the woff files and put that in the project. That way the resource is there when needed than depending on a font file cdn to do it like google fonts. Never know when the link might change or get updated. But I would also ask the person who designed the comp to choose a secondary font that is available on most browsers to add on to the font family if shall the font files cannot be grabbed or served somehow.
  
* Explain how a browser determines what elements match a CSS selector.
  > - The browser checks the DOM by filtering out by specificity. It starts from the child and moves up to the parent element.  The shorter the CSS selector, the faster the browser can determine the right match and style the element.

* Describe pseudo-elements and discuss what they are used for.


* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.

* What does ```* { box-sizing: border-box; }``` do? What are its advantages?

* What is the CSS `display` property and can you give a few examples of its use?
  > - CSS display property is used to hide elements from the users' view and also the DOM. Visibility keeps it in the DOM. Some examples you would use it for is when you want an element to be hidden when a form is submitted and things like animation to hide certain elements. 

* What's the difference between inline and inline-block?
  > - inline you can't do much margin styling or height and width styling to the element.  This includes elements like anchors and spans.
  > - inline-block allows you to set a height/width/margins/padding on the element because it gets some properties from the block style.
* What's the difference between the "nth-of-type()" and "nth-child()" selectors?

* What's the difference between a relative, fixed, absolute and statically positioned element?
  > - Static element is the default position of every element. The element flows as it should on the page normally. The only reason to use static is remove the positioning set on it previously.
  > - Relative positioning allows you to position the element from itself. Meaning if you use top: 10px; it will move 10 px down from where it was. You can also use to this limit the scope of absolute positioned children elements inside.
  > - Absolute positioning is nice for being able to put the element you want anywhere on a page and it will be left there, but ! it is still scoped to whichever element it is relative to. so if no relative positioning is set to the parent div around it, its scope will be the entire body. The flow of the element under this positioning is removed. So any elemenst next to it, is under it. Also need to rememeber that if overused it can affect the responsiveness work that needs to be done on it.
  > - Fixed positioning 

* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?  Bootstrap, Materialize, SASS, Animated
  > - I think they have their goods, but if it's anything I would change, I say if the dev only needs certain parts of the libraries it would be nice to be able to just grab that portion of the library than have all the components.
  
* Have you used CSS Grid?  - Y/Y

* Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?
  > - 1.) it depends on the user base of the app/site. 
  > - 2.) mobile first can ean two things, a mobile app, or a website that is meant to be used on mobile devices. 
  > - 3.) when you code a website to be responsive, you are designing it to be responsive on different screen sizes.
  
* Have you ever worked with retina graphics? If so, when and what techniques did you use? -no

* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
  > If you don't need to fix the flow of one element somewhere in the parent context it is in, don't use absolute positioning. 

* How is clearfix css property useful?
  -  move elements under without using br/ for example a div you want to clear left and right of it. 
  -  You can use it to clear floats.
