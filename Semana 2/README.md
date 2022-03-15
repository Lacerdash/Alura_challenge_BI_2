# [Semana 2](https://www.alura.com.br/challenges/bi-2/semana-02-food) - Alura Challenge BI 2ª Edição

A **Alura Food** tem interesse em **expandir** seu negócio entrando no mercado **indiano**. Para isso, ela precisa da sua ajuda na **criação de métricas e análise dos dados** disponibilizados para tomar a **melhor decisão**.

## Base de Dados

Para isso, ela disponibilizou uma base de dados com informações de restaurantes retiradas do aplicativo Zomato, um aplicativo de busca de restaurantes para pessoas que queres sair para jantar, buscar comidas ou pedir em casa e que está presente em diversos países, como Índia, Brasil, Estados Unidos, Catar, entre outros<sup>[1](https://pt.wikipedia.org/wiki/Zomato)</sup>.

Essas informações foram entregues em 7 arquivos diferentes:

- 5 arquivos do tipo JSON, que tem as informações sobre os restaurantes
- 1 planilha do Microsoft Excel com um dicionário de código dos países
- 1 documento do Microsoft Word com descrições sobre os arquivos e suas colunas

## Métricas

A empresa requisitou que as seguintes métricas estivessem no relatório:

- Filtrar por cidade, restaurantes e se tem reserva
- Total de restaurantes na Índia
- Preço Médio
- Média de avaliação
- Porcentagem de restaurantes que tem ou não delivery online
- Cidades que mais possuem restaurantes
- Culinárias que mais são exploradas da Índia
- Restaurantes por cidade e suas classificações

Como um bônus, porém sem a necessidade de aparecerem no relatório, a empresa requisitou as seguintes tarefas:

- Preço Médio através das moedas
- Página de estudo sobre cada restaurante

### Relacionamentos

Os 5 arquivos do tipo JSON possuem informações complementares que devem ser juntadas em 1 única tabela. Por isso não há relacionamentos entre os arquivos.

## Tratamento de dados

Primeiramente decidi tratar os dados via [Python Pandas](https://pandas.pydata.org/). Porém os arquivos JSON estão com informações aninhadas, isto é: as informações referentes ao restaurante estão em uma lista dentro de uma outra lista. Após tentar algumas soluções sem sucesso, migrei o tratamento das tabelas para a plataforma Power BI. Ao migrar para o Power BI, perdi algumas facilidades para limpeza de dados que a biblioteca Pandas permite, porém consegui resolver meu problema.

### Tratamentos no Power BI

#### Tratamento arquivos individuais
Para iniciar o tratamento, importei o arquivo 'file1.json' para a ferramenta. O arquivo entao foi lido e navegado até que as colunas do arquivo fossem mostradas.

![Primeira Etapa](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%202/Screenshots/Primeira%20etapa.PNG)

Utilizei a funcinalidade 'Acrescentar Consultas como Novas'. Essa funcinalidade me permitiu ter uma tabela única com as informações combinadas dos 5 arquivos. Para essa tabela dei o nome de 'base de dados'

Depois vi que as colunas não correspondiam com as informações que a empresa me passou. Ao estudar o arquivo, entendi que as informações requisiatadas pela empresa estavam dento da coluna *restaurants*, e que as outras podiam ser ignoradas para esse processo.

![Segunda Etapa](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%202/Screenshots/Segunda%20etapa.PNG)

Por último, naveguei até que as informações desejadas dos restaurantes fossem exibidas.

![Terceira Etapa](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%202/Screenshots/Terceira%20etapa.PNG)


#### Tratamento da tabela 'Restaurantes'

Com a tabela criada, a limpeza dos dados, que seria igual nos 5 arquivos, foi unificada. Essa tabela continha mais de 29753 linhas com informações de restaurantes. Além dessas, 848 linhas estavam sem informações. Para essas linhas serem excluidas, considerei que a coluna 'id' como sendo não nula e também que deve ser única, o que me levou a excluir valores duplicados também nesta coluna. Filtrei os dados pela coluna 'País' para aparecer so os dados dos resturantes Indianos. Além disso mesclei a tabela 'base de dados" com a planilha do Microsoft Excel com um dicionário de código dos países para depois extrair o nome do país para a tabela 'base de dados' e poder eliminar a coluna 'country id'.

Após essas tranformações, retirei de outras listas informações sobre os comentários e notas sobre o restaurante, vindos da coluna 'user_rating' e também sobre a localização, da coluna 'location'. 

Outras duas colunas ('offers' e 'establishment_types') também continham informações aninhadas, porém houve erro no momento de extração das informações. As colunas 'api.key' e 'deeplink' contém informações internas do aplicativo e a coluna 'res_id' contém as mesmas informações que a coluna 'id'. De acordo com a empresa, a coluna 'switch_to_order_menu' contém informações para trocar o tipo de menu, informação que não será aproveitada no dashboard, assim como a coluna 'zipcode', com informações de CEP dos restaurantes, porém com muitas informações faltantes. Essas e outras colunas foram excluidas do modelo para melhorar a legibilidade e performance. 

Título Original | Descrição da empresa | Título Novo | Tipo Definido
--------------- | -------------------- | ----------- | -------------
url|*a empresa não forneceu informação*|Site|
id|ID exclusivo de cada restaurante em várias cidades do mundo|ID do Restaurante| Texto
name | Nome do restaurante | Nome do Restaurante | Texto
country|País em que o restaurante está localizado|País| Texto
city|Cidade em que o restaurante está localizado|Cidade| Texto
address|Endereço do restaurante|Endereço| Texto
locality_verbose|Descrição detalhada da localidade|Endereço detalhado| Texto
latitude|Coordenada de latitude da localização do restaurante|Latitude| Texto
longitude|Coordenada de longitude da localização do restaurante|Longitude| Texto
average_cost_for_two|Custo para dois pessoas em diferentes moedas|Custo para duas pessoas| Número decimal fixo
currency|Moeda do país|Moeda| Texto
has_table_booking|Tem Reserva de mesa|Aceita reserva?| Texto Binário
has_online_delivery | Tem Entrega online | Tem entrega Online? | Texto binário
is_delivering_now | Está a entregar | Está entregando agora? | Texto binário
price_range | Faixa de preço da comida | Faixa de Preço | Texto
rating_text | Texto com base na classificação da classificação | Review dos usuários | Texto
rating_color | Cor dependente da classificação média | Cor da review | Texto
votes | Número de classificações feitas por pessoas | Número de Votos | Número inteiro
aggregate_rating | Classificação agregada (de 0 a 5) | Média de votos | Número decimal fixo


As informações de culinária dos restaurantes foram passadas para uma nova tabela 'culinária' que possui 2 colunas: 'Id do restaurante' (para poder ralacionar com a tabela 'base de dados' e 'Culinárias'dividida' (que possui a culinária do restaurante). 

Após as correções de tipo e de informações, a base de dados diminuiu de 30601 linhas para 8652 linhas. A diminuição das informações irá auxiliar na criação de um dashboard mais focado nas necessidades da empresa.


## Desenvolvimento do Dashboard

O dashboard foi desenvolvido em Power BI. A empresa não especificou as cores desejadas, mas disponibilizou imagens de logo para serem usadas. Depois de escolhida a logo, criei o dashboard pensando em um visual escuro, utilizando a cor verde para dar destaque nos dados.

![Página Análise de restaurantes Índia sem filtro](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%202/Screenshots/An%C3%A1lise%20de%20restaurantes%20%C3%8Dndia%20sem%20filtro.PNG)

## Ferramentas utilizadas
  Para a criação do dashboard foi utilizado o Microsoft Power BI. Para o plano de fundo foi utilizado o Microsoft Power Point. 
  
  ### Fontes dos ícones:
  
  Os ícones foram baixados do site [Flat Icon](https://www.flaticon.com/):




