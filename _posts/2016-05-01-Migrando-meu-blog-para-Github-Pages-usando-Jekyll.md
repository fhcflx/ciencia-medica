---
layout: post
title:  "Migrando meu blog para Github Pages usando Jekyll"
date:   2016-05-01 12:00:00 -0300
tags:
  - Jekyll update
  - GitHub
  - Bundler
author: ffelix
lang: pt-br
ref: blog
---
Decidi migrar meu [blog](https://pharmak.blogspot.com) para uma plataforma mais moderna e limpa. Para tanto, usei [Jekyll](https://jekyllrb.com) para criar a nova interface e [GitHub Pages ](https://pages.github.com/) para implementá-la e publicá-la na net. Inspirei-me em [Carl Boettiger](https://www.carlboettiger.info/index.html) e seu [**open lab notebook**](https://www.carlboettiger.info/2012/09/28/Welcome-to-my-lab-notebook.html). Como eu já tinha interesse em criar um projeto de "caderno de anotações de pesquisa aberto" ([open notebook science](https://en.wikipedia.org/wiki/Open_notebook_science)), mas voltado para pesquisa clínica, um [open science clinical trial](https://github.com/fhcflx/valkyrie) que vai abrigar um ensaio clínico com os princípios da [ciência aberta](https://pt.m.wikipedia.org/wiki/Ci%C3%AAncia_aberta) ([open science](https://en.wikipedia.org/wiki/Open_science)), entendi que a experiência com esta nova plataforma poderia ser aproveitada para este e outros projetos.
<!--more-->

Resumidamente, criei um repositório público no [GitHub](https://github.com) para abrigar os arquivos gerados pelo Jekyll, uma poderosa ferramenta para criar páginas estáticas da net. Usei, inicialmente, uma versão [portátil](https://github.com/madhur/PortableJekyll) de [Jekyll para Windows](https://jekyll-windows.juthilo.com), o que facilitou as coisas. Localmente, criei um diretório e iniciei um repositório de [Git](https://git-scm.com/) nele, onde rodei Jekyll para gravar os arquivos necessários para o blog. Também uso tanto a [versão para Windows de Git quanto sua versão portátil](https://git-scm.com/download/win). Na verdade, meus arquivos locais estão num pendrive e são usados em vários computadores, pessoais e do trabalho. Considerações com segurança não são uma preocupação, uma vez que a maioria de meus trabalhos são públicos. A fim de proteger a confidencialidade de meus pacientes, todos os dados referentes a eles que vão a público são [desidentificados](https://en.wikipedia.org/wiki/De-identification).

Em seguida, experimentei instalar [Ruby para Windows](https://rubyinstaller.org) e Jekyll via [Bundler](https://bundler.io) usando a [gem do GitHub Pages](https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/). Assim, recriei os arquivos do blog para que tivessem integração com os recursos e dependências do Github Pages. Localmente, criei um branch do repositório que havia iniciado, com o nome *gh-pages*. Fiz o push para o repositório do Github e _voilá_, o blog estava no ar. Alguns ajustes mais e estava bem razoável.

Uma das vantagens da plataforma Jekyll/Github Pages é poder escrever os posts em sintaxe [Markdown](https://daringfireball.net/projects/markdown/), uma forma simplificada de html que permite escrever quase como se estivesse usando apenas texto simples sem formatação, e mesmo assim renderiza páginas esteticamente agradáveis. Os posts podem ser comitados localmente ou no próprio Github na net. Por exemplo, este post foi escrito em markdown ([GitHub flavored](https://guides.github.com/features/mastering-markdown/)) no Escritor Pro, um aplicativo para iOS e comitado no Github em meu iPad.

Farei novas postagens neste novo formato do Pharmakon, não importarei todas as postagens antigas, uma [funcionalidade](https://jekyllrb.com/docs/migrations/) oferecida pelo Jekyll, porém vou importar manualmente e acrescentar mais comentários, atualizando e aprofundando o conteúdo, as principais postagens do antigo Pharmakon, para dar um kick-off no novo blog. Uma das postagens a ser "rebooted" vai ser aquela do [tratamento de hemangiomas com propranolol]( https://pharmak.blogspot.com.br/2009/03/uso-de-propranolol-revoluciona.html), uma das mais visualizadas do velho Pharmakon.


[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
