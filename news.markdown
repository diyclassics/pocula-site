---
layout: page
title: News
permalink: /news/
---

<div class="news-container">
  <h1>Latest News</h1>

  {% assign news_posts = site.posts | where_exp: "post", "post.tags contains 'news'" %}

  {% if news_posts.size > 0 %}
    <div class="post-list">
      {% for post in news_posts %}
        <div class="news-item" style="margin-bottom: 1.5rem;">
          <h3 style="margin-bottom: 0.1rem;">
            <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
          </h3>
          <span class="post-meta" style="display: block; margin-bottom: 0.3rem; font-size: 0.9rem;">{{ post.date | date: "%B %-d, %Y" }}</span>
          {% if post.excerpt %}
            <div class="post-excerpt" style="margin-top: 0.2rem;">
              {{ post.excerpt }}
              <a href="{{ post.url | relative_url }}" class="read-more">Read more...</a>
            </div>
          {% endif %}
        </div>
        {% unless forloop.last %}
          <hr style="border: 0; height: 1px; background-color: #e8e8e8; margin: 1.5rem 0;">
        {% endunless %}
      {% endfor %}
    </div>
  {% else %}
    <p>No news articles available at this time.</p>
  {% endif %}
</div>
