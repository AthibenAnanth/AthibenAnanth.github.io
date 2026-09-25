---
layout: post
category: F1 Telemetry Analysis
title: Custom F1 Telemetry analysis tool using FastF1 Database
description: A dashboard built with Streamlit and Plotly to translate raw FastF1 data into insights on vehicle dynamics, track dominance, tire degradation etc.
image: /assets/images/f1_telemetry.png
---

### The Objective

I enjoy watching Formula 1 and the technical side of things always interests me, I actively look out for telemetry in the live broadcast and post race analysis available online in multiple forms. This got me thinking, could i make a tool that can help me retrieve and visualize data for me to understand. 

### The Code Architecture:

- Framework and UI: I used streamlit for this, it was relatively easier to understand and gave very clean lookign UIs.
- Data & processing: I looked at many sources for data, after a little bit of research i was left with 2 options, FastF1 and OpenF1, I decided to use FastF1 mainly because I wanted to be able to run the project offline with cached data instead of API calls, I would have loved to have access to live telemetry during the race but OpenF1 restricts the number of calls per min on the free plan.
- Visualization: Using Plotly I was able to make graphs and other data visualization techniques. 

### The Analytical Modules

For ease of programming, each major statistic was made into its own "Module", thus far I have implemented 5 Major modules, these cover a wide array of data from lap by lap data to race pace and stint data. 

- Module 1: Lap telemetry and time delta mapping:
- This module focuses mainly on comparison of basic telemetry like speed, brake %, throttle % etc, this data is visualized with plots against time to clearly observe how it varies thru a lap. The extreme values are also shown to get a idea of the range.A calculated statistic from this would be the plot of time delta across a lap. I can analyze up to 6 different laps from any session any driver simultaneously,  this helps visualize how factors like driver confidence, set up changes etc effect lap time across sessions.  ![](/assets/images/nor_vs_ant_SPA_Q.png "Ananlysis of Norris's and Antonelli's qualifying laps in Q3 of the new spanish grand prix where norris almost lost a huge 0.35+s lead in the last corner leading to a final delta of just 0.011s")
- Module 2: Track dominance:
    - I've always looked at the track domination images, especially in 26, we can clearly see how dominant Ferrari are in the corners due to a superior chassis yet they loose out on straight line power to Mercedes due to a weaker power unit.
    - The script calculates the highest average speed in each sector and maps the dominant driver to the geometric track layout, instantly highlighting which car favors high-speed corners versus heavy traction zones.
    - This also lets us visualize how much the drivers are pushing and at what location are they most comfortable in doing so.
- Module 3: Track Position across lap: 
    - This module takes GPS coords and maps it across the lap, this is very useful to check visually which driver is ahead where and where the driver is loosing most of their time to their rivals.
    - Since we can control the time along the lap, we can freeze it at any point and check out the difference between the laps. 
- Module 4: Advanced Lap & Corner Metrics:
    - This section is probably the most fascinating, it gives us a deeper look into the lap by lap differences. It also shows basic lap and tyre data like compound, tyre life, sector times etc. 
    - Each lap has a detailed breakdown, this includes statistics like:
        - Apex speeds at different corners
        - Time to 100% throttle
        - Total time spent braking
        - Avg L&C time ( transition btwn braking and trottle)
        - Max & Min recorded speed
    - It also shows a 0-200 time for starting laps, this was very useful to visualize the superior starts by Ferrari due to a smaller turbo and faster spool up time which gave them very good speeds into turn 1.
- Module 5: Race pace and tyre deg:
    - This section mainly focuses on long sting data, it shows me a scatter plot of laptime vs lap number which allows us to see progression in laptime as tyres die out or as fuel level drops.
    - It also gives us an idea on how much compromise a team took for race pace over 1 lap qualifying pace.

### My learning:

- This project was a deep look into how engineers optimize a "set up". It gave me a good understanding on how to spot differences as well as theorize on possible causes.
- It also gave me experience working with data and how to visualize it. Even tho majority of the project was vibe coded, i spent a good amount of time debugging plots and understanding how to read it. 
- Overall I still use it to compare driver and car differences to see where my favorite teams lack or gain.
