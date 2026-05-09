---
layout: page
permalink: /courses/
title: courses
nav: true
nav_order: 6
course_groups:
  - id: "CS 171"
    title: "CS 171 - Introduction to Computer Science II"
    description: "Data structures, algorithm analysis, and object-oriented design in Java."
    semesters: ["Spring 2022", "Fall 2021", "Fall 2017"]
  - id: "CS 334"
    title: "CS 334 - Machine Learning"
    description: "Fundamentals of statistical machine learning with real-world applications."
    semesters: ["Spring 2024", "Fall 2023", "Fall 2019"]
  - id: "CS 377"
    title: "CS 377 - Database Systems"
    description: "Relational databases, SQL, query optimization, and database design."
    semesters: ["Fall 2021", "Spring 2018", "Spring 2017", "Spring 2016"]
  - id: "CS 534"
    title: "CS 534 - Machine Learning"
    description: "Graduate-level machine learning theory, algorithms, and applications."
    semesters: ["Fall 2023", "Fall 2018", "Fall 2017", "Spring 2017"]
  - id: "CS 584"
    title: "CS 584 - Big Data Analytics"
    description: "Methods and tools for analytics on large-scale datasets."
    semesters: ["Spring 2016"]
---

<div class="row row-cols-1 row-cols-md-2">
  {% for group in page.course_groups %}
  <div class="col mb-4">
    <div class="card h-100 hoverable">
      <div class="card-body">
        <h5 class="card-title">{{ group.title }}</h5>
        <p class="card-text text-muted">{{ group.description }}</p>
        <div class="mt-auto pt-2">
          {% for sem in group.semesters %}
            {% assign matched = site.courses | where: "semester", sem %}
            {% assign course_page = nil %}
            {% for c in matched %}
              {% if c.title contains group.id %}
                {% assign course_page = c %}
              {% endif %}
            {% endfor %}
            {% if course_page %}
              <a href="{{ course_page.url | relative_url }}" class="badge badge-pill badge-light border mr-1 mb-1" style="font-size: 0.8rem; font-weight: normal;">{{ sem }}</a>
            {% else %}
              <span class="badge badge-pill badge-light border mr-1 mb-1" style="font-size: 0.8rem; font-weight: normal;">{{ sem }}</span>
            {% endif %}
          {% endfor %}
        </div>
      </div>
    </div>
  </div>
  {% endfor %}
</div>
