---
layout: page
title: Marcadores
lang: pt-br
ref: tags
---

<!-- PASSO 1: Coletar todas as tags que aparecem em posts DO IDIOMA DESTA PÁGINA. -->

{% assign tags_do_idioma_atual = "" | split: "," %}
{% for post in site.posts %}
  {% if post.lang == page.lang %}
    {% for tag in post.tags %}
      {% assign downcased_tag = tag | downcase %} <!-- Normalizar para minúsculas para evitar duplicatas de case -->
      {% unless tags_do_idioma_atual contains downcased_tag %}
        {% assign tags_do_idioma_atual = tags_do_idioma_atual | push: downcased_tag %}
      {% endunless %}
    {% endfor %}
  {% endif %}
{% endfor %}
{% assign tag_words = tags_do_idioma_atual | sort_natural %} <!-- tag_words agora contém apenas tags do idioma atual, em minúsculas e ordenadas -->

<!-- PASSO 2: Incluir o taglist.html. Ele usará o novo tag_words.
         Precisaremos modificar taglist.html para contar posts do idioma correto. -->
{% include taglist.html %}


<!-- PASSO 3: Listar os posts por tag, filtrando pelo idioma da página. -->

<div style="max-width: 1200px;">
  {% for tag_name_normalizada in tag_words %}
    {% assign posts_nesta_tag_e_idioma = 0 %}
    {% assign posts_para_exibir = "" | split: "," %}
    {% for post in site.tags[tag_name_normalizada] %} {# site.tags ainda usa o nome original da tag, pode ser um problema se o case importa muito para você. Melhor iterar sobre posts. #}
      {% if post.lang == page.lang %}
         {% assign posts_nesta_tag_e_idioma = posts_nesta_tag_e_idioma | plus: 1 %}
         {% assign posts_para_exibir = posts_para_exibir | push: post %}
      {% endif %}
    {% endfor %}

    # Alternativa mais robusta para coletar posts_para_exibir se o case da tag for um problema.
    # Este loop garante que estamos usando a tag_name_normalizada para encontrar os posts corretos.
    {% assign posts_para_exibir_alt = "" | split: "," %}
    {% assign count_alt = 0 %}
    {% for post_geral in site.posts %}
        {% if post_geral.lang == page.lang %}
            {% for p_tag in post_geral.tags %}
                {% if p_tag | downcase == tag_name_normalizada %}
                    {% assign posts_para_exibir_alt = posts_para_exibir_alt | push: post_geral %}
                    {% assign count_alt = count_alt | plus: 1 %}
                    {% break %} # Evita adicionar o mesmo post múltiplas vezes se ele tiver a mesma tag com cases diferentes, o que não deveria acontecer após normalização
                {% endif %}
            {% endfor %}
        {% endif %}
    {% endfor %}
    {% assign posts_para_exibir = posts_para_exibir_alt | uniq | sort: "date" | reverse %}
    {% assign posts_nesta_tag_e_idioma = count_alt %}


    {% if posts_nesta_tag_e_idioma > 0 %} # Só mostra a seção da tag se houver posts NELA E NESTE IDIOMA. Remova o > 5 ou > 9 para mostrar todas.
      <h2 id="{{ tag_name_normalizada | cgi_escape }}">{{ tag_name_normalizada | capitalize }}</h2> # Usar a tag normalizada 
      {% for post_item in posts_para_exibir %}
        {% if post_item.title != null %}
          <div>
            <span style="float: left;">
              <a href="{{ post_item.url | prepend: site.baseurl }}">{{ post_item.title }}</a>
            </span>
            <span style="float: right;">
              {{ post_item.date | date:"%d/%m/%Y" }}
            </span>
          </div>
          <div style="clear: both;"></div>
        {% endif %}
      {% endfor %}
    {% endif %}
  {% endfor %}
</div>
