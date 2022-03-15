# [Semana 3 e 4](https://www.alura.com.br/challenges/bi-2/semana-03-04-skimo) - Alura Challenge BI

A **Alura Skimo** necessita acompanhar suas **vendas** através de um painel que comporte todas métricas necessárias. 

## Base de Dados

Para a criação dos dashboards, a empresa disponolizou um bando de dados MySQL, contendo 5 tabelas relacionadas entre si. As tabelas trazem informações complementares a respeito de clientes, produtos, pedidos e vendedores:

![image](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/mysql.PNG)


- A tabela *categorias* traz informações sobre a categoria dos produtos (se é picolé ou sorvete) e conta com um ID, utilizado como chave primária.
- A tabela *clientes* traz informações sobre os clientes: Nome, endereço, gênero, data de nascimento e CPF, que funciona como um ID e chave primária da tabela.
- A tabela *itens_pedido* traz informações sobre os itens incluidos em cada pedido e suas quantidades
- A tabela *pedido* traz informações sobre os pedidos feitos: data de venda, qual foi o vendedor e qual foi o cliente. Essa tabela tem uma coluna 'ID Pedido' que funciona como chave primária.
- A tabela *produtos* traz informações sobre os produtos disponíveis para a venda como preço, custo, tamanho, sabor e família de produtos. Também conta com um ID próprio de cada produto.
- A tabela *vendedores* traz informações como data de admissão, nome, percentual de comissão e matrícula do vendedor, que funciona como chave primária.

Primeiramente o banco de dados foi recuperado no computador e depois foi feita a conexão ao Power BI. Após a importação e antes do tratamento dos dados, verifiquei as relações existentes entre as tabelas. A ferramenta já havia relacionado algumas tabelas, porém alguns relacionamentos foram criados. 

Além disso criei uma nova tabela 'Tabela_data' usando a linguagem M

![tabela data](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/Tabela_data1.PNG)

### Relacionamentos

As tabelas se relacionam entre si da seguinte maneira:

Tabelas  | Coluna | Relacionamento
---------|--------|---------------
*itens_pedido* - *pedido* | ID pedido | m:1
*itens_pedido* - *produto* | ID Produto | m:1
*pedido* - *categorias* | ID Cliente (CPF) | m:1
*pedido* - *vendedores* | ID vendedor | m:1
*pedido* - *Tabela_data* | Data_venda | m:1
*produto* - *categorias* | ID Produto | m:1


Essas relações foram implementadas no Power BI.

![image](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/relacionamento.PNG)

## Métricas

Com a base de dados, a empresa espera que algumas informações sejam exibidas no dashboard.

- Faturamento
- Ranking de produtos vendidos
- Vendedores que mais geram faturamento
- Custo
- Quantidade de vendas
- Lucro
- Categorias mais vendidas
- Ticket médio por venda

Como um bônus, porém sem a necessidade de aparecerem no relatório, a empresa requisitou as seguintes tarefas:

- Dashboard de vendedores e produtos
- Dashboard de produtos: análise de cenário
- Dashboard de produtos: previsão de faturamento


## Tratamento de dados

Após a recuperação do banco de dados e da importação no Power BI, analisei as informações contidas nas tabelas. Durante essa análise, percebi que a tabela *produtos* precisava ser tratada com mais calma. As outras tabelas possuíam apenas problemas pontuais, como efetuar a troca do tipo de dados, e de padronização dos nomes das colunas, deixando todos com a letra inicial em maiúscula.

### Tabela produtos

Na tabela de produtos, para poder deixar o dashboard mais dinâmico, decidi fazer alguns tratamento de dados. Esses tratamentos permitirão o uso de outros filtros.

![produto1](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/produtos1.PNG)

Após primeira análise, decidi por dividir a coluna *Descritor* em 3 colunas distintas: *peso*, *sabor* e *embalagem*. Após isso, foram excluidos dos dados possívels caracteres brancos nos dados e a tabela foi padronizada da mesma forma que as outras.

![produto2](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/produtos.PNG)

Durante o desenvolvimento do dashboard, percebi que existiam informações incompletas. Há informações na tabela *itens_pedido* que não estão presentes na tabela *pedidos*: os pedidos com ID '3375', '53715', '70186' e '77333' estão apenas com informações de quantidades vendidas, mas não contém informações de datas de vendas, vendedor ou cliente. Há também o pedido nº '121', que utiliza um CPF não cadastrado na base de dados e o pedido '146, que utiliza um produto não cadastrado. Essas informações estão em 20 linhas da base de dados, de um total de 213.364 linhas na tabela *itens_pedido* e em 6 linhas dentro de um total de 87.873 linhas na tabela *pedidos*. Para esse dashboard, irei excluir as linhas com as informações equivocadas e informarei a empresa a respeito dos erros.

Após a criação da tabela e limpeza dos dados, foi possível criar as hierarquias desejadas.

## Desenvolvimento do Dashboard

De acordo com os pedidos da empresa dividi o dashboard em 4 páginas. A primeira página funcionará como página inical trazendo informações chave a respeito da empresa como faturamento, custo, comissão e lucro. Junto a essas informações, será exibido um gráfico de linhas trazendo a informação de quantidade vendida ao longo do tempo, faturamento por categoria, qtd vendida por categoria, faturamento por estado e filtros por ano, mês e categoria.

A segunda página terá informações dos venderores. Serão exibidos os valores de faturamento, qtd pedidos, comissão, além de outros gráficos e indicadores de desempenho. Será possível escolher o vendedor por meio de filtros também. 

A terceira página será destinada aos produtos. Serão exibidos os valores faturamento, custo, margem percentual, unidades vendidas, além de gráficos e 2 indicadores de desempenho. Será possível escolher o produto, categoria, embalagem, sabor e peso por meio de filtros também. 

E a quarta página será a dos cenários. Nessa página é possível criar cenários e ver quais implicaçãoes no faturamento, custo, comissão e lucro esses cenários trazem, assim como um texto dinâmico baseado na escoha do usuário.

### Criação de medidas 

Para a criação dos dashboards financeiro, de vendedores e de produtos, foram criadas algumas métricas para fazer o cálculo do valor. A criação de métricas permite uma legibilidade maior e fácil transferência de ideias.

![image](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/medidas.PNG)

Medida  | Fórumla DAX | Descrição
---------|--------|---------------
Comissão | -SUMX(Vendedores,[Faturamento] * Vendedores[Comissão]) | Calcula a comissão total e por vendedor.
Custo | -SUMX('Itens do Pedido', [Quantidade Vendida] * RELATED(Produtos[Custo])) | Calcula o custo de produção
Margem | [Faturamento] + [Custo] + [Comissão] | Calcula o lucro final.
Faturamento | SUMX('Itens do Pedido', [Quantidade Vendida] * RELATED(Produtos[Preço])) | Calcula o faturamento total das vendas.
Qtd Itens Vendidos | SUM('Itens do Pedido'[Quantidade Vendida]) | Mostra a quantidade de itens vendidos.
Qtd pedidos | COUNT(Pedido[ID Pedido]) | Exibe a quantidade total de vendas no período.
Ticket Médio | [Faturamento]/[Qtd pedidos] | Calcula o ticket médio por venda.

Além das medidas anteriores, foi criadas uma nova tabela, que terá medidas para serem utilizadas na página de análise de cenários. Em conjunto com a nova tabela, foram criados parâmetros para serem ajustados pelo cliente. 


![image](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/parametros.PNG)


Todos os parâmetros foram criados da mesma forma:

![image](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/parametro%20cria%C3%A7%C3%A3o.PNG)

Após a criação dos parâmetros, foi possível criar as novas medidas para a página de cenários.

![image](https://github.com/Lacerdash/Alura_challenge_BI_2/blob/main/Semana%203/Screenshots/medidas%20cen%C3%A1rios.PNG)

Medida  | Fórumla DAX | Descrição
---------|--------|---------------
Comissão cenário | *[Comissão] * (1 + [% alteração comissão Valor])*  | Calcula o novo valor da comissão com base no cenário
Custo cenário | *[Custo] * (1 + [% alteração custos Valor])* | Calcula o novo custo com base no cenário
Diferença comissão | *'Medidas cenários'[Comissão cenário] - [Comissão]*  | Calcula a diferença da comissão real X a do cenário
Diferença custo | *'Medidas cenários'[Custos cenário] - [Custo]* | Calcula a diferença do custo real X a do cenário
Diferença fat | *[Faturamento cenário] - [Faturamento]* | Calcula a diferença do faturamento real X a do cenário
Diferença lucro | [Lucro previsto] - [Lucro] | Calcula a diferença do lucro real X a do cenário
Faturamento cenário | *[Faturamento] * (1 + [% alteração faturamento])* | Calcula o faturamento total, com base no cenário
Lucro Previsto | [Preço cenário] + [Custo previsto] + [Comissão prevista] | Calcula o lucro final.
Texto cenário | "Se o faturamento " & if('Paramêtros faturamento'[% alteração faturamento] >= 0, "aumentar ", "diminuir ") & FORMAT([% alteração faturamento],"0%") & ", os custos " & if('Parametro custos'[% alteração custos Valor] >= 0, "aumentarem ", "diminuirem ") & FORMAT([% alteração custos Valor],"0%") & " e a comissão " & if('Parametro comissão'[% alteração comissão Valor] >= 0, "aumentar ", "diminuir ") & FORMAT([% alteração comissão Valor],"0%") & " o lucro irá " & if([Diferença lucro] >= 0, "aumentar ", "diminuir ") & FORMAT('Medidas cenários'[Diferença lucro],"R$#,##0") | Cria o texto dinâmico que aparece embaixo da página de cenários dependendo das alterações que a pessoa escolher

Além dessas medidas outras medidas foram criadas e utilizadas nos visuais, como o visual de indicadores na página de vendedores e produtos que possui ambos os valores e o título vinculado a medidas.

Com as medidas criadas, o dashboard foi desenvolvido com 4 páginas. 

## Feramentas Utilizadas

Para a criação do dashboard foi utilizado o Microsoft Power BI. Para o plano de fundo foi utilizado o Microsoft Power Point.

### Paleta de cores:

A paleta de cores foi derivada em grande parte do site [My color Space](https://mycolor.space/), com algumas pequenas alterações. 

### Fontes dos ícones:

Os ícones foram baixados do site [Flat Icon](https://www.flaticon.com/):

