---
title: "Digging into tooltips with David Lynch"
date: "2021-04-10"
url: "https://www.juditbekker.com/post/digging-into-tooltips-with-david-lynch"
---

In the past few weeks (maybe months), I was on holiday in the deserted creativity island, so it feels good to be back with a dataviz design I’m happy with. There’s no shame in not being able to come up with ideas. To phrase it in a Lynchian way, you have to take a sunbathe on the shore before catching the big fish. I don’t attach negative feelings to the lack of creativity, and I did a lot of great things I feel good about – they just happened to be different than dataviz. I biked a lot, planted a spice garden on the 3rd floor (still not sure if they will start growing or not, but my cherry tomatoes look promising), read new books, and completely fell in love with David Lynch.

Trying to catch that fish

Cutting photos into pieces was always on my creative agenda, I keep collecting pictures like the ones below on my UI design Pinterest board. How cool these look?

I also put together a Twin Peaks Pinterest board: there are so many great artworks out there that I could easily cover all my walls in the apartment with just these.

Faking a treemap

This idea I came up with lurked around my mind for what seems like an eternity. The original thought was to cut poor David Lynch into segments following the lines of a treemap, which looks like it is, but I had to make some changes. The treemap alignment seemed awkward, but I found no way to sort them how I wanted. And I understand why. Custom sorting would undermine the whole concept of visualizing treemaps. So here’s what I did. I reorganized the pieces while keeping their proportions, but this meant that each tile ended up as a separate sheet rather than one big treemap. Poor David Lynch did get cut into segments at the end.

The interactive version is published on my Tableau Public profile.

Final design in Illustrator

Transcending into tooltips

This is the first time in my life I’m satisfied with the tooltips. Honestly, I don’t have a single clue how these work in Tableau, but even if they look fine(ish) on the desktop, my tooltips become way too wide on the server. I compared how my default tooltips would’ve looked like versus the formatted version I end up with. Take a look at the original:

Original tooltip

I’m not saying it wasn’t 568% extra work to make them more visually appealing, but I think it worth the effort. You can probably tell by its appearance how I did it: viz in tooltips. While the upper solution contains text snippets + a bullet chart, the formatted version consists of 4 different worksheets that I added to the tooltips pane. This way, I could control the height and width of all elements. By applying this method, they won’t “overflow” on the server.

Formatted tooltip

Tooltip 1: Plain text explaining what the visualization is about, how you should read it, the data source, and the picture credit

Tooltip 2: Title and details of the film (year, duration, IMDb score)

Tooltip 3: IMDb score bullet chart

Tooltip 4: The synopsis of the film

URL action: Takes you the IMDb page of the film (this is set up on the dashboard not the worksheet)

Tooltip setup

I hope you can use these tooltip formatting options in your work because tooltips deserve to be beautiful too.
