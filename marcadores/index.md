---
layout: page
title: Marcadores
lang: pt-br
ref: tags
---

{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}
{% assign tag_words = site_tags | split:',' | sort %}

{% include taglist.html %}

<!-- Posts by Tag -->
<div style="max-width: 1200px;">
  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] }}{% endcapture %}
    {% assign count = 0 %}
    {% for post in site.tags[this_word] %}
      {% if post.lang == page.lang %}
        {% assign count = count | plus: 1 %}
      {% endif %}
    {% endfor %}
    {% if count > 4 %}
      <h2 id="{{ this_word | cgi_escape }}">{{ this_word }}</h2>
      {% for post in site.tags[this_word] %}
        {% if post.lang == page.lang and post.title != null %}
          <div>
            <span style="float: left;">
              <a href="{{ site.baseurl }}/{{ post.url }}">{{ post.title }}</a>
            </span>
            <span style="float: right;">
              {{ post.date | date:"%d/%m/%Y" }}
            </span>
          </div>
          <div style="clear: both;"></div>
        {% endif %}
      {% endfor %}
    {% endif %}
  {% endunless %}{% endfor %}
</div>