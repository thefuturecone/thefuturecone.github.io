---
layout: page
title: Blog
---

<ul style="list-style: none; margin-left: 0; padding-left: 0;">
  {% for post in site.posts %}
    <li style="margin-bottom: 60px; list-style: none;">

      <!-- Title -->
      <h2 style="margin-bottom: 5px;">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>

      <!-- Date -->
      <p style="color: #666; font-size: 0.9em; margin-top: 0; margin-bottom: 10px;">
        {{ post.date | date: "%b %d, %Y" }}
      </p>

      <!-- Excerpt -->
      <div style="margin-top: 10px; margin-bottom: 15px; color: #333; line-height: 1.6;">
        {{ post.excerpt | strip_html | truncatewords: 25 }}
      </div>

      <!-- Tags -->
      {% if post.tags %}
        <div style="font-size: 0.85em; color: #555; margin-top: 15px;">
          📁 Tags:
          {% for tag in post.tags %}
            <a href="{{ '/archive.html' | relative_url }}#{{ tag | slugify }}"
               style="background: #f0f0f0; color: #333; padding: 3px 8px; border-radius: 4px; margin-right: 6px; display: inline-block; text-decoration: none;">
              {{ tag }}
            </a>
          {% endfor %}
        </div>
      {% endif %}

    </li>
  {% endfor %}
</ul>
