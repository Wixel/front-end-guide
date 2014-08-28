<<<<<<< HEAD
#Wixel Front-end Style Guide
===

The Wixel Style Guide defines the format, rules and style that should be followed by developers working on **ALL** Wixel sites & products. The reason for the Style Guide is to have high quality & maintainable code which result in great products/sites.


---

##General

###Indentation
Don't mix indentation spaces *always look at the indentation used throughout the document*, at Wixel we use 4 spaces for indentation.

```
.foo{
	color: #ffffff;
}
```

###Comments
Always use descriptive comments where possible but avoid comments ending up in production code (keep performance in mind) except if it serves an important purpose.

Useful comments would include the following information:

* Where the code has affect
* What does it do
* Why have you chosen this solution
* Warnings
* If better solutions are available list them for other developers.

###Automate your build process
Your time spent coding should be uninterupted and other tasks like compiling, optimizing, refreshing should be done automatically. Use an automatic task runner to do these things for you ie. Codekit, grunt, gulp etc.

###Code validity
Continuesly check the validity of the code you're writing. Modern browsers auto correct a lot of invalid HTML but that is no excuse to write poor code.

###Seperation
Strictly keep structure (markup), presentation (styling), and behavior (scripting) apart.

###Assets
Always keep http request to a minimum, compile and minify assets with the exception of libraries and large files.

---

##HTML

###Document type
All Wixel products/sites should use the HTML5 spec and therefore use `<!DOCTYPE html>`.

###Elements

####Block elements
Block elements should always have their opening and closing tags on single lines ie.

```
<article>
	<header>
		<h1>Title</h1>
	</header>
	<main>
		<p>Blah blah blah.</p>
		<p>Blah blah blah.</p>
	</main>
</article>
```

####Inline elements
Inline elements should be on single lines ie.

```
<b>The content.</b>
```

####Void elements
Although fine with HTML, do not close void elements, i.e.
Write `<br>` not `<br />`

###Semantics & accesibility
Use elements (sometimes incorrectly called “tags”) for what they have been created for. For example, use heading elements for headings, `p` elements for paragraphs, `a` elements for anchors, etc.

[HTML5 elements list](https://developer.mozilla.org/en/docs/Web/Guide/HTML/HTML5/HTML5_element_list)

[HTML5 sectioning flow chart (pdf)](http://html5doctor.com/downloads/h5d-sectioning-flowchart.pdf)

Only use the `a` element if the `href` element actually links to something otherwise use `button`.


```
<a href="#" >Scroll to top</a>
```
rather use

```
<button type="button">Scroll to top</button>
```

Please check [when to use the button element](http://css-tricks.com/use-button-element/) to see why.

####Multimedia fallback
For multimedia, such as images, videos, animated objects via `canvas`, make sure to offer alternative access. For images that means use of meaningful alternative text (`alt`) and for video and audio transcripts and captions, if available.

Providing alternative contents is important for accessibility reasons: A blind user has few cues to tell what an image is about without `alt`, and other users may have no way of understanding what video or audio contents are about either.

(For images whose `alt` attributes would introduce redundancy, and for images whose purpose is purely decorative which you cannot immediately use CSS for, use no alternative text, as in `alt=""`.)

####Keep it clean
Try not to use any unecesary elements.

Also omit type attributes for style sheets and scripts. ie.

`<script type="text/javascript" src="path/to/script.js" >Scroll to top</script>`

rather use

`<script src="path/to/script.js" >Scroll to top</script>`

####Quotation marks
Use double `""` for HTML and single `''` for CSS and JS.

---

##CSS

Use a preproccessor where possible (preferably SCSS syntax of Sass) and make code as reusable as possible - think of systems and not pages.

####Reusable class names
Use

```
.bg-alt{
	background-color: #000000;
}
```
Instead of

```
.hero{
	background-color: #000000;
}
```

####Sass
We use the SCSS syntax of Sass.

Keep sass variables in one file and link it to all your other Sass files with `@include`

####OOCSS
At Wixel we use OOCSS to keep code clean and reusable

####Comments

Keep you SCSS code well documented with comments but remove comments from compiled CSS

#####Nested selectors

Keep selectors as simple as possible. Don't nest more than 3 children down.





---

##Images

Not part of coding but has a big impact on site performance ie. page load.

Use SVG where possible - optimize images with an image optimizer - BG images can be lossy, large images with fine detail - should be main content -lossless


=======
Coming soon.
>>>>>>> d9e7cf916dbd5dbb4cb5f41e0a27926702591c6d
