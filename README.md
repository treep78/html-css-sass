[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# HTML, CSS, & Sass

## Prerequisites

-   [ga-wdi-boston/html-css](https://github.com/ga-wdi-boston/html-css)
-   [ga-wdi-boston/js-template-installation](https://github.com/ga-wdi-boston/js-template-installation)

## Objectives

-   Store style rules in variables
-   Calculate styles using variables and arithmetic operations
-   Make a custom extension to DRY out CSS

## Preparation

1.  [Fork and clone](https://github.com/ga-wdi-boston/meta/wiki/ForkAndClone)
    this repository.
1.  Install dependencies with `npm install`.

## Sass

[Sass](http://sass-lang.com) is a powerful [CSS
preprocessor](https://github.com/showcases/css-preprocessors). CSS preprocessors
use programming languages like Ruby, C, or JavaScript to add features to your
stylesheets that are absent from native CSS. Some examples include:

-   variables,
-   calculations,
-   and extensions or mix-ins.

Examples of how you can use a preprocessor like Sass:

-   [Build A Pleasing Color Scheme Programmatically](http://devmag.org.za/2012/07/29/how-to-choose-colours-procedurally-algorithms/)
-   [Build Your Own Custom Grid](http://webdesign.tutsplus.com/tutorials/a-simple-responsive-grid-made-even-better-with-sass--cms-21540)
-   [Make Your Application Themeable](http://webdesign.tutsplus.com/tutorials/how-to-use-sass-to-build-one-project-with-multiple-themes--cms-22104)
-   [Improve Your Markup by Extending Classes](https://coderwall.com/p/wixovg/bootstrap-without-all-the-debt)

Let's start by defining a theme for an example application.

## Demo: Save Colors as Variables

Let's have a look at the current styles in
[`assets/styles/index.scss`](assets/styles/index.scss). You'll see that we're
already making use of a great feature of Sass: variables. You should save
important bits of style, especially colors, with a descriptive, useful name.

## Exercise: Semantic Color Names and Theming

These variables names aren't that great. First, I'll create a colors module that
defines semantic names for the inscrutable hexadecimal color literals we're
using. Then, I'll create a theme module that gives us a better idea of how these
colors map to styles on our page.

Finally, I include the theme in
[`assets/styles/index.scss`](assets/styles/index.scss), which serves as our
style "manifest". Webpack will look for styles here and then let Sass follow
import statements to find all the files it needs. If we leave a module out of
this file and it isn't included inside another module, it won't affect the
styling of our page.

In general, you should `@import` a module when it is used inside the current
module. For the modules that apply to our entire application, we should include
them in our manifest as well. Sass will not duplicate rules if they're imported
in multiple places.

## Lab: Typography

The text on our page isn't that readable. Have a look at [Better Motherfucking
Website](http://bettermotherfuckingwebsite.com/). Use your hacker skills to
figure out the CSS rules the site uses to make content more readable.

Typography is a complex subject, but for now, when we talk about typography,
we mean CSS rules aimed at improving the readability of your website. Such
rules include, but are not limited to:

-   `margin`
-   `width` and friends (like `max-width`)
-   `line-height`
-   `font-size`
-   `padding`

Save *only the rules that deal with typography* in
[`assets/styles/typography.scss`](assets/styles/typography.scss) and be sure to
include it inside your manifest.

## Demo: Styling a Quote

In publishing, it is often desirable to pick essential quotes in content and
re-print them using special styling that draws attention to the importance of
that specific content. These are sometimes called "block quotes" or "callouts".

We have an example of such a quote in [`index.html`](index.html). Some would
argue that quotes are not paragraphs, but I think semantically they are. Here's
what Mozilla considers the semantics of paragraph elements:

> Paragraphs are usually represented in visual media as blocks of text that are
> separated from adjacent blocks by vertical blank space and/or first-line
> indentation. Paragraphs are block-level elements.
>
> [<p> - HTML (HyperText Markup Language) &#124; MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)

Since semantics don't just depend on what developers think the semantics are,
but how the reader of our content would interpret meaning, it is acceptable to
use the generic block element, `div`, for our quote, instead.

We already have a style that draws attention to the quote in our manifest. Let's
clean that up by extracting that rule into a module.

## Exercise: Move Quote Styles

Move the quote style declarations into the theme. Why would we want to keep
these styles in the theme module?

## Lab: Use Sass Functions

Make use of existing color definitions and the Sass `darken` function to darken
the `$background-color` by 10% instead of writing a color literal.

Also, use a calculation based on default `font-size` instead of using a literal
`px` unit.

Use variables to store the results of calculations.

## Exercise: Create an Extension

Define the custom functions described in the [Sass
Guidelines](http://sass-guidelin.es/#lightening-and-darkening-colors) for
manipulating color. They provide greater control than `darken` and `lighten`.

## Lab: Include an Extension

Now, include your extension and use it instead of the `darken` function.

## Best Practices

You'll notice that the Sass linter yells at you for a lot of things that might
seem silly. Follow the advice anyway. These simple rules, while annoying at
first, will lead to DRYer rules declarations and prevent accidental surprises
when developing your own custom CSS.

Best practice include, but are not limited to:

-   Do not use HTML `id` attributes to select elements for styling.
-   Always save color literals in meaningful variable names, defined as
    hexadecimal values.
-   Instead of hard-coding size units, give them a good name and use arithmetic
    to adjust as necessary.
-   Re-used calculations should be stored in a variable.
-   Sort rule declarations by property name in alphabetical order.

For more best practices, see [Sass Guidelines](http://sass-guidelin.es/), a
community-maintained list of best practices and explanations.

## Additional Resources

-   [Color Picker - Explore Colors for HTML and CSS](http://www.hexcolortool.com)
-   [Controlling color with Sass color functions](https://robots.thoughtbot.com/controlling-color-with-sass-color-functions)
-   [PXtoEM.com: PX to EM conversion made simple.](http://pxtoem.com/)

## [License](LICENSE)

Source code distributed under the MIT license. Text and other assets copyright
General Assembly, Inc., all rights reserved.
