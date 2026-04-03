---
title: "Happy Women’s Day!"
date: "2021-03-08"
url: "https://www.juditbekker.com/post/happy-women-s-day"
---

I’m lucky enough that I never felt less than a man and experienced no discrimination in any areas of life. I know it’s not the case for all women. Focusing on the negative aspects is always more shocking and eye-catchy, but I’m so in for good vibes! I chose to celebrate the 2021 International Women’s day with a positive story. Did you know that almost half of the commissioners of the European Commission are female? That was not always the case, and it’s great to see politicians start dealing with such an important topic by setting an example.

José Manuel Barroso stated in 2004 that he wants to increase the ratio of women in his cabinet to 33% – which he managed to achieve. Fifteen years later, Ursula von der Leyen pledged to put together the most gender-diverse team in EC history. And this is where we are now: 13 female and 14 male commissioners.

You can check out the interactive version on Tableau Public and read on for the technical stuff if you’re interested.

Final design in Tableau Public

The inspiration behind the design

Last week was my first one at my new job, and I was so tired every day that I felt I won’t ever have the energy to make visualizations for fun again. I scheduled a lot of to-do-s for the weekend and ended up doing none of them. Saturday night, I saw this editorial design on Pinterest, and I had the idea to jump on the bandwagon and make a viz for Women’s Day.

To achieve the same fading effect, search for a photo where the subject stands out from a more or less seamless background. That is the ideal setup for masking in Photoshop – or at least the easiest. I found the above pic on Pexels by Maksim Goncharenok. There’s a blog post I wrote some month ago about layering in Tableau where I explained masking. Check it out if you want to try it out yourself.

The three women on the canvas are just duplications of the original png image with a lower opacity score, but there are a couple of options (Appearance / Opacity) you can play with. I chose to multiply them, but there are so many ways to go. What looks good depends on the effect you desire to achieve and the image you’re working with. There are no best practices here, just trials & errors – and hopefully some successes at the end. My example image has a 100% opacity version and a duplicate on top of it with 80% opacity. Sometimes the difference between versions is barely visible. Here are all the opacity options available in Adobe Illustrator:

Different opacity options in Illustrator

I hear a lot of people complaining about image quality when they are adding them to Tableau. No matter how big a resolution you choose, it seems blurry. When I’m adding backgrounds, I go on total autopilot and just fit & center the image. It might just be me, but my background picture was the same size as the dashboard, and when I accidentally skipped the fit & center menu, it seemed way sharper than before. You might want to give this a try if the quality seems off.

A bumpy ride with the curved area chart

I spent a good 6 hours on this visualization as I was trying to add the curved area chart, but it was not showing what it would suppose to show. I followed Toan Hoang’s tutorial, which was a great starting point, but I had to tweak it a little to get what I wanted. Here are a couple of things I learned during the process:

This method is not working with dates (x-axis), not even discrete ones, so I had to convert them to strings to get the right numbers.

I wouldn’t like my first year to start from 0, which would have been misleading, and I wanted to show data from only 2003 anyway. Since the building tutorial is based on table calculations, I had to add the previous year to the view and hide (not exclude) it. With exclusion, the first entry would have started from 0 again.

You can double-check with a simple line chart if the curved line looks as it should. That’s what I did, and I was surprised to see that it looks completely different. (And then started 2 hours of bug fixing…)

When I decreased the opacity of the area chart to 60%, thin lines started to appear. I realized this is because the segments overlap a bit. Toan suggests fixing the axis from -6 to 6, but I found mine to look the best from -5.55 to 5.55. Let me show you the difference:

Left: -6 to 6 axis, Right: -5.55 to 5.55 axis

Thanks for reading, tune in for more data adventures!
