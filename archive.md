---
layout: page
title: Tags
permalink: /archive.html
---

<div class="tag-cloud" style="margin-bottom: 40px; line-height: 2;">
  {% assign sorted_tags = site.tags | sort %}
  {% for tag in sorted_tags %}
    {% assign tag_name = tag[0] %}
    {% assign tag_posts = tag[1] %}
    <a href="#{{ tag_name | slugify }}" style="background: #2a7ae2; color: white; padding: 5px 10px; border-radius: 4px; margin-right: 5px; text-decoration: none; display: inline-block; font-size: 14px;">
      {{ tag_name }} ({{ tag_posts.size }})
    </a>
  {% endfor %}
</div>

<hr>

{% for tag in sorted_tags %}
  {% assign tag_name = tag[0] %}
  {% assign tag_posts = tag[1] %}
  <div id="{{ tag_name | slugify }}" class="tag-section" style="margin-bottom: 30px;">
    <h3 style="border-bottom: 1px solid #ccc; padding-bottom: 5px; color: #2a7ae2;">
      Entries tagged with "#{{ tag_name }}"
    </h3>
    <ul>
      {% for post in tag_posts %}
        <li style="margin-bottom: 10px;">
          <span style="color: #999; font-size: 14px; margin-right: 10px;">{{ post.date | date: "%b %d, %Y" }}</span>
          <a href="{{ post.url | relative_url }}" style="font-weight: bold;">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  </div>
{% endfor %}
