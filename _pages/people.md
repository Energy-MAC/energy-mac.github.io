---
layout: single
title: "People"
permalink: /people/
author_profile: false
---

## Principal Investigator

<div class="person-card">
    <img class="person-photo" src="/assets/img/people/duncan-callaway.png" alt="Duncan Callaway" style="max-width: 150px;">  <div class="person-info">
    <h3><a href="https://erg.berkeley.edu/people/callaway-duncan/">Duncan Callaway</a></h3>
    <p class="person-role">Professor, Energy and Resources Group</p>
    <p>Duncan's research focuses on modeling, optimization, and control of electric power systems with high penetrations of renewable energy and distributed energy resources.</p>
    <p><a href="mailto:dcal@berkeley.edu">dcal@berkeley.edu</a></p>
  </div>
</div>

---

## Current Group Members

{% assign current = site.people | where: "alumni", "no" | sort: "name" %}
{% for person in current %}
<div class="person-card">
  {% if person.photo %}<img class="person-photo" src="{{ person.photo }}" alt="{{ person.name }}">{% endif %}
  <div class="person-info">
    <h3>{{ person.name }}</h3>
    <p class="person-role">{{ person.role }}, {{ person.program }}</p>
    {% if person.bio and person.bio != "" %}
    <p>{{ person.bio }}</p>
    {% endif %}
    {% if person.scholar or person.linkedin %}
    <p>{% if person.scholar %}<a href="{{ person.scholar }}">Google Scholar</a>{% endif %}{% if person.scholar and person.linkedin %} · {% endif %}{% if person.linkedin %}<a href="{{ person.linkedin }}">LinkedIn</a>{% endif %}</p>
    {% endif %}
  </div>
</div>
{% endfor %}

---

## Alumni

{% assign alumni = site.people | where: "alumni", "yes" | sort: "name" %}
{% if alumni.size > 0 %}
{% for person in alumni %}
<div class="person-card">
  <div class="person-info">
    <h3>{{ person.name }}</h3>
    <p class="person-role">{{ person.role }}, {{ person.program }}</p>
    {% if person.bio and person.bio != "" %}<p>{{ person.bio }}</p>{% endif %}
    {% if person.current_role %}<p><strong>Now:</strong> {{ person.current_role }}</p>{% endif %}
    {% if person.scholar or person.linkedin %}
      <p>{% if person.scholar %}<a href="{{ person.scholar }}">Google Scholar</a>{% endif %}{% if person.scholar and person.linkedin %} · {% endif %}{% if person.linkedin %}<a href="{{ person.linkedin }}">LinkedIn</a>{% endif %}</p>
    {% endif %}
  </div>
</div>
{% endfor %}
{% else %}
*Former group members will be listed here.*
{% endif %}
