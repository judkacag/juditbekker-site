---
title: "The Man from New York"
date: "2020-09-22"
url: "https://www.juditbekker.com/post/the-man-from-new-york"
---

An unpopular opinion, but I was raised never to feel ashamed of the things I love. So here it is: I love Woody Allen. For me, he’s one of the most talented, intelligent, and funniest people of our century. When I was little, I told my parents that I wanna be Woody Allen when I grow up (still better than my brother who collected keychains because he wanted to be a burglar). I saw almost all of his movies, Manhattan alone 10+ times, and I don’t think I’ll ever get bored with it. The idea to make a visualization of his filmography was on my table for a long time, but I finally had the motivation to put it on the canvas. You can have a look at the interactive version on my Tableau Public profile.

Final design in Tableau

I wanted to make a bar chart of Manhattan inside his iconic glasses of the IMDB scores of his films. At first, I drew the glasses in Illustrator with the help of the pen tool and cut the lenses out to make them transparent. As a next step, I downloaded the traditional font of his movies: Windsor Light Condensed.

Coloring the bar charts was fairly tricky, I had to categorize them into four categories to make the ones at the back the darkest, and the ones at the front the lightest. The original color I used was #282828 and I decreased the opacity of them by 2% to achieve this subtle difference. This was a fully manual data preparation work, no magic tricks there. As I made the lenses of the glasses transparent I just had to move the charts to the back.

Next, I exported the dashboard image as a png file and put it on my canvas in Illustrator on a separate layer and moved it to the background so that the charts would fall into their place. I drew the lightning windows and the moon over the bar charts and hid the dashboard image I exported before saving. I refreshed the background image in Tableau and the windows appeared on top of the bars. The only thing left was to duplicate the bar charts as a fully transparent version and send them to the foreground of the visualization to make to tooltips work.
