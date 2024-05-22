# AbxTecnologia
Desafio proposto como segundo checkpoint de Disruptive architectures


### Angélica Ferreira de Matos Melo - RM550776
### Ricardo Yuri G. Domingues - RM551808
### Samara de Oliveira Moreira - RM552302
### Vinicius Monteiro Manfrin - RM552293
##

## Sobre nós
Nossa empresa é uma consultoria especializada em tecnologia, e foi contratada para fornecer suporte à ABXTecnologia. Esta empresa atua no segmento de importação e revenda de produtos, atendendo a uma variedade de clientes, que inclui desde pequenas lojas até grandes redes de supermercados e armarinhos.
##

## Entendendo o problema:
A maioria dos clientes da empresa solicitam prazos de pagamento superiores a 30 dias após a entrega dos produtos.

A empresa possui um time especializado em análise de crédito, onde esse time determina o limite máximo de crédito que cada cliente pode obter comprando a prazo. 

Dentro desse time de analistas, há uma separação onde existem especialistas em microcrédito, focados em pequenas operações, especialistas em concessão de crédito para grandes negócios, logo isso indica que a análise de crédito não é uniforme. E varia de acordo com o segmento do cliente.
##

## Definição do problema:
A empresa deseja traçar estratégias comuns para grupos de clientes, mas nunca realizou esse tipo de análise e não sabe como proceder. Os dados disponíveis incluem faturamento, ano de fundação e endividamento, mas não informações claras sobre o segmento ou tamanho dos clientes. Desenvolver essas estratégias beneficiaria significativamente os times de marketing e análise de crédito.

Após mapearmos o problema e definir grupos de clientes com suas características, a empresa planeja criar um robô automatizado. Para a nossa solução, o cliente solicitará o crédito, e retornaremos se será ou não aprovado.
##

## Bom, para criarmos toda essa resolução, utilizamos o Deep Analytics e modelos de Machine e Deep Learning, que é o que vamos apresentar neste momento!
##

## Nossa solução:
Quanto ao dataset, inicialmente tratamos os dados, adicionando nos valores nulos, a moda referente àquela coluna. Logo após, criamos o gráfico de correlação para entender de fato o que se relaciona no nosso dataset, tivemos esse resultado através de um gráfico de correlação:

## Pudemos analisar, no caso, que as variáveis que mais se relacionam, são:

Mas além disso, realizamos também a inserção de duas novas variáveis, como a classificação de nível. A partir de analisar o faturamento, o endividamento e o ano da fundação, classificamos então o tamanho da empresa, como: grande, médio e baixo nível (porte).

Logo após, utilizando os clursters, agrupamos os nossos clientes em 5 segmentos, com base nas colunas mencionadas anteriormente. Com o clursters, geramos um gráfico (Scatter Plot):

Conseguimos analisar que temos alguns grupos de clientes mais próximos, então as características são comuns, mas ainda assim há alguns segmentos dispersos.

## Análise com Boxplot
Com base nos clusters identificados, geramos um gráfico de boxplot para identificar outliers. Através dessa análise, observamos dois critérios importantes:

Primeiro, os valores de crédito solicitados variam amplamente, entre R$20.000,00 e R$45.000,00. Segundo, notamos que a maioria das aprovações ocorre para empresas que solicitam valores entre R$10.000,00 e R$30.000,00. 

Isso indica que há uma tendência de aprovação mais alta dentro dessa faixa específica de solicitação, o que pode guiar futuras recomendações de crédito e ajustes nas políticas de concessão.

Com base nessa análise, classificamos também o valor solicitado:


Através dessas informações obtidas, geramos o modelo de classificação de clientes aprovados ou não aprovados, utilizando o modelo de Regressão Logística, e tivemos esse retorno:

A partir desse modelo, pudemos atribuir ao nosso dataset informações de um novo cliente, já categorizando ele com a categoria do valor solicitado e o seu segmento.

## Esse é o nosso modelo, tendo como parâmetro esse novo cliente:

Um ponto a ser analisado é que com base nessas informações inseridas, e o valor solicitado ser de R$ 2.000,00, o crédito é aprovado, mas ao testar com R$ 20.000,00, o valor já é reprovado.

# Segmento 0:

#### Número de Solicitações: Elevado, com uma média de 4853 solicitações.
#### Maior Atraso: Relativamente baixo, com média de 22.91 dias.
#### Margem Bruta Acumulada: Média de 0.37, indicando uma margem razoável.
#### Percentual de Protestos: Quase inexistente (0.0019%).
#### Prazo Médio de Recebimento de Vendas: 22.48 dias, o que é uma média razoável.
#### Títulos em Aberto: Média de 40,553.77, com uma grande dispersão nos valores.
#### Valor Solicitado: Média de 436,268.60, mas com grande variação (máximo de 600 milhões).
#### Diferença Percentual de Risco: Alta, com média de 0.85.
#### Percentual de Risco: Baixo, com média de 0.15.
#### Valor Aprovado: Média de 109,357.20.
#### Ativo Circulante: Média de 14.64 milhões.
#### Passivo Circulante: Média de 9.81 milhões.
#### Total do Ativo: Média de 22.80 milhões.
#### Total do Patrimônio Líquido: Média de 12.23 milhões.

## Este segmento representa clientes com um alto volume de solicitações, baixa taxa de protestos e um perfil de risco relativamente controlado


