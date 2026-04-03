---
title: "How to start building a new dashboard for clients?"
date: "2020-11-05"
url: "https://www.juditbekker.com/post/how-to-start-building-a-new-dashboard-for-clients"
---

I collected all the questions that in a dream world I’d like to get answers to before start building a dashboard. I divided them into four sections (technical setup, purpose, audience, and development) and included a one-pager of the blog post. Without knowing these, for me, it’s just pure luck if I can calculate the effort right.

One-pager

Technical setup

Which Tableau Desktop / Server version you are using?

Some features won’t work in older versions, so it’s good to know that you have to make a dashboard in 10.5 before you add tons of parameter actions to it. Exporting to older versions can cause inconveniences as well – especially since the introduction of the new logical layer in the data model – that might result in some back and forth troubleshooting emails with your client.

What is the data source, and how many data sources you have?

Always ask for examples/extracts from the data to see what you have to deal with. Sometimes you hear it’s just 2 Excel files, and you feel ‘okay, that shouldn’t be a big deal’. But what if those 2 Excel files contain 35 sheets? Or it turns out that the two files don’t have any fields in common, so there’s no way to connect them. This step can save you both money and time, especially if you’re working on a fix-priced project.

What kind of data do you have?

It is crucial to see if you have to work with financial, survey, CRM, or any other type of data. For example, if you have to build a dashboard from raw survey data, 99% of the time it requires data preparation. And it requires a lot. When writing offers, always make sure to scale your hours according to the time you have to spend on the ETL process, not just the hours you need to build the dashboard.

Does it require additional data preparation?

If yes, it’s important to see your options in terms of tools you can use to accomplish the project. Let’s state that you can build a prep flow in Alteryx within a day. Seems fine if this is a one-time thing. But what if the client wants to refresh the data every week and they don’t have an Alteryx license? In this case, you might need to select from the tools they have or use open-source software. Again, this can take extra time because of two things: you either have to choose an option that you’re not used to and/or some steps are more complicated to add than in your go-to tool.

Do you require written documentation of the development?

It’s worth discussing before the project because writing documentation takes hours, and you should know if it’s needed to estimate your efforts better.

How many dashboards are you planning to have in the course of this project?

Sometimes clients don’t know the difference between a dashboard and a workbook. And this is not their fault, since in one BI tool, it means this, and in another, it means that. If you don’t want to be surprised and build ten dashboards for the price of one, you might want to clarify this before jumping into dashboard development.

Purpose

What are the questions you would like to get answers to?

This point is the most important thing to clarify before even drawing the wireframes. You have to know what they are curious about to make your visualization ‘storyboard’. Of course, the client will say everything is important, but we have to define critical questions and prioritize them.

What are the success criteria?

Think about the business goal that you want to achieve and how to measure success.

What is the purpose of the dashboard?

You have to use completely different narratives if the dashboard is for weekly sales monitoring or if you want to prepare an important decision. If you analyze the suggested price reduction of a given product, you need to build your visualization around that issue. It means using annotations, story points, and text containers to back up your suggestion. On the other hand, for a monitoring dashboard, you would like to put together something general that would stand the test of time and always show those 3 KPIs and trendlines.

Is the dashboard based on new requirements, or it will replace an existing report?

If it will replace an existing report, it’s worth digging into the old one. What are the good elements? What can be improved? Can the logic be replicated in Tableau, or do you need some adjustments in the data layer?

Define the key performance indicators and the insights you want to highlight.

How do you want to use the dashboard?

You have to build something entirely different if all the employees would access the dashboard on their Tableau Server, or if they would print it to PDF to circulate within the company. In this case, you have to put together a narrative that would make sense even without interactivity.

Audience

Who will be the audience of the dashboard?

Different consumers require different levels of detail. Imagine a manufacturing company, where the CEO would only like to have a look at the main KPIs, while an operations manager  wants to know which lines are underperforming to make adjustments. User stories can help defining the flow of the dashboard.

Do you want to create personas for different roles or one-site-fits-all?

If we want to create three personas (C-level, manager level, operations), how do we want to achieve it? By making multiple dashboards, or by making just one and apply drill-down functions, show & hide containers and other solutions to put together a top-down analysis?

Development

Should it fit on the screen, or can we enable scrolling? Do you need device optimization?

This point is crucial in the layout planning phase if you don’t want to rebuild the dashboard multiple times. When there’s a story to tell in the viz, you have to know where it’s best to break it if the client wants to avoid scrolling. This is also the step where you should ask whether you have to optimize the dashboard for tablet, mobile, etc.

Do you have your own font and color choices?

If yes, make sure the client sends their brand guidelines.
