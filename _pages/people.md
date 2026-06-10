---
layout: single
title: "People"
permalink: /people/
---

## Principal Investigator

<div class="person-card">
  <img src="/assets/img/headshot_small_23.png" alt="Duncan Callaway" class="person-photo">
  <div class="person-info">
    <h3><a href="https://erg.berkeley.edu/people/callaway-duncan/">Duncan Callaway</a></h3>
    <p class="person-role">Professor, Energy & Resources Group</p>
    <p>Research focuses on control, optimization, and analysis of electric power systems and distributed energy resources.</p>
    <p><a href="mailto:dcal@berkeley.edu">dcal@berkeley.edu</a></p>
  </div>
</div>

---

## PhD Students

{% assign phd_students = site.students | where: "role", "PhD Student" %}
{% for student in phd_students %}
<div class="person-card">
  {% if student.photo %}
  <img src="{{ student.photo }}" alt="{{ student.name }}" class="person-photo">
  {% else %}
  <img src="/assets/img/avatar-icon.png" alt="{{ student.name }}" class="person-photo">
  {% endif %}
  <div class="person-info">
    <h3><a href="{{ student.url }}">{{ student.name }}</a></h3>
    <p class="person-role">{{ student.role }}</p>
    {% if student.research %}<p>{{ student.research }}</p>{% endif %}
    {% if student.email %}<p><a href="mailto:{{ student.email }}">{{ student.email }}</a></p>{% endif %}
  </div>
</div>
{% endfor %}

---

## Postdoctoral Researchers

{% assign postdocs = site.students | where: "role", "Postdoctoral Researcher" %}
{% if postdocs.size > 0 %}
{% for student in postdocs %}
<div class="person-card">
  {% if student.photo %}<img src="{{ student.photo }}" alt="{{ student.name }}" class="person-photo">
  {% else %}<img src="/assets/img/avatar-icon.png" alt="{{ student.name }}" class="person-photo">{% endif %}
  <div class="person-info">
    <h3><a href="{{ student.url }}">{{ student.name }}</a></h3>
    <p class="person-role">{{ student.role }}</p>
    {% if student.research %}<p>{{ student.research }}</p>{% endif %}
  </div>
</div>
{% endfor %}
{% else %}
*No current postdocs.*
{% endif %}

---

## Alumni

{% assign alumni = site.students | where: "alumni", true %}
{% if alumni.size > 0 %}
| Name | Degree | Year | Current Position |
|------|--------|------|-----------------|
{% for person in alumni %}| [{{ person.name }}]({{ person.url }}) | {{ person.degree }} | {{ person.grad_year }} | {{ person.position }} |
{% endfor %}
{% endif %}
