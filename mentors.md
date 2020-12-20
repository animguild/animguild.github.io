---
layout: page
title: Mentors
---
{% assign sorted_mentors = site.mentors | sort:"weight" %}

<div class="title">Mentors</div>

<section class="list">
    <div class="circular-grid">
        {% for mentor in sorted_mentors %}
            <a href="{% if mentor.externalLink %}{{ mentor.externalLink }}{% else %}{{ site.url }}{{ mentor.url }}{% endif %}" class="item">
                <div class="item-image-container">
                    <img class="item-image" src="{{ mentor.image }}" alt="mentor image"/>
                </div>
                <div class="item-details">
                    <span class="item-title">{{ mentor.name }}</span>
                    <div class="item-tags">
                        {% if site.show-tags %}
                            {% for tag in mentor.tags %}
                                <span class="item-tag tag-{{ tag | downcase }}" href="{{ site.url }}/tags/#{{ tag | slugify }}">{{ tag }}</span>
                            {% endfor %}
                        {% endif %}
                    </div>
                </div>
            </a>
        {% endfor %}
    </div>
</section>
