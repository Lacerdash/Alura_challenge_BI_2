# Alura Challenge BI - 2ª Edição

Neste Repositório estão os meus projetos desenvolvidos nos meses de Fevereiro e Março de 2022 como parte do [Alura Challenge BI](https://www.alura.com.br/challenges/bi-2/). O curso utiliza o Challenge Based Learning, com o objetivo de aprofundar os conhecimentos dos alunos em uma área específica.

## Sobre

O Alura Challenge constituiu de 3 desafios semanais para que os participantes possam desenvolver novos conhecimentos, aprender novas ferramentas e criar um portifólio na área de Business Inteligence e ciência de dados, enquanto era simulado um fluxo de trabalho em uma empresa. 
Em cada semana do desafio foi enviado uma área de trabalho no [Trello](https://trello.com/), disponibilizando um conjunto de dados e algumas informações pertinentes da empresa, assim como informando as métricas que deveriam ser exibidas na versão final do dashboard. Além disso, foram disponibilizados links para cursos da plataforma Alura, com o intuito de aprofundar o conhecimento dos participantes.

* [Projetos desenvolvidos](#projetos-desenvolvidos)
    + [Semana 1 Mergulhando no mercado cinematográfico](#semana-1---mergulhando-no-mercado-cinematográfico---alurafilms)
      - [Página de Gêneros](#página-de-gêneros)
      - [Página de Filmes](#página-de-filmes)
      - [Página de Atores](#página-de-atores)
      - [Página de Diretores](#página-de-diretores)
    + [Semana 2 Entendendo o mercado de restaurantes da Índia.](#semana-2-entendendo-o-mercado-de-restaurantes-da-índia)
      - [Página de Análise de Restaurantes Índia](#página-de-análise-de-restaurantes-índia)
      - [Página de Análise Individual](#página-de-análise-individual)
    + [Semana 3 Analisando o setor de vendas da Alura Skimó.](#semana-3-analisando-o-setor-de-vendas-da-alura-skimó)
      - [Página de Análise de Vendas](#página-de-análise-de-vendas)
      - [Página de Vendedores](#página-de-vendedores)
      - [Página de Produtos](#página-de-produtos)
      - [Página de Cenários](#página-de-cenários)

## Projetos desenvolvidos
### 🎞Semana 1 - Mergulhando no mercado cinematográfico - AluraFilms
[Clique aqui para ir ao dashboard](https://app.powerbi.com/view?r=eyJrIjoiMDgxNGI0MTQtZGU5OC00OWM5LTk0NGYtYTMzNTFiZjUyNTAwIiwidCI6IjIwZmZhYzMwLThiNWMtNDIwYy1hNjg5LTRiYjg4NzdkM2UxMiJ9)
### 📃Briefing

Para essa semana, a empresa Alura Films dispinibilizou um dataset com informações sobre os 1000 filmes mais bem avaliados no [Internet Movie Database(IMDb)](https://www.imdb.com/) e requisitou algumas métricas para encontrar a combinação ideal de elenco e produção. Para o desenvolvimento do dashboard, foram requisitadas que algumas métricas estivessem presentes.

Para a criação do dashboard, criei 4 páginas com informações pertinentes a respeito de gêneros, filmes, atores e diretores para que a Alura Films consiga fazer a tomada de decisão de maneira mais assertiva e prática. As páginas possuem botões de navegação para facilitar o acesso as diferentes páginas do dashboard.

#### Página de Gêneros

![Página Gêneros](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20G%C3%AAneros.PNG)

Na página de gêneros, temos as informações de quantidade de filmes produzidos por gênero, receita média e total por gênero, assim como os gêneros com as maiores médias de nota no IMDB e no Metacritic. Ao lado, encontram-se 1 filtro: o de data. Esse filtro altera os gráficos, que passam a mostrar as informações de acordo com o filtro escolhido. Além disso ao se clicar em alguma das barras do gráfico de gêneros, as informações desse gênero são realçadas nos outros gráficos.

#### Página de Filmes

![Página Filmes](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20Filmes.PNG)

Na página de filmes, 3 gráficos são mostrados: um com dos filmes com as maiores bilheterias, o segundo com os filmes com as melhores notas no Metacritic e o terceiro com os filmes com as melhores notas no IMDB. Nessa página existem mais 3 filtros além do filtro de data: filtro de nome do filme, de Gênero e de classificação indicativa.

Os 3 gráficos possuem a mesma dica de ferramenta. Ao passar o mouse sobre alguma barra do gráfico a dica de ferramenta é mostrada e trás o nome do diretor do filme, a nota no IMDB, a nota no Metacritic e a imagem do poster do filme.

![Dica filme](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/dica%20filmes.png)

#### Página de Atores

![Página atores](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20Atores.PNG)

Na página de atores, 4 gráficos são mostrados: o primeiro é dos atores com maior receita dividida por nível de estrela (1, 2, 3 ou 4) acumulada de filmes, o segundo é dos atores com mais filmes estrelados, o terceiro é dos atores com as maiores médias no Metacritic  e o quarto é dos atores com as maiores médias no IMDB. Existem 4 filtros na página: data, ator, gênero e classificação indicativa

Os 3 últimos gráficos possuem a mesma dica de ferramenta. Ao passar o mouse sobre alguma barra do gráfico a dica de ferramenta é mostrada e trás quantidade de aparições em filmes, a média da nota no Metacritic, a média da nota no IMBD e a uma lista com o nome dos filmes que o ator participou.

![Dica atores](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/dica%20atores.png)


#### Página de Diretores

![Página diretores](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20Diretores.PNG)

Na página de atores, 4 gráficos são mostrados: o primeiro é dos diretores com maior receita de filmes acumulada, o segundo é dos diretores com mais filmes produzidos, o terceiro é dos diretores com as maiores médias no Metacritic e o quarto é dos atores com as maiores médias no IMDB. Existem 4 filtros na página: data, ator, gênero e classificação indicativa

Os 3 últimos gráficos possuem a mesma dica de ferramenta. Ao passar o mouse sobre alguma barra do gráfico a dica de ferramenta é mostrada e trás quantidade de filmes produzidos, a média da nota no Metacritic, a média da nota no IMBD e a uma lista com o nome dos filmes que o diretor produziou.

![Dica diretores](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/dica%20diretores.png)


### Semana 2 Entendendo o mercado de restaurantes da Índia.
[Clique aqui para ir ao dashboard](https://app.powerbi.com/view?r=eyJrIjoiNDM2MTRlNDAtMzg2YS00OTcwLThmN2ItYjUzNjYyNzgyODc2IiwidCI6IjIwZmZhYzMwLThiNWMtNDIwYy1hNjg5LTRiYjg4NzdkM2UxMiJ9&pageName=ReportSection4ed72ac43749d96c0c07)

### 📃Briefing

Para essa semana, a empresa Alura Foods dispinibilizou um dataset no formato JSON com informações sobre restaurantes de diversos paises conseguidas atraves do site [ZOMATO](https://www.zomato.com/pt). A Alura Food tem interesse em expandir seu negócio entrando no mercado indiano. Para tomar a melhor decisão, ela precisa da sua ajuda na criação de métricas e análise dos dados disponibilizados. A empresa então requisitou que algumas informações estivessem presentes no dashboard, para que as decisões fossem tomadas com mais clareza.

Para esse dashboard, criei 2 páginas. A primeira página traz as informações do mercado de resturantes Indiano, requisitado pela empresa. A segunda também é um pedido da empresa, contendo um relatório individualizado dos restaurantes. Crie botões para faciltar a navegação entre as páginas dos dashboards.

Para esse dashboard, aproveitei as cores presentes na logo da empresa: cinza e verde, e inclui as cores laranja e azul, para lembrar a bandeira indiana.

#### Página de Análise de Restaurantes Índia

![Página Análise Restaurantes Índia](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%202/Screenshots/An%C3%A1lise%20de%20restaurantes%20%C3%8Dndia%20sem%20filtro.PNG)

Para mostrar as opções de filtro basta clicar no botão de filtro no canto superior esquerdo e para fecha-lo basta clicar no botão com um X que aparecerá. 

Para seguir para a página de Análise Individual basta clicar no botão com o escrito " Análise Individual de Restaurantes"

![Página Análise Restaurantes Índia1](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%202/Screenshots/An%C3%A1lise%20de%20restaurantes%20%C3%8Dndia%20com%20filtro.PNG)


#### Página de Análise Individual

![Página Análise Individual](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%202/Screenshots/An%C3%A1lise%20individual%20resturantes.PNG)

Nenhum visual foi especificado pela empresa. Nessa página é possível filtrar as informações por restaurante, usando o filtro logo embaixo do título, ou por cidades, utilizando o mapa. Os filtros selecionados irão afetar os outros visuais, incluindo o título da página, que varia de acordo com o resturante selecionado.

Os cartões embaixo do filtro de restaurante trazem as informações sobre delivery, reserva ou entrega do restaurante. Abaixo, é possível ver as informações de preço em rúpias, em dólares, em euros e em reais. Também é possível ver as informações de review dos usuários: nota média, avaliação do aplicativo e número de votos.

Por último, embaixo do mapa encontram-se um botão a página do restaurante no ZOMATO.


### Semana 3 Analisando o setor de vendas da Alura Skimó.
[Clique aqui para ir ao dashboard](https://app.powerbi.com/view?r=eyJrIjoiNjNkOGVlYzItNzNlOC00ZThhLTgyZjEtODM1NTdhMjgwMmU1IiwidCI6IjIwZmZhYzMwLThiNWMtNDIwYy1hNjg5LTRiYjg4NzdkM2UxMiJ9&pageName=ReportSection6ad199bac3bd505adac0)

Para essa semana, a empresa Alura Skimo está buscando um painel que comporte todas as métricas necessárias para acompanhar suas vendas. Outra demanda é a criação de outras paineis voltados somente para produtos e outro somente para vendedores, para poderem analisar de forma mais segmentada. Além disso a empresa solicitou uma análise de cenário do faturamento, custo e comissão. Para isso a empresa forneceu um banco de dados MySQL com 6 tabelas (categorias, clientes, itens_pedido, pedido, produtos, vendedores). 

Utilizei a ferramenta [ColorSpace](https://mycolor.space/) para auxiliar na escolha da paleta de cores.

#### Página de Análise de Vendas

![Página Análise de Vendas](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/An%C3%A1lise%20de%20vendas1.PNG)

No canto esquerdo da página inicial é possível visualizar o menu de navegação com ícones referentes as demais páginas do dashboard (vendedores, produtos e cenários), além disso é possível encontrar botões que direcionam para minhas redes sociais (linkedin e github). No canto direito superior se encontra os filtros de ano, mês e categoria do produto que podem ser utilizados separadamente ou em conjunto para afetar as visualizações dessa página. Outro ponto que vale ressaltar é o gráfico de faturmento por Ano/mês contém uma projeção das vendas para os próximos 4 trimestres.

#### Página de Vendedores

![Página Análise Restaurantes Índia1](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/Vendedores1.PNG)

Na página de vendedores trouxe informações que considerei pertinentes para 

#### Página de Produtos

![Página Análise Restaurantes Índia1](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/Produtos.PNG)

#### Página de Cenários

![Página Análise Restaurantes Índia1](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/Cen%C3%A1rios.PNG)


