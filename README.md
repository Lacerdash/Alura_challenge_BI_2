# Alura Challenge BI - 2ª Edição

Neste Repositório estão os meus projetos desenvolvidos nos meses de Fevereiro e Março de 2022 como parte do [Alura Challenge BI](https://www.alura.com.br/challenges/bi-2/). O curso utiliza o Challenge Based Learning, com o objetivo de aprofundar os conhecimentos dos alunos em uma área específica.

## Sobre

O Alura Challenge constituiu de 3 desafios semanais para que os participantes possam desenvolver novos conhecimentos, aprender novas ferramentas e criar um portifólio na área de Business Inteligence e ciência de dados, enquanto era simulado um fluxo de trabalho em uma empresa. 
Em cada semana do desafio foi enviado uma área de trabalho no [Trello](https://trello.com/), disponibilizando um conjunto de dados e algumas informações pertinentes da empresa, assim como informando as métricas que deveriam ser exibidas na versão final do dashboard. Além disso, foram disponibilizados links para cursos da plataforma Alura, com o intuito de aprofundar o conhecimento dos participantes.

* [Projetos desenvolvidos](#projetos-desenvolvidos)
    + [Semana 1 Mergulhando no mercado cinematográfico](#semana-1-mergulhando-no-mercado-cinematográfico---alurafilms)
      - [Página de Gêneros](#página-de-gêneros)
      - [Página de Filmes](#página-de-filmes)
      - [Página de Atores](#página-de-atores)
      - [Página de Diretores](#página-de-diretores)
    + [Semana 2 Entendendo o mercado de restaurantes da Índia.](#semana-2-entendendo-o-mercado-de-restaurantes-da-índia)
    + [Semana 3 Analisando o setor de vendas da Alura Skimó.](#semana-3-analisando-o-setor-de-vendas-da-alura-skimó)

## Projetos desenvolvidos
### 🎞Semana 1 - Mergulhando no mercado cinematográfico - AluraFilms

### 📃Briefing

Para essa semana, a empresa Alura Films dispinibilizou um dataset com informações sobre os 1000 filmes mais bem avaliados no [Internet Movie Database(IMDb)](https://www.imdb.com/) e requisitou algumas métricas para encontrar a combinação ideal de elenco e produção. Para o desenvolvimento do dashboard, foram requisitadas que algumas métricas estivessem presentes.

Para a criação do dashboard, criei 4 páginas com informações pertinentes a respeito de gêneros, filmes, atores e diretores para que a Alura Films consiga fazer a tomada de decisão de maneira mais assertiva e prática.

#### Página de Gêneros

![Página Gêneros](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20G%C3%AAneros.PNG)

Na página de gêneros, temos as informações de quantidade de filmes produzidos por gênero, receita média e total por gênero, assim como os gêneros com as maiores médias de nota no IMDB e no Metacritic. Ao lado, encontram-se 1 filtro: o de data. Esse filtro altera os gráficos, que passam a mostrar as informações de acordo com o filtro escolhido. Além disso ao se clicar em alguma das barras do gráfico de gêneros, as informações desse gênero são realçadas nos outros gráficos.

A página também possui um menu de navegação do lado esquerda, onde é possível clicar e navegar entre as páginas do Dashboard.

#### Página de Filmes

![Página Filmes](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20Filmes.PNG)

Na página de filmes, 3 gráficos são mostrados: um com dos filmes com as maiores bilheterias, o segundo com os filmes com as melhores notas no Metacritic e o terceiro com os filmes com as melhores notas no IMDB. Nessa página existem mais 3 filtros além do filtro de data: filtro de nome do filme, de Gênero e de classificação indicativa.

A página possui um menu de navegação na parte superior, onde é possível clicar e navegar entre as páginas do Dashboard.

Os 3 gráficos possuem a mesma dica de ferramenta. Ao passar o mouse sobre alguma barra do gráfico a dica de ferramenta é mostrada e trás o nome do diretor do filme, a nota no IMDB, a nota no Metacritic e a imagem do poster do filme.

![Dica filme](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/dica%20filmes.png)

#### Página de Atores

![Página atores](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20Atores.PNG)

Na página de atores, 4 gráficos são mostrados: o primeiro é dos atores com maior receita dividida por nível de estrela (1, 2, 3 ou 4) acumulada de filmes, o segundo é dos atores com mais filmes estrelados, o terceiro é dos atores com as maiores médias no Metacritic  e o quarto é dos atores com as maiores médias no IMDB. Existem 4 filtros na página: data, ator, gênero e classificação indicativa

A página possui um menu de navegação na parte superior, onde é possível clicar e navegar entre as páginas do Dashboard.

Os 3 últimos gráficos possuem a mesma dica de ferramenta. Ao passar o mouse sobre alguma barra do gráfico a dica de ferramenta é mostrada e trás quantidade de aparições em filmes, a média da nota no Metacritic, a média da nota no IMBD e a uma lista com o nome dos filmes que o ator participou.

![Dica atores](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/dica%20atores.png)


#### Página de Diretores

![Página diretores](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20Diretores.PNG)

Na página de atores, 4 gráficos são mostrados: o primeiro é dos diretores com maior receita de filmes acumulada, o segundo é dos diretores com mais filmes produzidos, o terceiro é dos diretores com as maiores médias no Metacritic e o quarto é dos atores com as maiores médias no IMDB. Existem 4 filtros na página: data, ator, gênero e classificação indicativa

Os 3 últimos gráficos possuem a mesma dica de ferramenta. Ao passar o mouse sobre alguma barra do gráfico a dica de ferramenta é mostrada e trás quantidade de filmes produzidos, a média da nota no Metacritic, a média da nota no IMBD e a uma lista com o nome dos filmes que o diretor produziou.

![Dica diretores](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/dica%20diretores.png)


### 🎞Semana 2 Entendendo o mercado de restaurantes da Índia.

### Semana 3 Analisando o setor de vendas da Alura Skimó.
