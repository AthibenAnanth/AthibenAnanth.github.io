---
layout: landing
title: FEA & Structural Analysis
description: "Validating structural integrity through transient and static finite element methods."
image: /assets/images/wheel_stress.jpg
permalink: /fea-hub/
---

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
                <a href="{{ site.baseurl }}{{ post.url }}" class="image">
                    {% if post.image %}
                    <img src="{{ site.baseurl }}{{ post.image }}" alt="{{ post.title }}" data-position="center center" />
                    {% endif %}
                </a>
                <div class="content">
                    <div class="inner">
                        <header class="major">
                            <h3>{{ post.title }}</h3>
                        </header>
                        <p>{{ post.description }}</p>
                        <ul class="actions">
                            <li><a href="{{ site.baseurl }}{{ post.url }}" class="button">Read Deep Dive</a></li>
                        </ul>
                    </div>
                </div>
            </section>
            {% endif %}
        {% endfor %}
    </section>
</div>
