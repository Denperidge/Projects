---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<p>Don't forget to check out <a href="https://resume.denperidge.com/">my resume</a> as well!</p>

<h1>Denperidge's Projects</h1>
<ul>
{% for project in site.projects %}
<li><a href="#{{ project.slug }}">{{ project.title }}</a></li>
{% endfor %}
</ul>

{% for project in site.projects %}

<h2 id="{{ project.slug }}">{{ project.title }}</h2>

<a href="https://github.com/{{ project.repoowner }}/{{ project.reponame }}" target="_blank">
    <object data="https://gh-card.dev/repos/{{ project.repoowner }}/{{ project.reponame }}.svg"></object>
</a>

<p>{{ project.description }}</p>



<h3>What went right/what could improve?</h3>
<p>Pro:</p>
<ul>
    {% for part in project.pro %}
    <li>{{ part }}</li>
    {% endfor %}
</ul>

<p>Contra:</p>
<ul>
    {% for part in project.con %}
    <li>{{ part }}</li>
    {% endfor %}
</ul>


{% if project.website %}
<h3>URLs</h3>
<ul>
    <li>View the wesbite <a href="{{ project.website }}">here</a>...</li>
    <li>... and view the repository <a href="https://github.com/{{ project.repoowner }}/{{ project.reponame }}" target="_blank">here</a>!</li>
</ul>
{% else %}
<p>View the repository here! <a href="https://github.com/{{ project.repoowner }}/{{ project.reponame }}" target="_blank">here</a>,</p>
{% endif %}

{% if project.tags %}
<p>Tags: 
    {% for tag in project.tags %}
    <a href="tag?{{ tag }}">{{ tag }}</a>,&nbsp;
    {% endfor %}
</p>
{% endif %}

<br>


---


<br><br>

{% endfor %}
