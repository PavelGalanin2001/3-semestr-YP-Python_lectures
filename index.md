---
title: Лекции Python (БрГТУ ПОИТ) Хацкевич
---

<link rel="stylesheet" href="{{ site.baseurl }}/main.css" />

<div class="container">
    <div class="page__cards_block">
        {% for post in site.posts %}
            {% if post.show == 1 %}
                <div class="page__card">
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
                            class="card__button"
                            href="{{ site.baseurl }}{{ post.url }}"
                        >Просмотр</a>
                        {% if post.hasJupyter == 1%}
                        <a
                            class="card__button"
                            href="{{ site.baseurl }}{{ post.url | remove:'/index.html' }}/jupyter-notebook.ipynb"
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