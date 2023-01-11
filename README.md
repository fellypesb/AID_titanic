# Análise Inicial dos Dados
- **Dataset:** Titanic - Machine Learning from disaster 
- **Endereço web:** [https://www.kaggle.com/competitions/titanic/data?select=train.csv](https://www.kaggle.com/competitions/titanic/data?select=train.csv)

![](https://www.fatosdesconhecidos.com.br/wp-content/uploads/2019/01/capa-147.jpg)

## Problema

Este dataset apresenta informações sobre os passageiros do famoso navio titanic operado pela _white star line_ e que, após a colisão com um grande _iceberg_, teve seu tão memorável naufrágio em 1912. Infelizmente, nem todos os passageiros conseguiram se salvar resultando na morte de 1502 passageiros dentre um total de 2224. Embora houvesse algum elemento de sorte envolvido na sobrevivência, parece que alguns grupos de pessoas eram mais propensos a sobreviver do que outros. Nesse sentido, o _kaggle_ apresenta-nos um desafio instigando-nos a contruir um modelo preditivo que responda a seguinte pergunta: “que tipo de pessoa tem maior probabilidade de sobreviver?” usando os dados do passageiro (ou seja, nome, idade, sexo, classe socioeconômica, etc).

## Instâncias e Atributos

Após analisar os dados obtidos constatou-se que este apresenta 891 linhas e 12 colunas de dados que representam as **instâncias** e **atributos** desta base de dados.

## Dicionário de dados

Abaixo apresenta-se os atributos contidos nesta base de dados bem como suas definições e valores possíveis.

|Atributos| Definição | Valores |
|:---|:---:|---:|
|PassengerId| ID do passageiro | chave única |
|Survived| Sobrevivente | [0, 1]|
|Pclass| Ticket da classe do passageiro| [1, 2, 3]|
|Name| Nome do passageiro| chave diversa |
|Sex| sexo do passageiro| [male, female]|
|Age| idade do passageiro| chave diversa|
|SibSp|Nº de irmãos/cônjuges a bordo|[0,1,2,3,4,5,8]|
|Parch|Nº de pais/filhos a bordo|[0,1,2,3,4,5,6]|
|Ticket|Número do bilhete | chave diversa |
|Fare| Tarifa de passageiro |chave diversa |
|Cabin| Número da cabine | chave diversa |
|Embarked|Porto de embarque| [C,Q,S]|

Neste problema, nosso atributo alvo é o  _**Survived**_ e como este atributo possui apenas dois possíveis valores, ou zero ou um, podemos então dizer que este problema trata-se de classificação, em que temos duas classes: a classe de sobreviventes ao nafrágio e a classe de não sobreviventes ao naufrágio.

## Tipo dos atributos
Analisando cada atributo podemos identificar diferentes tipos para cada um deles. Na tabela abaixo, apresenta-se os atributos e seus respectivos tipos (discutidos em sala de aula) que estão presentes na base de dados.

|Atributos| Tipo |
|:---:|:---:|
| Survived | Discreta | 
| Pclass | Ordinal | 
| Name | Nominal |
| Sex | Nominal | 
| Age | Racional | 
| SibSp | Discreta |
| Parch | Discreta |
| Ticket | Heterogêneo | 
| Fare | Continua |
| Cabin | Heterogêneo | 
| Embarked | Discreta | 

## Qualidade dos dados

Ao realizar uma breve análise dos dados encontrou-se alguns valores _null_ ou _not a number_ presentes nos atributos: **Age**, **Cabin** e **Embarked**, a quantidades desses valores está resumida na tabela abaixo. Podemos perceber que existe uma grande quantidade de dados faltosos no atributo **Cabin** o que poderá invibializar o uso desse atributo, visto que, a quantidade de dados faltosos representa cerca de 77% do total de intâncias da base de dados.

|Atributos| Dados _null_ |
|:---:|:---:|
| Age | 177 | 
| Cabin | 687 | 
| Embarked | 2 |

Em relação a relevância dos atributos todos aparentemente são úteis e relevante para o contexto do problema, exceto, o atributo **Name** que nos fornece apenas a informação do nome dos passageiros, algo que não tem nenhum impacto em sua sobrevivência. Porém, este atributo também apresenta os titulos de nobreza de cada passageiro, algo que poderia ser utilizado para construção de um novo atributo apenas com os títulos de cada passageiro, levando-se em consideração que, supostamente, passageiros com título de nobreza mais alto teriam maiores chances de sobreviver em relação aos passageiros com título de nobreza mais baixo.

Ao observar o atributos **Ticket**, encontrou-se uma grande quantidade de valores distintos e aparentemente sem nenhum tipo de padronização. Neste caso, uma investigação acerca de sua relevância para o problema seria interessante.

Uma possível inconsistência nos dados foi observada em relação a idade dos passageiros, visto que, alguns deles apresentam idade menor que 1. Ou apenas sejam os bebês presentes no navio. Porém, algo que chamou atenção é que todos eles sobreviveram.

Possíveis _outliers_ foram identificados no atributo **Fare**, em foram encontrados excepcionalmente 3 (três) amostras que as suas tarifas de embarque foram de 512, valor extremamente alto e que foge do padrão dos dados. 

## Análises Extras

Ao explorar um pouco mais os dados encontrou-se algo interessante cerca de 15 pessoas não pagaram tarifa para realizar a viagem e dentre esses passageiros encontrou-se as seguintes características: todos eles eram homens, não tinha parentes a bordo, embarcaram em Southampton, e além disso, dentre os 15 apenas 1 sobreviveu.

A média de idade dos passageiros foi de 29 anos com um desvio padrão de 14.53. Tendo-se como idade mínima, 0.42 e idade máxima, 80 anos.

Em relação a taxa de sobreviventes (desta amostra de dados) apenas 38% dos passageiros sobreviveram, como pode ser constatado observando-se a distribuição do atributo **Survived**. 

|Survived| Quantidade |
|:---:|:---:|
| 0 | 549 | 
| 1 | 342 | 

Outro fato interessante encontrado é que a taxa de sobrevivência entre os passageiros de 1° classe foi maior do que das demais classes inferiores.

|Pclass| Sobreviventes |
|:---:|:---:|
| 1 | 136 | 
| 2 | 87 |
|3| 119|


