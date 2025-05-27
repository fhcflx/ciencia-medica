---
layout: page
title: Tags # ou Markers
lang: en-us
ref: tags # Mesma referência para o seletor de idioma
---

<!-- PASSO 1: Coletar todas as tags que aparecem em posts DO IDIOMA DESTA PÁGINA. -->

{% assign tags_do_idioma_atual = "" | split: "," %}
{% for post in site.posts %}
  {% if post.lang == page.lang %}
    {% for tag in post.tags %}
      {% assign downcased_tag = tag | downcase %}
      {% unless tags_do_idioma_atual contains downcased_tag %}
        {% assign tags_do_idioma_atual = tags_do_idioma_atual | push: downcased_tag %}
      {% endunless %}
    {% endfor %}
  {% endif %}
{% endfor %}
{% assign tag_words = tags_do_idioma_atual | sort_natural %}

{% include taglist.html %}

<!-- PASSO 3: Listar os posts por tag, filtrando pelo idioma da página.
(Use a versão melhorada do loop como em marcadores/index.md) -->

<div style="max-width: 1200px;">
  {% for tag_name_normalizada in tag_words %}
    {% assign posts_para_exibir = "" | split: "," %}
    {% assign count = 0 %}
    {% for post_geral in site.posts %}
        {% if post_geral.lang == page.lang %}
            {% for p_tag in post_geral.tags %}
                {% if p_tag | downcase == tag_name_normalizada %}
                    {% assign posts_para_exibir = posts_para_exibir | push: post_geral %}
                    {% assign count = count | plus: 1 %}
                    {% break %} 
                {% endif %}
            {% endfor %}
        {% endif %}
    {% endfor %}
    {% assign posts_para_exibir_final = posts_para_exibir | uniq | sort: "date" | reverse %}


    {% if count > 0 %} 
      <h2 id="{{ tag_name_normalizada | cgi_escape }}">{{ tag_name_normalizada | capitalize }}</h2>
      {% for post_item in posts_para_exibir_final %}
        {% if post_item.title != null %}
          <div>
            <span style="float: left;">
              <a href="{{ post_item.url | prepend: site.baseurl }}">{{ post_item.title }}</a>
            </span>
            <span style="float: right;">
              {{ post_item.date | date:"%m/%d/%Y" }} {# Formato de data para inglês #}
            </span>
          </div>
          <div style="clear: both;"></div>
        {% endif %}
      {% endfor %}
    {% endif %}
  {% endfor %}
</div> 
