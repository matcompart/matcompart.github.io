---
layout: post
title:  "Extração de Conteúdo por Densidade de HTML - Parte I"
categories: data-mining
---
> Extrair a notícia de uma página de notícia. Deve ser fácil... não? 
> <br>**CHAVES, Victor**.

# O Desafio

Quando estudava Recuperação de Informação, naturalmente fui levado à extração de informação. Mas foi um projeto do professor Flávio Coelho[1] de análise midiática que levantou esse problema específico.

Digamos que você possui um banco de dados de todas as notícias dos 100 sites de notícia mais relevantes do Brasil. É uma mina de ouro de informação, mas como minerar sem antes passar pela recuperação e extração do conteúdo principal dos documentos?

Se dos documentos estivessem salvos apenas seus excertos textuais relevantes, não haveria problema. Infelizmente as notícias são capturadas pela sua página HTML e consequentemente vem com um volume assombroso de lixo: código html, scripts, css, propagandas, comentários de visitantes etc.

Existem soluções bastantes avançadas no assunto como o Goose ([Scala][gravity-goose] ou [Python][python-goose]) e o [Boilerpipe][boilerpipe]. Como não conhecia estes projetos e o problema pareceu interessante, decidi tentar ao menos uma abordagem que parecia promissora.

# Mas.. mas... é só olhar e ver!

Um padrão que se repete na matemática e na computação é a formalização da intuição. A princípio pode parecer difícil desenvolver um algoritmo que resolva um problema prático, então uma saída comum é tentar implementar um algoritmo que formalize e otimize o comportamento de um ser humano.

A primeira solução que poderia se pensar seria analisar visualmente a página, como fazemos diariamente. Mas nada é simples no domínio do processamento de imagens, e isso iria requerer um aprendizado de máquina muito sofisticado.

A segunda solução é observar como um ser humano procura o conteúdo principal dentro de um código HTML, nossa matéria prima em seu estado natural. Agora estaremos lidando com linhas de código em vez de blocos alocados espacialmente.

aqui
=========

Como essa extração manual ocorre? A metodologia pode ser resumida da seguinte forma:

> Começamos do início do texto procurando por uma região densa em linguagem natural. Ao encontrar, lemos seu conteúdo e decidimos se trata do assunto a qual o documento é dedicado. Caso positivo, este provavelmente faz parte do conteúdo principal da página.

# Fundamentação

# Procedimento

# Discussão

Uma abordagem simples e intuitiva possui seus custos em performance. A desvantagem de espelhar o comportamento humano num algoritmo de extração é a intrínseca limitação cognitiva do algoritmo. Isto é, não aproveitamos todos os recursos computacionais que poderíamos pois nos limitamos inicialmente a um padrão humano de pensamento.

Ao final desta série farei uma análise rápida dos extratores existentes (Goose e Boilerpipe) e ficará demonstrado que o maior nível de abstração dado pelo poder computacional resulta em um algoritmo muito mais poderoso. Já adiantando o assunto com um exemplo, estes algoritmos não analisam o documento separando somente por linhas, mas navegam na estrutura em árvore do documento HTML.

<br>
___________
<br>

Este é o primeiro post da série sobre extração de conteúdo de documentos HTML. Para continuar lendo, acesse:

- [Extração de Condeúdo por densidade de HTML - Parte II][parte-2]

- [IPython Notebook][ipynb-ptBr] do artigo produzido, contendo mais informações

- O [artigo][paper-ptBr] produzido como relatório para este projeto.


[gravity-goose]: https://github.com/GravityLabs/goose
[python-goose]:  https://github.com/grangier/python-goose
[boilerpipe]: https://code.google.com/p/boilerpipe/
[parte-2]: https://github.com/vvbchaves/WebNectar

[webnectar-gh]: https://github.com/vvbchaves/WebNectar
[ipynb-ptBr]: http://nbviewer.ipython.org/github/vvbchaves/WebNectar/blob/master/paper_pt-BR.ipynb
[paper-ptBr]: http://nbviewer.ipython.org/github/vvbchaves/WebNectar/blob/master/paper_pt-BR.ipynb

[1]: http://emap.fgv.br/people/flavio.coelho.html
