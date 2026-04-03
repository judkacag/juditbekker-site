---
title: "I dared to make a map"
date: "2020-11-08"
url: "https://www.juditbekker.com/post/i-dared-to-make-a-map"
---

On Friday, Steven Shoemaker dared me to make a map-centered viz. It was like he’s reading into me. I haven’t created a map so far because every time I tried, I realized how much I suck at it. But after I saw Jonni Walker’s Mapbox tutorial, I had the feeling that I can at least copy what he did there, and that’s a great starting point. As I’m a big procrastinator, I let it sleep on my to-do list for a good six months until I decided to give it a try. On Friday afternoon – what a coincidence! When I saw what Stephen challenged me with, I thought it’s going to be okay. And when I realized how big a step this is out of my comfort zone, I started panicking. This is the viz I put together – read on to feel my struggles, and check out the interactive version on Tableau Public.

Final visualization in Tableau

What is #DataDare?

Zach Bowders (who else) came up with the idea to create a dataviz chain letter by daring each other. It started with the three of us, Zach dared Steven, Steven dared me, and I dared Zach to make something new. After posting our visualization, we can challenge someone else from the Tableau community to keep the game alive. I wonder if I was too hard on Zach with the task to make a viz that looks like it’s from the 19th century, but I’m quite sure he can manage this. He explained the mechanism of #DataDare in a tweet – go check it out.

Phase 1: Panicking

Where to start? I had no clue. No idea, no dataset, no design inspiration. Nothing. I turned to the datafam to spoil me with some great examples, so if you’re planning to make a map, this is a thread to follow. We were avoiding each other for such a long time with Mapbox that the only thing I was sure of is the tool. So I opened the studio and had some desperate efforts at making something that makes me feel satisfied.

Too colorful, too busy, too vivid – they are not my style. Not to speak about the fact that I didn’t manage to make a seamless pattern as a background. And again, I didn’t have the data to adjust the style of the map. So I decided to take a U-turn and find something that I like and then search for data. That’s how I picked Iceland! I made an infographic about the country a few years back, and I’m fascinated by the Icelandic landscape (on my travel bucket list for a long time), so the most obvious choice was: volcanos.

Phase 2: Styling for data

I wanted to achieve a subtle look that the volcanos would shine through. In the end, I only used a few layers within Mapbox to have my final look. I had a bright grey background, added the ‘mapbox-terrain-rgb’, the landcover, the contour, and a couple of hillshade layers. As Jonni pointed out in his webinar, I duplicated the hillshade layer a couple of times and shifted them to make the shadow effect visible.

Iceland in Mapbox Studio

Phase 3: Gathering the data

At first, I thought it would be the easiest part of the process. I found a website where there was a list of all the volcanos with a lot of additional data. I collected the data manually, which took like 1.5 hours, but then came the surprise. Tableau showed an entirely different picture of the location of the volcanos than the map on the page (as if they were shifted 20 pixels in a random direction). That’s when I realized that the coordinates were wrong, and I had to search for them one by one.

Phase 4: Styling in Tableau

Finally, the fun part! I had this idea to use a buffer calculation for the first time to show a 20 km distance around the crater of the volcanos. I converted the locations to points so that I could make the buffer calculation and switched them to shapes that showed tiny fires. I toned down the colors by decreasing the opacity. I then created a dual-axis map to visualize both, and there it was. Since it was the first time for a lot of things, I decided to add a parameter action to show the names of volcanos on hover.

Points and buffers in Tableau

Phase 5: Unexpected errors and exporting SVG images

At first, I thought I’d make the background of the map transparent and then add the texts to the canvas as I always do. But even though all the colors were turned off, when I created the dual axis map, row-band-like lines showed up on the chart. I tried to get rid of them for hours without any success. So I decided to add a background color to the map (which miraculously made the lines disappear) and do something with my image that I intended to use as the first layer that shows under the transparent chart. The solution was to add the texts and labels as SVG so that the quality won’t get crappy.

To do that, I had to expand all the texts so that the export would look as it should. As always, I used Adobe Illustrator to design my elements. You can find the Expand option under Objects, and this is what you should do:

Expand appearance in Illustrator

I tried several SVG export options, but in the end, this was the one working fine for me. If you add your text and visual elements as a picture in Tableau, this is the way to keep them as sharp as they can be.

SVG export option in Illustrator

I hope you enjoyed this blog post and found some useful things in it. Tune in for more!
