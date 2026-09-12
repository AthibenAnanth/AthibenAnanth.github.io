---
layout: landing
title: FEA & Structural Analysis
description: "Validating structural integrity through transient and static finite element methods."
image: /assets/images/wheel_stress.jpg
permalink: /fea-hub/
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
                <h2>Predicting Failure, Ensuring Performance</h2>
            </header>
            <p>From automotive components at high RPM to civil engineering failure analysis, my work focuses on using Ansys and SolidWorks to simulate real-world physics. I specialize in transient structural analysis where time-dependent loads determine the longevity of a design.</p>
        </div>
    </section>

    <section id="two" class="spotlights">
        {% for post in site.posts %}
            {% if post.category == 'Engineering Project' %}
            <section>
                <a href="{{ post.url | relative_url }}" class="image">
                    {% if post.image and post.image != "" %}
                    <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" data-position="center center" />
                    {% else %}
                    <!-- Fallback image if you forget to upload one in the CMS -->
                    <img src="{{ '/assets/images/wheel_stress.jpg' | relative_url }}" alt="Default" data-position="center center" />
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
