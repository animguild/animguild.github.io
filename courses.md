---
layout: page
title: Courses
---
{% assign sorted_courses = site.courses | sort:"weight" %}

<div class="title">Courses</div>

<section class="list">
    <div class="block-grid">
        {% for course in sorted_courses %}
            <a href="{% if course.externalLink %}{{ course.externalLink }}{% else %}{{ site.url }}{{ course.url }}{% endif %}" class="item item--{{ course.imageSize }}" style="background: url('{{ course.image }}'); background-size: cover; background-position: center;">
                <div class="item-details">
                    {{ course.title }}
                    <div class="item-tags">
                        {% if site.show-tags %}
                            {% for tag in course.tags %}
                                <span class="item-tag" href="{{ site.url }}/tags/#{{ tag | slugify }}">{{ tag }}</span>
                            {% endfor %}
                        {% endif %}
                    </div>
                </div>
            </a>
        {% endfor %}
    </div>
</section>
