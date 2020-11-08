---

---

<ul>
    {% for post in site.posts %}

        {% unless post.next %}
        <h2>{{ post.date | date: '%Y' }}</h2>

        {% else %}

        {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
        {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}

        {% if year != nyear %}
            <h2>{{ post.date | date: '%Y' }}</h2>
        {% endif %}

        {% endunless %}

        <li>
            <a href="{{ site.baseurl }}{{ post.url }}">
                <!-- {{ post.title }} -->
                <time datetime="{{ post.date | date: "%Y-%m-%d" }}">
                    {{ post.date | date: "%d %B %Y" }}
                </time>
            </a>
        </li>
    {% endfor %}
</ul>
