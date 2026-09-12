---
layout: landing
title: CAD & Robotics
description: "Exploring the limits of geometry through implicit modeling and solo robot builds."
image: assets/images/robotics_bg.jpg
permalink: /cad-robotics/
---

<div id="main">
    <section id="one">
        <div class="inner">
            <header class="major">
                <h2>Implicit Design & Combat Robotics</h2>
            </header>
            <p>This section documents my work in advanced CAD methodologies—specifically focusing on <b>nTop</b> for lattice structures and generative design—alongside my journey in building solo combat robots for the Indian circuit.</p>
        </div>
    </section>

    <section id="two" class="spotlights">
        {% for post in site.posts %}
            {% if post.category == 'CAD and Robotics' %}
            <section>
                <a href="{{ post.url | relative_url }}" class="image">
                    {% if post.image and post.image != "" %}
                    <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" data-position="center center" />
                    {% else %}
                    <!-- Fallback image if you forget to upload one in the CMS -->
                    <img src="{{ '/assets/images/robotics_bg.jpg' | relative_url }}" alt="Default" data-position="center center" />
                    {% endif %}
                </a>
                <div class="content">
                    <div class="inner">
                        <header class="major">
                            <h3>{{ post.title }}</h3>
                        </header>
                        <p>{{ post.description }}</p>
                        <ul class="actions">
                            <li><a href="{{ post.url | relative_url }}" class="button">Read Project</a></li>
                        </ul>
                    </div>
                </div>
            </section>
            {% endif %}
        {% endfor %}
    </section>
</div>
