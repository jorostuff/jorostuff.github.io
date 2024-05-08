---
layout: default
---

<section class="posts">
    <h2 style="margin-top: 0;">Writings</h2>
    {% assign sorted_posts = site.posts | sort: "date" | reverse %}
    <ul>
        {% for post in site.posts %}
        <li>
            <div style="display: flex; align-items: center;">
                <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
                <div class="tags">
                    {% for tag in post.tags %}
                    <a href="/tag/{{tag}}">{{tag}}</a>{% unless forloop.last %}, {% endunless %}
                    {% endfor %}
                </div>
            </div>
            <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%m-%d-%Y" }}</time>
        </li>
        {% endfor %}
    </ul>
</section>