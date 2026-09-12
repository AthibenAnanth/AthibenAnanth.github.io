---
layout: landing
title: F1 Data Science
description: "Mining telemetry for the tenth of a second."
image: assets/images/f1_telemetry.jpg
permalink: /f1-data/
---

<div id="main">
    <section id="one">
        <div class="inner">
            <header class="major">
                <h2>Telemetry & Performance Analytics</h2>
            </header>
            <p>Using the FastF1 and OpenF1 APIs, I develop Python-based tools to analyze lap times, tire degradation, and throttle/brake application. My goal is to translate raw sensor data into actionable race strategy insights.</p>
        </div>
    </section>

    <section>
  <div class="inner">
    <h2>Recent Telemetry Analysis</h2>
    <div class="posts">
      {% for post in site.posts %}
        {% if post.category == 'F1 Telemetry Analysis' %}
          <article>
            <header>
              <h3><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3>
            </header>
            {% if post.image %}
              <a href="{{ site.baseurl }}{{ post.url }}" class="image fit"><img src="{{ site.baseurl }}{{ post.image }}" alt="" /></a>
            {% endif %}
            <p>{{ post.description }}</p>
            <ul class="actions">
              <li><a href="{{ site.baseurl }}{{ post.url }}" class="button">Read More</a></li>
            </ul>
          </article>
        {% endif %}
      {% endfor %}
    </div>
  </div>
</section>
</div>
