---
layout: single
title: ""
permalink: /people/
author_profile: false
---

## Current Group Members

<div class="person-card">
    <img class="person-photo" src="/assets/img/people/duncan-callaway.png" alt="Duncan Callaway" style="max-width: 150px;">  
    <div class="person-info">
      <h3>Duncan Callaway</h3>
      <p class="person-role">Professor, Energy and Resources Group</p>
      <a href="https://scholar.google.com/citations?user=Ugijg1wAAAAJ">Google Scholar</a>
      <p><a href="/assets/files/Duncan Callaway CV 2026.pdf">CV</a> · <a href="mailto:dcal@berkeley.edu">dcal@berkeley.edu</a></p>
  </div>
</div>

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
    <p><em>{{ person.years }}</em></p>
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
    <p class="person-role">{{ person.role }}{% if person.role != "Postdoc" %}, {{ person.program }}{% endif %}</p>
    {% if person.bio and person.bio != "" %}<p>{{ person.bio }}</p>{% endif %}
    {% if person.current_role %}<p><strong>Now:</strong> {{ person.current_role }}</p>{% endif %}
    {% if person.scholar or person.linkedin %}
      <p>{% if person.scholar %}<a href="{{ person.scholar }}">Google Scholar</a>{% endif %}{% if person.scholar and person.linkedin %} · {% endif %}{% if person.linkedin %}<a href="{{ person.linkedin }}">LinkedIn</a>{% endif %}</p>
    {% endif %}
    <p><em>{{ person.years }}</em></p>
  </div>
</div>
{% endfor %}
{% else %}
*Former group members will be listed here.*
{% endif %}
