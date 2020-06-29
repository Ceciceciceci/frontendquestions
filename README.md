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
  > - When you float an element, what it does is it changes the flow of the elemts around it. While inline elements still respect its boundaries, the block element does not, so thats why <p> element or <div> (both block elements )will collapse, because they don't 'sense' anything is there. Float left will move the element to the left and all inline elements are to the left.  If you use clear on inline, you can move it under the float element. when you check the boundary spacing after the float element, it's been elimated.
  > - The CSS clear property can be used to be positioned below left/right/both floated elements.
  > - 
 
* Describe z-index and how stacking context is formed.
  > - z-index is a layering component.  The stacking is formed like layers where the first or previous layer is the in the back and stacked on top of each other like an imaginary z-axis relative to the user.  The layers are also based depended on the position/parent/child as well. They may be affected by other properties on how they stack.
  > - For example, If an element B sits on top of element A, a child element of element A, element C, can never be higher than element B even if element C has a higher z-index than element B.
 
* Describe BFC (Block Formatting Context) and how it works.
  > - The Block Formatting Context is a term to describe how an element lays out things in its own block. The outermost element in a document that uses block layout rules establishes the first, or initial block formatting context. This means that every element inside the <html> element's block is laid out according to normal flow following the rules for block and inline layout.  It determines as well the padding, margins, and borders of the elements inside of how they will react to each other in the layout. This can be observed with the CSS box properties. border-box, etc.
 
* What are the various clearing techniques and which is appropriate for what context?
 > - The .clearfix hack uses a clever CSS pseudo selector (:after) to clear floats. Rather than setting the overflow on the parent, you apply an additional class like clearfix to it. Then apply this CSS:
         ```.clearfix:after {
            content: '.';
            visibility: hidden;
            display: block;
            height: 0;
            clear: both;
          }```
 > - overflow clears : auto or hidden method - Parent will establish a new block formatting context and expand to contains its floated children. Alternatively, give overflow: auto or overflow: hidden property to the parent element which will establish a new block formatting context inside the children and it will expand to contain its children.

* How would you approach fixing browser-specific styling issues?
  > - media queries, dev tools on inspect console and testing in the console before fixing the code, reduces refresh time. 
  
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
  > - One technique is after identifying the issue and the offending browser, use a separate style sheet that only loads when that specific browser is being used. This technique requires server-side rendering though.
  > - You can also use CSS libraries that exist like Bootstrap that has uniformally tested to work between multiple browsers.
  > - there are also prefixes that can be used to this as well like -webkit-transition - o , -moz, -ms, 
  > - Use caniuse.com to check for feature support.
  > - Progressive enhancement — The practice of building an application for a base level of user experience, but adding functional enhancements when a browser supports it.
  
* What are the different ways to visually hide content (and make it available only for screen readers)?
  > 1.) Use alt for images, use aria-labels for divs and other non-img containers.  
  > 2.) Positioning and fixing height and width to 1px and setting overflow to hidden to make it gone with people with sight but not invisible to screen readers.
  > 3.) text-indent: -9999px. This only works on text within the block elements.
  
* Have you ever used a grid system, and if so, what do you prefer?
  > I have used three, Bootstraps grid system, CSS flexbox, and CSS grids.  I prefer CSS grids, however, it is not fully supported yet on Intervnet Explorer so CSS flexbox is a good fall back. Bootstrap is good but only in cases where it's needed quickly but a danger if the library would one day get depreciated or need to be moved to a new version.
  > I do know of the float grid system, it does have the most support at the moment even with older browsers.
  
* Have you used or implemented media queries or mobile specific layouts/CSS?
  > Yes 680/768 px is common pixel count for starting mobile related layout. 420px as well.

* Are you familiar with styling SVG?
  > - Mainly with fills and strokes
  
* Can you give an example of an `@media` property other than `screen`?
  > - there is just the min-width, max-width, print(for printing). With print you need to add page-breaks
  
* What are some of the "gotchas" for writing efficient CSS?
  > 1.) Don't use the official css tag selectors when making new names.
  > 2.) Make your rules as specific as possible. Prefer class and ID selectors over tag selectors.
  > 3.) Remove redundant qualifiers. Like repeatedly using.
  > 4.) Create :root variables if you can use them. This will help lessen the amount of changing every single instance of for example a color across multiple areas of the file.
  > 5.) If writing in HTML file, always put CSS in the head.
  
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
  > - advantages: It's good to compile a whole bunch of CSS files into one to only serve one css file. Keeps the rest of the CSS code nice and clean and modularized. 
    - Easy to write nested selectors.
    - Variables for consistent theming. Can share theme files across different projects.
    - Mixins to generate repeated CSS.
    - Splitting your code into multiple files. CSS files can be split up too but doing so will require a HTTP request to download each CSS file.

  > - disadvantages: you have to make sure after compiling that not all the css files contain certain codes that are repeated through out multiple css files. You might also spend more time recompiling.

* How would you implement a web design comp that uses non-standard fonts?
  > - Can use @font-face css keyword  OR
  > - import otfs on the mac. or grab the woff files and put that in the project. That way the resource is there when needed than depending on a font file cdn to do it like google fonts. Never know when the link might change or get updated. But I would also ask the person who designed the comp to choose a secondary font that is available on most browsers to add on to the font family if shall the font files cannot be grabbed or served somehow.
  
* Explain how a browser determines what elements match a CSS selector.
  > - The browser checks the DOM by filtering out by specificity. It starts from the child and moves up to the parent element.  The shorter the CSS selector, the faster the browser can determine the right match and style the element.

* Describe pseudo-elements and discuss what they are used for.
 > - A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s). They can be used for decoration (:first-line, :first-letter) or adding elements to the markup (combined with content: ...) without having to modify the markup (:before, :after).  There is also nth-child, and the like. 

* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
 > -  The CSS box model is responsible for calculating:
       - How much space a block-level element takes up.
       - Whether or not borders and/or margins overlap, or collapse.
       - A box’s dimensions.
 > - calculated by width, height, padding, borders, and margins.

* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
 > - By default, elements have ```* {box-sizing: content-box }``` applied, and only the content size is being accounted for.
 > -box-sizing: border-box changes how the width and height of elements are being calculated, border and padding are also being included in the calculation.
    > - The height of an element is now calculated by the content's height + vertical padding + vertical border width.
    > - The width of an element is now calculated by the content's width + horizontal padding + horizontal border width.

* What is the CSS `display` property and can you give a few examples of its use?
  > - CSS display property is used to hide elements from the users' view and also the DOM. Visibility keeps it in the DOM. Some examples you would use it for is when you want an element to be hidden when a form is submitted and things like animation to hide certain elements. 

* What's the difference between inline and inline-block?
  > - inline you can't do much margin styling or height and width styling to the element.  This includes elements like anchors and spans.
  > - inline-block allows you to set a height/width/margins/padding on the element because it gets some properties from the block style.
  
* What's the difference between the "nth-of-type()" and "nth-child()" selectors?
  > - nth-of-type() is a little less picky than nth-child.  nth-child checks the parent that is applied to like an array and finds that particular element see how many children are under it and then finds the #th in the array.  nth-of-type() applies it to every element attached to the kind of element specified to it like p:nth-of-type will go find all paragraphs in the element that are paragraphis and that condition.
  
* What's the difference between a relative, fixed, absolute and statically positioned element?
  > - Static element is the default position of every element. The element flows as it should on the page normally. The only reason to use static is remove the positioning set on it previously. The top, right, bottom, left and z-index properties do not apply.
  > - Relative positioning allows you to position the element from itself. Meaning if you use top: 10px; it will move 10 px down from where it was. You can also use to this limit the scope of absolute positioned children elements inside.
  > - Absolute positioning is nice for being able to put the element you want anywhere on a page and it will be left there, but ! it is still scoped to whichever element it is relative to. so if no relative positioning is set to the parent div around it, its scope will be the entire body. The flow of the element under this positioning is removed. So any elemenst next to it, is under it. Also need to rememeber that if overused it can affect the responsiveness work that needs to be done on it.
  > - Fixed positioning is when the element is removed from the flow of the page and positioned at a specified position relative to the viewport and doesn't move when scrolled.

* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?  Bootstrap, Materialize, SASS, Animated
  > - I think they have their goods, but if it's anything I would change, I say if the dev only needs certain parts of the libraries it would be nice to be able to just grab that portion of the library than have all the components.
  > - Bootstrap 
  
* Have you used CSS Grid?  - Y/Y
  > - Grid is nice for 2 dimensional layouts but I'm hoping that it will get more supported in the future as it will change how we can structure our sites and components to make it more easier to maintain.

* Can you explain the difference between coding a web site to be responsive versus using a mobile-first strategy?
  > - 1.) it depends on the user base of the app/site. 
  > - 2.) mobile first can ean two things, a mobile app, or a website that is meant to be used on mobile devices. 
  > - 3.) when you code a website to be responsive, you are designing it to be responsive on different screen sizes.
  
* Have you ever worked with retina graphics? If so, when and what techniques did you use? -no

* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
  > translate() is a value of CSS transform. Changing transform or opacity does not trigger browser reflow or repaint, only compositions, whereas changing the absolute positioning triggers reflow. transform causes the browser to create a GPU layer for the element but changing absolute positioning properties uses the CPU. Hence translate() is more efficient and will result in shorter paint times for smoother animations.
When using translate(), the element still takes up its original space (sort of like position: relative), unlike in changing the absolute positioning.

* How is clearfix css property useful?
  -  move elements under without using br/ for example a div you want to clear left and right of it. 
  -  You can use it to clear floats.
