---
title: "How to use fonts in Tableau?"
date: "2020-05-13"
url: "https://www.juditbekker.com/post/how-to-use-fonts-in-tableau"
---

I had my hardships using fonts in Tableau and I’m far from being a typography expert, but here are some suggestions on how to use fonts to avoid the common pitfalls. I started digging deeper into this matter when I published a Superhero dashboard using Comica BD and only weeks later had it turn out, that the others are seeing it differently. I was pretty upset when this came to surface because the whole visualization was centered around that Typekit.

What types of fonts do we have?

Monospace

A monospaced font, also called a fixed-pitch, fixed-width, or non-proportional font, is a font whose letters and characters each occupy the same amount of horizontal space. This contrasts with variable-width fonts, where the letters and spacings have different widths.

Examples of popular monospace fonts:  Courier, Courier New, Lucida Console, Monaco, Consolas, Inconsolata

Serif

In typography, a serif is a small line or stroke regularly attached to the end of a larger stroke in a letter or symbol within a particular font or family of fonts. A typeface or “font family” making use of serifs is called a serif typeface (or serifed typeface), and a typeface that does not include them is a sans-serif one.

Examples of popular serif fonts: Times New Roman, Garamond, Baskerville, Georgia, Playfair Display

Sans serif

In typography and lettering, a sans-serif, sans serif, gothic, or simply sans letterform is one that does not have extending features called “serifs” at the end of strokes. Sans-serif fonts tend to have less stroke width variation than serif fonts. They are often used to convey simplicity and modernity or minimalism.

Examples of popular sans-serif fonts: Helvetica, Arial, Verdana, Futura, Avenir, Myriad Pro

Script

Script typefaces are based upon the varied and often fluid stroke created by handwriting. They are generally used for display or trade printing, rather than for extended body text in the Latin alphabet.

Examples of popular script fonts: Brush Script, Lucida Calligraphy, Lucida Handwriting, Papyrus, Comic Sans

Display

A display typeface is a typeface that is intended for use at large sizes for headings, rather than for extended passages of body text. They may take inspiration from other genres of lettering, such as hand painted signs, calligraphy or an aesthetic appropriate to their use, perhaps ornamented, exotic, abstracted or drawn in the style of a different writing system.

Examples of popular display fonts: Bauhaus, Broadway, Stencil, Windsor

For business dashboards it’s best to use only monotype, serif, and sans serif options.

What are web safe fonts?

Using fonts in Tableau can be a tricky thing because only Tableau web safe fonts will show up the same for everyone. A web safe font is a font that is considered to be a ‘safe bet’ to be installed on the vast majority of computers. Every computer that has a browser installed has default fonts built in so that it can display the text on the web.

Tableau Public and Tableau Online support fonts officially licensed for their Linux servers. Other fonts cannot be guaranteed to display as expected since browser rendering of fonts depends on fonts being installed on both the server and client devices.

If you use a font installed on your computer, that a viewer doesn’t have installed, his view will fall back to his default browser font. Let’s have a look at a Safari example! If I use a custom monospace font (like Lucida Console), for the others viewing my dashboard in Safari, it will fall back to Courier, a custom serif (like Playfair Display) to Times, and a custom sans-serif (like Futura) to Helvetica.

This is the official list of Tableau Public web safe fonts according to Tableau:

Arial

Calibri

Courier New

Georgia

Meiryo UI

Noto CJK Sans

Noto Thai Sans

Noto Thai Serif

Poppins

Roboto

Tableau

Times New Roman

Trebuchet

Verdana

However, I just made a test and it doesn’t seem to be accurate. I put together a list of popular web safe fonts, then deleted everything custom both on my Mac & PC and this is what I see:

If you know you’re designing for PC / Mac users only, here’s a broader list for you. You can read about using custom fonts in Tableau here.

Which font size to use when?

When building a dashboard make sure not to use a lot of different font sizes, because it can mess up the looks and consistency. In an average case, you don’t have to use more than four sizes. Points can vary based on the type of font you’re using, but here’s a guideline you can follow:

22-36pt: for the dashboard title

16-22pt: for subtitles and chart titles

10-14pt: for texts, labels, annotations

8-10pt: axis, notes, date / period, data source, author

If you ever used Figma or Illustrator combined with Tableau, you might have seen that the same font size results in a different outcome, and it’s because it’s not the same. While Tableau is using points by default, Figma and Illustrator use pixels (10 pixels = 8 points). Here’s a converter for you.

There are different CSS units, you won’t use them much, but it’s good to have the overall picture. We have 3 main groups: absolute, relative and viewport units (only makes sense in CSS). In the absolute group we have mm, cm, in, pt, px, and pc – these are all fixed sizes. It gets trickier with relative units, as they are based on the default font size of the browser, which is 16px in most cases (you can overwrite this setting though). These are the relative font size measurement types:

% – percentage

em – font size of the element relative to its parent

2em means that it’s 2 times bigger than the normal size

in case of a 16px default font size 2em means 32px

rem – font size of the element relative to the root html element

Don’t bother if you don’t understand relative units, for dataviz purposes it’s enough to know the difference between the ones in the absolute group:

What font colors to use?

Always make sure that your text is readable. This doesn’t only depend on the font size you choose, but the combination of background color and font color as well. You should always aim for the highest contrast possible. My suggestion would be to avoid using anything other font colors than black, gray, or white, especially on business dashboards. If you use something other than that, it might be disturbing for the eye and could increase your bounce rate.

Let me show you a couple of good and bad practices! (Meh can mean yes for artistic dashboards, but no for business ones.)

How to use emphasis and capitals?

90% of the time you should use regular fonts. If you want to emphasize the different types of information on your dashboard, restrain yourself to italic and bold, and leave everything else behind. No extra bold, bold italic, condensed, condensed extra bold for a business dashboard.

Here’s how to decide what to use when (if not regular):

bold: for dashboard / chart titles, emphasizing the importance of information in a text / note / callout

italic: notes, date / period, data source, author

Mainly things that you don’t want to have on your dashboard, but it’s necessary to have. They don’t convey a valuable message for understanding the data but need to be there for credit and further reference.

Here’s how to use capital letters:

Use them all across the dashboard

Don’t use them at all

Use them for titles only

Font pairings – Do or don’t?

I’d only advise using more fonts if you’re working on an artistic dashboard, but for business purposes, it’s best sticking to one. If you decide to use more, here are the golden rules to follow from combining serif and sans serif fonts to visual hierarchy.

For artistic playdate with fonts I have a Pinterest board for you.

Featured image: Jéshoots
