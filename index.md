---
layout: default
title: Home
---

<section class="hero">
    <div class="container">
        <h1 class="hero-title">Air Quality Science and Policy Analysis</h1>
        <p class="hero-subtitle">
            Turn air pollution science into policy action | Advising authorities and governments
        </p>
        <a href="{{ '/blog/' | relative_url }}" class="btn">Explore Our Blog</a>
    </div>
</section>

<section class="container">
    <h2 style="text-align: center; margin-bottom: 2rem;">Latest Articles</h2>

    <div class="blog-grid">
        {% for post in site.posts limit:6 %}
        <div class="blog-card">
            <div class="blog-card-meta">
                <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
                {% if post.categories %}
                <span class="separator">•</span>
                <span>{{ post.categories | join: ', ' }}</span>
                {% endif %}
            </div>
            <h3 class="blog-card-title">
                <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            </h3>
            <p class="blog-card-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
            <a href="{{ post.url | relative_url }}" class="read-more">Read more →</a>
        </div>
        {% endfor %}
    </div>

    <div style="text-align: center; margin-top: 2rem;">
        <a href="{{ '/blog/' | relative_url }}" class="btn">View All Posts</a>
    </div>
</section>

{% include newsletter.html %}
