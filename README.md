# Rocket House Project

Este é um projeto fictício. Todo o contexto e perguntas são fictícias.

# Índice

- [Índice](#índice)
- [Descrição do Projeto](#descrição-do-projeto)
- [Atributos](#atríbutos)
- [Premissas do Negócio](#premissas-do-negócio)
- [Estratégias Utilizadas](#estratégias-utilizadas)
- [Principais Resultados](#principais-resultados)
- [Validação de Hipóteses](#validação-de-hipóteses)
- [Questões do Negócio](#questões-do-negócio)
- [Conclusão](#conclusão)
- [Ferramentas Utilizadas](#ferramentas-utilizadas)

# Descrição do Projeto

House Rocket é uma empresa que trabalha com compra e venda de imóveis, que busca maximizar a sua receita, através de boas oportunidades de negócio.

Todos os dados para o projeto foram retirado do [Kaggle](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction)

# Atríbutos

|   Atributos   |                                         Significado                                         |
| :-----------: | :-----------------------------------------------------------------------------------------: |
|      id       |                       Numerção únida de identificação de cada imóvel                        |
|     date      |                                    Data da venda da casa                                    |
|     price     |                    Preço que a casa está sendo vendida pelo proprietário                    |
|   bedrooms    |                                      Número de quartos                                      |
|   bathrooms   |                                     Número de banheiros                                     |
|  sqft_living  |                   Tamanho em pés quadrado do espaço interior dos imóveis                    |
|   sqft_lot    |                             Tamanho em pés quadrado do terreno                              |
|    floors     |                                 Número de andares do imóvel                                 |
|  waterfront   |              Variável que indica a presença de vista para água (0=não e 1=sim)              |
|     view      | Índice de qualidade da vista do imóvel, variando de 0 a 4, onde 0 é pior vista e 4 a melhor |
|   condition   |        Ínidice de condição do imóvel, variando de 0 a 5, sendo 5 em melhor condição         |
|     grade     |     Índice de construção e desing do imóvel, variando de 0 a 13, sendo a 13 melhor nota     |
| sqft_basement |                              Tamanho em pés quadrados do porão                              |
|   yr_built    |                                      Ano de construção                                      |
| yr_renovated  |                                       Ano de reforma                                        |
|    zipcode    |                                        CEP do imóvel                                        |
|      lat      |                                          Latitude                                           |
|     long      |                                          Longitude                                          |
| sqft_living15 |   Tamanho em pés quadrados do espaço interno do imóvel para os 15 vizinhos mais próximos    |
|  sqft_lot15   |              Tamanho em pés quadrados do terreno dos 15 vizinhos mais próximos              |

# Premissas do Negócio

- Valores iguais a zero em yr_renovated são casas que nunca foram reformadas;
- O valor 33 em bathroom foi considerado um erro e deletada do dataset;
- Valores iguais a zero em sqft_basement são locais que não possuem porão;
- Foi considerado que as estações do ano são verão para os meses 6,7 e 8, primavera para os meses 3, 4 e 5, outono para os meses 9, 10 e 11, inverno para os meses 12, 1 e 2.
- Valores duplicados de ID foram removidos deixando somente o mais recente.
- Os fatores decisivos para a indicação da compra dos imóveis foram, condição do imóvel, localidade e preço.
- A estação do ano foi a característica decisava para a época de venda do imóvel.

# Estratégias Utilizadas

1. Coleta de Dados via Kaggle
2. Entendimento do negócio
3. Tratamento dos dados.
   - Corrigindo os tipos de variáveis
   - Criando novas features
   - Verificando valores duplicados
   - Verificando valores nulos
4. Análise estatística
5. Exploração de dados
6. Teste de Hipóteses
7. Questões do negócio
8. Conclusão

# Principais Resultados

- Os imóveis com vista para a água são 30% mais caros.
  - Na verdade os imóveis com vista para água são média 212% mais caros.
- Imóveis com data de construção menor que 1955 são em média 50% mais baratos.
  - O ano de construção do imóvel não infulicar diretamente no preço.
- Imóveis em boas condições e com vista para água são pelo menos 10% mais caros em comparação aos em boas condições e sem vista para água.
  - Comparando imóveis em boas condições os que possuem vista para água são em média 163% mais caros.

# Validação de Hipóteses

|                                                                   Hipótese                                                                   | Resultado  | Indicações                                                                                                                                  |
| :------------------------------------------------------------------------------------------------------------------------------------------: | :--------: | ------------------------------------------------------------------------------------------------------------------------------------------- |
|                                     H1 - Imóveis com a vista para a água são peloo menos 30% mais caros.                                     | Verdadeiro | Fazer uma maior monitoramento para oportunidades com imóveis com vista para água                                                            |
|                               H2 - Imóveis com data de construção menor que 1955 são em média 50% mais baratos                               |   Falso    | Não deixar o ano de construção ser um fator decisivo para realizar o investimento                                                           |
|                     H3 - Imóveis sem porão poussem área total (sqrt_lot) pelo menos 50% maiores do que imóveis com porão                     |   Falso    | Imóveis sem porão não apresentam forte apelo para investimento                                                                              |
|                                     H4 - O crescimento do preço dos imóveis ano após ano (YoY) é de 10%                                      |   Falso    | Apesar do crescimento ser inferior a 1%, é de grante interesse que se realize o investimento o quanto antes, para maior margem de lucro.    |
|                                          H5 - Imóveis com 3 banheiros tem um crescimento MoM de 15%                                          |   Falso    | Deve-se atentar no momento que vai ser realizada a compra, pois os valores oscilaram entre subidas e descidas                               |
|             H6 - Imóveis com data de construção inferior a 1955 e reformados são 50% mais baratos, comparado aos não reformados              |   Falso    | Imóveis com estas característica podem ser oportunidades de investimento                                                                    |
|       H7 - Imóveis em boas condições e com vista para água são 20% mais caros em comparação aos em más condições e com vista para água       |   Falso    | Realizar o investimento em móveis em boas condições e com vista para água é mais interessante devido ao preço menor por uma qualidade maior |
| H8 - Imóveis em boas condições e com vista para água são pelo menos 10% mais caros em comparação aos em boas condições e sem vista para água | Verdadeiro | Fazer uma maior monitoramento para oportunidades com imóveis com vista para água                                                            |
|                        H9 - Imóveis que nunca foram reformados são pelo menos 10% mais baratos que os não reformados                         | Verdadeiro | Estes podem ser uma oportunidade, podendo realizar uma reforma e agregando um maior valor ao imóvel                                         |
|                                     H10 - H10: Imóveis construídos antes de 1955 possuem mais banheiros                                      |   Falso    | Imóveis mais recentes possivelmente seja mais atrativo a família maior devido a uma quantidade maior de banheiros                           |

# Questões do Negócio

1. Quais casas o CEO da Rocket House deveria comprar e por qual preço?

   Após a realização de uma filtragem através da mediana do preço dos imóveis pelo Cep, foram selecionados 712 possíveis investimentos que apresentam valor inferior ao preço da mediana e que se encontram em boas condições.

2. Uma vez a casa em posse da empresa, qual o melhor momento para vendê-las e qual seria o preço da venda ?

   Os imóveis indicados para a compra foram agrupados pela sazonalidade, no qual o preço de venda indicado foi da calculado da seguinte forma, caso o valor do imóvel fosse maior o que o preço da mediana, ocorreria um aumento no valor para venda de 10%, caso o preço fosse menor que o da mediana o aumento no valor para venda seria de 30%. Caso seja realizado todas as compras e vendas coms os valores indicados a empresa consiguirá um lucro de U$63.061.590,80.

# Conclusão

Os imóveis apresentedados podem possuir boas oportunidade investimento, tais como os imóveis antigos que não foram reformados, que apresentam valor bem abaixo dos outros reformados, então desta forma seria interessante buscar oportunidades como estas, tal qual também realizar um maior estudo da evolução do preço dos imóveis para uma melhor projeção de preço de possíveis futuras compras de acordo com o histórico de preço de anos anteriores.

# Ferramentas Utilizadas

- Jupyter Notebook;
- Visual Studio Code;
- GitHub.
