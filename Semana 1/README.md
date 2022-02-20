# [Semana 1](https://bit.ly/Semana1_Challenge) - Alura Challenge BI 2ª Edição

A Alura Films contratou você para fazer uma pesquisa de mercado, com a finalidade de identificar a seleção ideal de elenco e produção. Para isso, ela disponibilizou uma base de 
dados do IMDB com 1000 filmes. Após tratamento dos dados, a empresa espera receber um dashboard que ajudará a mesma na tomada de decisão para projetos futuros.

## Base de Dados

A empresa disponibilizou 2 tabelas no formato CSV:
  
  1. Filmes, que possui colunas com as informações de produção dos top 1000 filmes de acordo com o IMDB.
  2. Posters, que possui informações sobre o código e URL das imagens de cada filme. 

Além das tabelas, a empresa também disponibilizou um arquivo com a descrição geral de cada arquivo, assim como resumos sobre as colunas de cada tabela. Com essa descrição, alterei os títulos das colunas do arquivo 'Filmes' para o portugês durante a fase de tratamento dos dados.

Título Original da Coluna | Descrição da empresa | Título da coluna traduzido
--------------- | -------------------------------- | -------------------
Id_Title | Id do filme | Id_nome
Series_Title | Nome do filme | Título
Released_Year | Ano em que o filme foi lançado | Ano_de_lançamento
Certificate | Classificação obtido por esse filme | Classificação_indicativa
Runtime | Tempo de execução total do filme | Duração_do_filme
Genre | Gênero do filme | Gênero
IMDB_Rating | Classificação do filme no site do IMDB | Nota_IMDb
Overview | mini-história/resumo | Resumo
Meta_score | Pontuação obtida pelo filme | Nota_Metacritic
Director | Nome do Diretor | Diretor
Star1,Star2,Star3,Star4 | Nome das Estrelas | Estrela1, Estrela2, Estrela3, Estrela4
Noofvotes | Número total de votos | Número de votos
Gross | Dinheiro ganho por esse filme | Receita

Também alterei o nome das colunas do arquivo 'Posters'

Título Original da Coluna | Descrição da empresa | Título da coluna traduzido
--------------- | -------------------------------- | -------------------
Id_Title | Id do filme | Id_nome
Poster_link | Link da imagem | link_imagem

## Métricas

A empresa requisitou que as seguintes métricas estivessem no relatório:

- Dinheiro ganho por Estrela 1, Estrela 2, Estrela 3 e Estrela 4
- Filmes mais votados
- Gêneros mais rentáveis
- Estrelas que mais aparecem nos filmes
- Percentual dos (n) gêneros mais explorados

Além disso, a empresa também requisitou uma exploração das colunas 'Meta_Score', 'IMDB_Rating' e 'Noofvotes'. Como um bônus, porém sem a necessidade de aparecerem no relatório, a empresa requisitou as seguintes tarefas:

- Padronização classificação indicativa
- Tradução do título das colunas
- Diretores mais rentáveis
- Pares mais comuns entre diretores e estrelas

## Tratamento de dados

Todos os tratamentos de dados foram realizados dentro do Power Query do Power BI. 

Título da coluna traduzido | Tratamento realizado
--------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Id_nome | N/A
Título | N/A
Ano_de_lançamento | N/A
Classificação_indicativa | Foi necessário utilizar a ferramente de substituir valores para traduzir as classificações indicativas, uma vez que as mesmas estavam nas mais variadas formas. [Link para a consulta das classificações](https://help.imdb.com/article/contribution/titles/certificates/GU757M8ZJ9ZPXB39?ref_=helpart_nav_27#spain)
Duração_do_filme | Os dados estavam formatados em forma de texto, contendo números e letras. Ex: 142 min. Então utilizei da ferramente de substituir valores para substituir ' min' para ''. Eliminando assim o texto e tranformando a coluna para uma coluna de números inteiros
Gênero | A coluna possui os gêneros do filme separados por vírgulas o que dificultava uma análise utilizando os gêneros. Para resolver o problema dividi a coluna por delimitador (no caso a ,) fazendo com que cada coluna guardasse apenas um gênero. Criei uma nova tabela no power query chamada 'FilmesGeneros' para armazenar as informações dos gêneros com o id_nome para conseguir fazer uma relação com a tabela principal
Nota_IMDb | N/A
Resumo | N/A
Nota_Metacritic | N/A
Diretor| N/A
Estrela1, Estrela2, Estrela3, Estrela4 | A forma como os dados estavam disponiblizados não possibilitava uma análise utilizando a estrela dos atores. Para resolver isso transformei as 4 colunas em linhas e passei essa informação para uma outra tabela chamada 'FilmesEstrela' que continha também o id_nome para conseguir fazer uma relação com a tabela principal
Número de votos |  N/A
Receita | Foi necessário utilizar a ferramente de substituir valores para substituir as vírgulas que estavam nos números por nada. Ex: 28,341,469. Depois de fazer isso a coluna foi tranformada em númerica para conseguir utiliza-la. A coluna possui valores nulos, esses valorse foram subsituidos pela média da Receita dos filmes

Alguns outros tratamentos foram realizados para poder limpar, melhorar ou padronizar a base de dados.

### Relacionamentos

As 2 tabelas originais e as 2 tabelas criadas se relacionam em uma cardinalidade de 1:1, por meio da coluna 'Id_nome'.

## Desenvolvimento do Dashboard

O dashboard foi desenvolvido em Power BI. A empresa não especificou as cores desejadas, mas disponibilizou imagens de logo para serem usadas. Depois de escolhida a logo, criei o dashboard pensando em um visual alaranjado, utilizando a cor azul escuro para dar destaque nos dados.

![Página Gêneros](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%201/Screenshots/P%C3%A1gina%20G%C3%AAneros.PNG)
