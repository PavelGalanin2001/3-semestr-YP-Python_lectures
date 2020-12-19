---

---

<link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css"
    rel="stylesheet"
    integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1"
    crossorigin="anonymous"
/>

<div class="container">
    <div class="row" style="justify-content: center;">
        {% for post in site.posts %}
            {% if post.show == 1 %}
                <div class="card" style="min-width: 240px; width: calc(100% / 4 - 8px * 4); margin: 8px;">
                    <img
                        class="card-img-top"
                        src=""
                        alt=""
                    />
                
                    <div class="card-body">
                        <h5 class="card-title">
                            <time datetime="{{ post.date | date: "%Y-%m-%d" }}">
                                {{ post.date | date: "%Y-%m-%d" }}
                            </time>
                        </h5>
                        <a
                            href="{{ site.baseurl }}{{ post.url }}"
                            class="btn btn-primary"
                            style="width: 100%; margin: 16px 0;"
                        >Просмотр</a>
                        {% if post.hasJupyter == 1%}
                        <a
                            href="{{ site.baseurl }}{{ post.url | remove:'/index.html' }}/jupyter-notebook.ipynb"
                            class="btn btn-primary"
                            style="width: 100%; margin: 16px 0;"
                        >Скачать Jupyter файл</a>
                        {% endif %}
                        <p class="card-text">
                            {{ post.title }}
                        </p>
                    </div>
                </div>
            {% endif %}
        {% endfor %}
    </div>
</div>