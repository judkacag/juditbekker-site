---
title: "How to make a Saturn chart?"
date: "2021-09-25"
url: "https://www.juditbekker.com/post/how-to-make-a-saturn-chart"
---

There might have been a thousand tutorials about this chart but I was too lame to find them, so I came up with my own version. Here, I present you the Saturn chart. I’m almost sure this is not the most optimal solution and can be done with less effort but this suited my logic the best. Read on to the next section, where I break down the process step by step. You can have a look at the interactive version on Tableau Public and download the workbook to play with it.

Final visualization

Step 1: Setting up the data the right way

To check what happens through the movie, the first step was to create a line for every second. The same result can be achieved by a join but it made sense to me to save that step. The duration of the film is 2:05:01, so I ended up with 7507 lines of data (most of them empty). After this, I needed to come up with the events I wanted to track. I used four categories: singing, smoking, violence (sometimes called brutality), and sex. I assigned an index value to all the rows but made sure to add the same index for the same events. This way, I ended up with 7507 rows but only 7502 unique indexes. You can check my logic marked yellow in the table below:

Dataset filtered down to the rows where the ‘What’ field is not null

Step 2: Creating the calculations

I wanted the data to have a circular shape, so at first, I had to know how many pieces I need to ‘cut’ my circle into. I called this calculation densification, 7502 is the number of unique indexes I had. Again, this is something that could’ve been calculated and would’ve looked more elegant.

densification = (360-(7502/WINDOW_MAX(MAX([Index]))))/WINDOW_MAX(MAX([Index]))

Next, I made a Who (group) since I didn’t want all the characters displayed, and added a shape transform calculation to have only these categories visualized:

shape transform =
IF [What] = 'cigarette' and [Who (group)] = 'Lula' then 'Lula cigarette'
ELSEIF [What] = 'cigarette' and [Who (group)] = 'Sailor' then 'Sailor cigarette'
ELSEIF  [What] = 'cigarette' and [Who (group)] = 'Other' then 'Others cigarette'
ELSEIF [What] = 'sing' then 'sing'
ELSEIF [What] = 'brutality' then 'brutality'
ELSEIF [What] = 'sex' then 'sex'
END

I wanted the sing and cigarette events to appear on the main circle, while brutality and sex should have a bigger / smaller circle size. That’s where the radius calculation came into the picture.

radius =
IF [What] = 'sing' or [What] = 'cigarette' or [What] = NULL then 1
ELSEIF [What] = 'brutality' then 1.15
ELSE 0.85
END

This was followed by the x and y calculations that I’ll later add to my Columns and Rows shelves.

x = SIN(RADIANS(MAX([Index])*[densification]))*MIN([radius])
y = COS(RADIANS(MAX([Index])*[densification]))*MIN([radius])

The next trick I made is not best practice at all, but I imagined it this way. I intended brutality and sex events to have no size, while adding a SUM(duration) to the size of sing and cigarette. The below calculation seems like a made up mess, so let me explain. Even though sing and cigarette categories appear on the same circle, I wanted to make them independent by distorting the size. That’s why the size of sing events is 5 times bigger than cigarettes. The sizing difference between the two ‘no size events’ is only optical. I assigned rectangles to brutality and circles to sex, and circles appeared bigger than rectangles so I had to correct it.

second = DATEDIFF('second', [Time], [End])

duration transform =
IF MIN([What])= 'sing' then SUM([seconds])*5
ELSEIF MIN([What]) = 'cigarette' then SUM([seconds])
ELSEIF MIN([What]) = 'brutality' then 3
ELSE 2
END

Step 3: Table calculations

Here came the fun part! The only thing left was adding the right fields to the right marks and fine tuning table calculations. I placed duration transform to the size card, SECOND(Time), Who (group), and What to the Details, and shape transform to the Shapes card.

Right fields on the right marks

The x and y calculations are placed on Columns and Rows, and the table calculation should be set up this way:

Table calculation

Hope this tutorial helps you to create a chart similar to mine, in case you have any questions just drop me a message. I cover the design aspects of this visualization in a previous post.
