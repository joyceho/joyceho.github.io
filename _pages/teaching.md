---
layout: page
permalink: /courses/
title: courses
semesters: [Fall 2019, Fall 2018, Spring 2018, Fall 2017, Spring 2017, Spring 2016]
nav: true
---

{% for y in page.semesters %}
  <h3 class="semester">{{y}}</h3>
  <ul>
    {% for course in site.courses %}
        {% if course.semester == y %}
            <li><a href="{{ course.url | prepend: site.baseurl | prepend: site.url }}">{{ course.title }}</a></li>
    {% endif %}
    {% endfor %}
   </ul>
{% endfor %}