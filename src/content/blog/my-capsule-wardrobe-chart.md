---
title: "My Capsule Wardrobe Chart"
date: "2024-12-10"
url: "https://www.juditbekker.com/post/my-capsule-wardrobe-chart"
---

Cheers to this recently finished dataviz project that I should've given up on four days after starting it, but I didn't because I'm a stubborn doer. I had the idea to visualize what I wear for a month, and I had slightly different expectations in terms of a lot of things. First of all, I always knew that my sock game is good, but I had no clue that my choices of color are THAT BORING. On the other hand, I try to be more conscious when I buy new clothes (or usually secondhand) and ask myself if I really need this piece and would wear it on a regular basis. At least seeing how many times I put on the same clothes gives comfort, and I can proudly say: I'm very much an outfit repeater!

My biggest struggle, though, was the effort this project needed. I pulled off some really long-term projects in the past (like logging everything I watched for a year), but the complexity was never so high. Every time I changed shoes, went out, or took off a sweater because I was hot, it meant a new outfit.

Here’s the final visualization! Check out the interactive version on Tableau Public. If you’re feeling inspired to whip up something similar or just want to put together a mekko chart, you can also download the workbook.

The final version of the visualization

This year taught me how important pen & paper notes are in my life. They are not only good for ranting and venting, but also for planning purposes, gathering ideas, and keeping myself accountable. I started a dataviz journal to jot down my thoughts, possible projects, design ideas, and just to have somewhere to sketch. This is exactly how this visualization came to life as well.

Establishing my wardrobe rules

Based on my initial sketches, I decided that the width of the bar would be the number of hours I wore that outfit, and the height would always add up to 100, divided by the following: 10 feet, 45 lower body, 45 upper body. It seemed super straightforward, but then I started to have questions. What if I wear a longer sweater? What is the color of a T-shirt when it's colorful? Or if I opt for layers one day and wear a shirt over a tank top? This is where I had to establish some rules and curb my overthinking:

One color to rule them all: choose the dominant color and forget about the rest.

Only the clothes that are visible count.

If there's visible layering, then the upper body number can be further divided based on the dominant colors.

In case I own multiple pieces of the same clothing, those have the same ID.

When the upper clothes "cut into" the lower ones (e.g., wearing a dress or a longer sweater), it can eat into the 45 set aside for the lower body.

Tracking hours are between getting out of bed and getting into bed (side note: all my pajamas are black anyway, so we didn't lose anything in terms of colors with this limitation).

Feet are always 10; when I wear shoes, then 5-5 goes to the shoes and the socks. When I'm inside, it's 10 for the socks.

The HEX codes of each piece are taken from the pictures of the clothes, apart from the black and white ones that are uniform (call me crazy, but I do have a Pinterest board with most of my wardrobe uploaded, so this wasn't too much of an effort).

Enlarged instructions on how to read the chart - and to illustrate the rules I set for myself

My very 2024 Clueless-style Pinterest board where I store almost my entire wardrobe
Data collection

I knew from the very beginning that I wanted the main chart to be a Marimekko or a Mosaic plot (the one that seems like a bar chart, but on top of the x and y values it has a size attribute as well), but I didn't expect it to be such a pain in the ass to create and maintain on the data side. I had three tabs in Google Sheets: an inventory of clothes, a weather register, and a change tracker. Logging data to the first two was a piece of cake, but the tracker caused a lot of headaches. I'm sure there would've been a better way to structure and enter the data, but when it finally worked, I was too happy to question it, and then I was too deep in it already. This is how it looked in Google Sheets; imagine you realize at Change ID 82 you made a mistake in Change ID 4 and it all trickles down (yes, this happened multiple times).

Change tracker in Google Sheets

Would I recommend anyone to follow suit and complete a similar project? Absolutely not, I'd rather count all my hairs than do this again.

Wardrobe insights

During these 4 weeks from November 11 to December 8, I changed outfits 121 times and wore 55 different pieces of clothing. It came as no surprise that my most preferred colors were black and grey, and also that I spent the most time in jogging pants. Three items in my top 10 were clothes I wear exclusively at home.

Week 1

This was my most colorful week, likely due to spending more time at home and the fact that my colorful clothes are mostly jumpers. My top items were a khaki jumper (50 hours) and a new Twin Peaks sweater (44 hours). The week’s highlights included seeing Pelikan Blue at the movies, discovering Jess Damuck’s Morning Glory Muffins, and making my second batch of kimchi (while rocking my kimchi socks!).

Week 2

I spent two days in the office this week, and even though I tried to lift my mood on Tuesday by dressing up, the nonstop rain all day had other plans. We had a team offsite on Thursday, and some friends stayed over for the weekend. As for clothing, the lineup was more balanced than last week: grey Levis sweater (28 hours), grey jogging pants (27 hours), black H&M sweater (26 hours), and stone-washed Reserved jeans (26 hours).

Week 3

This is when everything started turning black, and the Berlin winter somehow felt more cheerful than my outfits. Week 3 was busier than ever - I watched The Conclave at the movies, had a cooking day at the office, and visited a Christmas market. It was a bit of a shock to see that my number one item was my black Vans shoes (33 hours), but my trusty khaki jogging pants (32 hours) made a strong comeback after their week off, along with my favorite black sweater (26 hours).

Week 3

This is when everything started turning black, and the Berlin winter somehow felt more cheerful than my outfits. Week 3 was busier than ever - I watched The Conclave at the movies, had a cooking day at the office, and visited a Christmas market. It was a bit of a shock to see that my number one item was my black Vans shoes (33 hours), but my trusty khaki jogging pants (32 hours) made a strong comeback after their week off, along with my favorite black sweater (26 hours).

Week 4

In the final week of the outfit tracker project, I spent nearly two-thirds of my waking hours outside of home. Which, let’s be honest, is pretty wild. I went to the office two days in a row, all while daydreaming about testing out my new stand mixer (an early Christmas gift). On Saturday, we set out on a mission to find the best Panettone in Berlin - and ended up buying four. But don’t be fooled, the real MVP this week was my grey jogging pants (31 hours).

Design process

Finally, here's a part of the project that felt super easy!

I knew from the start that there would only be one chart on this dashboard that I'd make the star of the show. There was no other way around it anyway, since this ended up more colorful than all of the visualizations I did in the past 8 years altogether (which is very unlike me). Nevertheless, I didn't want to overdo it even more, and since I saw day after day how this chart was getting built, by the time I was ready to finish the project, I had the whole idea laid out in my mind, just needed time to put it onto the canvas.

I'm generally pleased with how this project turned out, but I still regret wearing purple socks one day, which threw off the color palette for me. Tune in for my next viz that is already in the works! Until then: have fun, and dress warmly!
