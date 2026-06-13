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
      <h3>Duncan Callaway · <small class="person-role"> Professor, ERG</small></h3>
      <p><a href="https://scholar.google.com/citations?user=Ugijg1wAAAAJ">Google Scholar</a> · <a href="/assets/files/cv-duncan-callaway.pdf">CV</a></p>
  </div>
</div>

{% assign current = site.people | where: "alumni", "no" | sort: "name" %}
{% for person in current %}
<div class="person-card">
  {% if person.photo %}<img class="person-photo" src="{{ person.photo }}" alt="{{ person.name }}">{% endif %}
  <div class="person-info">
    <h3>{{ person.name }} · <small class="person-role"> {{ person.role }}, {{ person.program }}, <em>{{ person.years }}</em></small></h3>
    {% if person.research and person.research != "" %}
    {{ person.research }}
    {% endif %}
    {% if person.scholar or person.linkedin %}
    {% if person.scholar %}<a href="{{ person.scholar }}">Google Scholar</a>{% endif %}{% if person.scholar and person.linkedin %} · {% endif %}{% if person.linkedin %}<a href="{{ person.linkedin }}">LinkedIn</a>{% endif %}{% if person.CV %} {% if person.scholar or person.linkedin %} · {% endif %}<a href="{{ person.CV }}">CV</a> {% endif %}
    {% endif %}
  </div>
</div>
{% endfor %}

---

## Alumni

{% assign alumni = site.people | where: "alumni", "yes" | sort: "name" %}
{% if alumni.size > 0 %}
{% for person in alumni %}
<div class="person-card alumni-card">
  <div class="person-info">
    <p><strong>{{ person.name }}</strong> · {{ person.degree }}{% if person.degree != "Postdoc" %}, {{ person.program }}{% endif %}, <em>{{ person.years }}</em>{% if person.current_role %}.<strong> Now:</strong> {{ person.current_role }}.{% endif %}</p>
    {% if person.bio and person.bio != "" %}<p>{{ person.bio }}</p>{% endif %}
    {% if person.scholar or person.linkedin %}
      <p>{% if person.scholar %}<a href="{{ person.scholar }}">Google Scholar</a>{% endif %}{% if person.scholar and person.linkedin %} · {% endif %}{% if person.linkedin %}<a href="{{ person.linkedin }}">LinkedIn</a>{% endif %}</p>
    {% endif %}
  </div>
</div>
{% endfor %}
{% else %}
*Former group members will be listed here.*
{% endif %}
