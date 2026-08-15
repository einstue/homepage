---
layout: default
title: Blog
permalink: /blog/
---

<section class="page-intro">

    <h1>Blog</h1>

    <p class="intro-copy">
        Notes on physics and mathematics
    </p>

</section>

<section class="blog-list">

    {% for post in site.posts %}

    <article class="blog-entry">

        <p class="blog-meta">
            {{ post.date | date: "%B %-d, %Y" }}
            {% if post.category %}
            · {{ post.category }}
            {% endif %}
            {% if post.level %}
            · {{ post.level }}
            {% endif %}
        </p>

        <h2>
            <a href="{{ post.url | relative_url }}">
                {{ post.title }}
            </a>
        </h2>

        {% if post.description %}
        <p class="blog-excerpt">
            {{ post.description }}
        </p>
        {% else %}
        <p class="blog-excerpt">
            {{ post.excerpt | strip_html | truncatewords: 30 }}
        </p>
        {% endif %}

    </article>

    {% endfor %}

</section>