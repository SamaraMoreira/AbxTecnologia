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

![Descrição da Imagem](https://i.imgur.com/fMf5LQh.png)

## Pudemos analisar, no caso, que as variáveis que mais se relacionam, são:

![Descrição da Imagem](https://i.imgur.com/v9W4W2x.png)

Mas além disso, realizamos também a inserção de duas novas variáveis, como a classificação de nível. A partir de analisar o faturamento, o endividamento e o ano da fundação, classificamos então o tamanho da empresa, como: grande, médio e baixo nível (porte).

![Descrição da Imagem](https://i.imgur.com/UCWi9Kl.png)

Logo após, utilizando os clursters, agrupamos os nossos clientes em 5 segmentos, com base nas colunas mencionadas anteriormente. Com o clursters, geramos um gráfico (Scatter Plot):

![Descrição da Imagem](https://i.imgur.com/9ApVLWv.png)

Conseguimos analisar que temos alguns grupos de clientes mais próximos, então as características são comuns, mas ainda assim há alguns segmentos dispersos.

## Análise com Boxplot
Com base nos clusters identificados, geramos um gráfico de boxplot para identificar outliers. Através dessa análise, observamos dois critérios importantes:

Primeiro, os valores de crédito solicitados variam amplamente, entre R$20.000,00 e R$45.000,00. Segundo, notamos que a maioria das aprovações ocorre para empresas que solicitam valores entre R$10.000,00 e R$30.000,00. 

Isso indica que há uma tendência de aprovação mais alta dentro dessa faixa específica de solicitação, o que pode guiar futuras recomendações de crédito e ajustes nas políticas de concessão.

Com base nessa análise, classificamos também o valor solicitado:

![Descrição da Imagem](https://i.imgur.com/q56hGVz.png)
![Descrição da Imagem](https://i.imgur.com/tccj5a2.png)

Através dessas informações obtidas, geramos o modelo de classificação de clientes aprovados ou não aprovados, utilizando o modelo de Regressão Logística, e tivemos esse retorno:

![Descrição da Imagem](https://i.imgur.com/sDAOTU5.png)

A partir desse modelo, pudemos atribuir ao nosso dataset informações de um novo cliente, já categorizando ele com a categoria do valor solicitado e o seu segmento.

![Descrição da Imagem](https://i.imgur.com/Ch6EJFf.png)

## Esse é o nosso modelo, tendo como parâmetro esse novo cliente:

![Descrição da Imagem](https://i.imgur.com/Qfe1h4F.png)

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

# Segmento 1:

#### Número de Solicitações: Muito baixo, com média de 35.
#### Maior Atraso: Moderado, com média de 30.06 dias.
#### Margem Bruta Acumulada: Média de 0.096, muito baixa.
#### Percentual de Protestos: Inexistente.
#### Prazo Médio de Recebimento de Vendas: Muito baixo, 1.94 dias.
#### Títulos em Aberto: Média de 73,164.57, alta considerando o número de solicitações.
#### Valor Solicitado: Média de 1.02 milhões.
#### Diferença Percentual de Risco: Moderada, com média de 0.73.
#### Percentual de Risco: Alta, com média de 0.27.
#### Valor Aprovado: Média de 847,771.40.
#### Ativo Circulante: Muito alto, média de 2.43 bilhões.
#### Passivo Circulante: Média de 1.84 bilhões.
#### Total do Ativo: Média de 4.16 bilhões.
#### Total do Patrimônio Líquido: Média de 1.11 bilhões.

## Este segmento parece representar grandes empresas ou instituições financeiras com baixo número de solicitações, mas com grandes volumes financeiros e ativos significativos. O risco percebido é moderado a alto.

# Segmento 2:

#### Número de Solicitações: Moderado, com média de 358.
#### Maior Atraso: Alta, com média de 40.93 dias.
#### Margem Bruta Acumulada: Média de 0.389, alta.
#### Percentual de Protestos: Inexistente.
#### Prazo Médio de Recebimento de Vendas: Muito alto, 121.61 dias.
#### Títulos em Aberto: Muito alto, média de 877,189.62.
#### Valor Solicitado: Muito alto, média de 11.43 milhões.
#### Diferença Percentual de Risco: Moderada, com média de 0.77.
#### Percentual de Risco: Moderada, com média de 0.23.
#### Valor Aprovado: Alta, média de 1.89 milhões.
#### Ativo Circulante: Alta, média de 86.93 milhões.
#### Passivo Circulante: Alta, média de 58.59 milhões.
#### Total do Ativo: Alta, média de 111.83 milhões.
#### Total do Patrimônio Líquido: Média de 52.94 milhões.

## Este segmento inclui clientes com volumes altos de solicitações e valores, mas também com um risco moderado e períodos longos de recebimento de vendas. Possivelmente são grandes empresas com fluxo financeiro robusto.

# Segmento 3:

#### Número de Solicitações: Muito baixo, com média de 6.
#### Maior Atraso: Relativamente baixo, com média de 28 dias.
#### Margem Bruta Acumulada: Média de 0.274.
#### Percentual de Protestos: Muito alto, 18.91%.
#### Prazo Médio de Recebimento de Vendas: Alto, 89.17 dias.
#### Títulos em Aberto: Nenhum.
#### Valor Solicitado: Muito baixo, média de 24,167.
#### Diferença Percentual de Risco: Moderada, com média de 0.76.
#### Percentual de Risco: Moderada, com média de 0.24.
#### Valor Aprovado: Muito baixo, média de 17,500.
#### Ativo Circulante: Nenhum.
#### Passivo Circulante: Nenhum.
#### Total do Ativo: Nenhum.
#### Total do Patrimônio Líquido: Nenhum.

## Este segmento pode representar clientes problemáticos ou não ativos, com baixíssimo número de solicitações e alto percentual de protestos, mas sem registros significativos de ativos ou passivos.

# Segmento 4:

#### Número de Solicitações: Alto, com média de 3685.
#### Maior Atraso: Relativamente baixo, com média de 25.31 dias.
#### Margem Bruta Acumulada: Média de 0.347.
#### Percentual de Protestos: Muito baixo, 0.0057%.
#### Prazo Médio de Recebimento de Vendas: 14.40 dias.
#### Títulos em Aberto: Média de 18,243.01.
#### Valor Solicitado: Média de 125,284.30.
#### Diferença Percentual de Risco: Relativamente baixa, com média de 0.614.
#### Percentual de Risco: Relativamente alta, com média de 0.386.
#### Valor Aprovado: Média de 61,046.86.
#### Ativo Circulante: Média de 6.24 milhões.
#### Passivo Circulante: Média de 7.41 milhões.
#### Total do Ativo: Média de 10.23 milhões.
#### Total do Patrimônio Líquido: Média de 4.43 milhões.

## Este segmento representa clientes com um número alto de solicitações e valores moderados. O risco é relativamente baixo, com ativos e passivos menores comparados aos outros segmentos.

# Em resumo:

#### Segmento 0: Maior número de solicitações e maior patrimônio líquido. 

#### Segmento 1: Maior margem bruta acumulada e maior valor aprovado. 

#### Segmento 2: Maior atraso e maior média de valor solicitado. 

#### Segmento 3: Maior percentual de protestos e nenhum registro significativo de ativos ou passivos.

#### Segmento 4: Maior atividade e valores moderados, com risco relativamente baixo.
