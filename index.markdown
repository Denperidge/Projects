---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<h1>Denperidge's Projects</h1>
<ul>
{% for project in site.projects %}
<li><a href="{{ project.slug }}">{{ project.title }}</a></li>
{% endfor %}
</ul>

{% for project in site.projects %}

<h2 id="{{ project.slug }}">{{ project.title }}</h2>

<object data="https://gh-card.dev/repos/{{ project.repoowner }}/{{ project.reponame }}.svg"></object>

<p>{{ project.description }}</p>

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
<ul>
    <li>View the wesbite <a href="{{ projects.website }}">here</a>,</li>
    <li>and view the repository <a href="https://github.com/{{ project.repoowner }}/{{ project.reponame }}">here</a>!</li>
</ul>
{% else %}
<p>View the repository here! <a href="https://github.com/{{ project.repoowner }}/{{ project.reponame }}">here</a>,</p>
{% endif %}

{% endfor %}

<p>Tags: 
    {% for tag in page.tags %}
    <a href="{{ tag }}">{{ tag }}</a>,&nbsp;
    {% endfor %}
</p>

