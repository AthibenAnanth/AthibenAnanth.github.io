---
layout: landing
title: F1 Data Science
description: "Mining telemetry for the tenth of a second."
image: assets/images/f1_telemetry.jpg
permalink: /f1-data/
---

<style>
  .spotlights > section > .image img {
    width: 100% !important;
    height: 100% !important;
    object-fit: cover !important;
    object-position: center center;
  }
</style>

<div id="main">
    <section id="one">
        <div class="inner">
            <header class="major">
                <h2>Telemetry & Performance Analytics</h2>
            </header>
            <p>Using the FastF1 and OpenF1 APIs, I develop Python-based tools to analyze lap times, tire degradation, and throttle/brake application. My goal is to translate raw sensor data into actionable race strategy insights.</p>
        </div>
    </section>

    <section id="two" class="spotlights">
        {% for post in site.posts %}
            {% if post.category == 'F1 Telemetry Analysis' %}
            <section>
                <a href="{{ post.url | relative_url }}" class="image">
                    {% if post.image and post.image != "" %}
                    <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" data-position="center center" />
                    {% else %}
                    <!-- Fallback image if you forget to upload one in the CMS -->
                    <img src="{{ '/assets/images/f1_telemetry.jpg' | relative_url }}" alt="Default" data-position="center center" />
                    {% endif %}
                </a>
                <div class="content">
                    <div class="inner">
                        <header class="major">
                            <h3>{{ post.title }}</h3>
                        </header>
                        <p>{{ post.description }}</p>
                        <ul class="actions">
                            <li><a href="{{ post.url | relative_url }}" class="button">Read Deep Dive</a></li>
                        </ul>
                    </div>
                </div>
            </section>
            {% endif %}
        {% endfor %}
    </section>
</div>
