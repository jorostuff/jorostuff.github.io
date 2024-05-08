---
layout: default
---

<section class="posts">
    <h2 style="margin-top: 0;">Projects</h2>
    {% assign sorted_projects = site.projects | sort: "date" | reverse %}
    <ul>
        {% for project in sorted_projects %}
        <li>
            <div style="display: flex; align-items: center;">
                <a href="{{ site.baseurl }}{{ project.url }}">{{ project.title }}</a>
                <div class="tags">
                    {% for tag in project.tags %}
                    <a href="/tag/{{tag}}">{{tag}}</a>{% unless forloop.last %}, {% endunless %}
                    {% endfor %}
                </div>
            </div>
            <time datetime="{{ project.date | date_to_xmlschema }}">{{ project.date | date: "%m-%d-%Y" }}</time>
        </li>
        {% endfor %}
    </ul>
</section>