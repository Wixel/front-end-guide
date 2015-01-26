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
Your time spent coding should be uninterrupted and other tasks like compiling, optimising, refreshing should be done automatically. Use an automatic task runner to do these things for you i.e. Codekit, grunt, gulp , etc.

###Code validity
Continuously check the validity of the code you're writing. Modern browsers auto correct a lot of invalid HTML but that is no excuse to write poor code.

###Separation
Strictly keep structure (markup), presentation (styling), and behaviour (scripting) apart.

###Assets
Always keep http request to a minimum, compile and minify assets with the exception of libraries and large files.

---

##HTML

###Document type
All Wixel products/sites should use the HTML5 spec and therefore use `<!DOCTYPE html>`.

###Elements

####Block elements
Block elements should always have their opening and closing tags on single lines i.e.

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
Inline elements should be on single lines i.e.

```
<b>The content.</b>
```

####Void elements
Although fine with HTML, do not close void elements, i.e.,
Write `<br>` not `<br />`

###Semantics & accessibility
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
Try not to use any unnecessary elements.

Also omit type attributes for style sheets and scripts. ie.

`<script type="text/javascript" src="path/to/script.js" >Scroll to top</script>`

rather use

`<script src="path/to/script.js" >Scroll to top</script>`

####Quotation marks
Use double `""` for HTML and single `''` for CSS and JS.

---

##CSS

Use a pre-processor where possible (We use the SCSS syntax of Sass) and make code as reusable as possible — think of systems and not pages.

###Simple do's and don't
Never use ID's in stylesheets. (follows the rule of keeping markup, styling and scripting apart).

Avoid nesting parent and child elements.

Selectors should be simple i.e. `.class` instead of `div.class`.

###Sass
We use the SCSS syntax of Sass.

Never ever use a framework where there will be any unused  styles or that you find yourself removing code. We're incredibly strict on performance.

For a simple front-end framework grab the [Wixel starter framework](https://github.com/Wixel/simple-wixel-starter-framework) to add to the project.

####Nesting
Never nest more than 3 levels deep. Nesting should also make logical sense i.e.

```
// correct
ul{
	li{
		padding: 2em 0;
	}
}
ol{
	li{
		padding: 1em 0;
	}
}
// incorrect
.hero-section{
	h1{
		// styles
	}
	content{
		.hero-img{
		}
	}
}
```

Nesting in SCSS is both a curse and a blessing. Nesting helps keep your sections and SCSS code organised but creates horrible output in css. Often causing you to overwrite properties and using `!important`. We've corrected this by doing the following:

```
.section{
	// global styles for all sections
	display: inline-block;
	
	&_about{
		// styles for this section
	}
	&_stats{
		// styles for this section
	}
}
```

With the output css being:

```
.section{
	display: inline-block;
}
	.section_about{
		// styles for this section
	}
	.section_stats{
		// styles for this section
	}
```

####Reusable class names
Reusing common styles reduces your stylesheet size, the risk of overwriting properties and saving time in development.

```
.bg{
	&-dark{
		background-color: $dark;
		color: $lightText;
	}
	&-light{
		background-color: $light;
		color: $darkText;
	}
	&-accent{
		background-color: $accent;
		color: $darkText;
	}
}
```
Which you can then simply add to your block elements with `.bg-dark`, `.bg-light` or `.bg-accent` Instead of doing the following over and over:

```
.hero{
	background-color: #000000;
	color: #ffffff;
}
.faq-section{
	background-color: #000000;
	color: #ffffff;
}
.portfolio-items{
	background-color: #ffffff;
	color: #000000;
}
.header{
	background-color: #cccccc;
	color: #000000;
}
```


####Comments

Keep you SCSS code well documented with comments but don't compile comments into the CSS file except for licences or important notices that need to be shown in source.

---

##Images

Not part of coding but has a big impact on site performance. So I felt it had to be noted here.

Use inline SVG for all icons and pretty much anything possible. We use [SVGInjector](https://github.com/iconic/SVGInjector) to keep our SVG's in single files but inject them into the DOM, this keeps your html files clean and the ability to style and animate our SVG's.

Optimise all jpeg's and png's (use SVG's where applicable) with an image optimiser.


