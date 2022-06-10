# Topic Modeling

![image](img.png)

Esse notebook servirá de guia para a execução de uma análise de tópicos completa, usando o algoritmo de LDA e recursos para interpretação dos resultados.

## Sumário
1. [Introdução](#introduction)
2. [Dataset](#dataset)
3. [Download dos dados do kaggle](#download-dos-dados)
4. [Verificando as Estatísticas do Corpus](#estatisticas-corpus)
5. [Seleção dos dados relevantes para a análise](#Seleção-dos-dados-relevantes-para-a-análise)
6. Instalação das principais ferramentas e importação de módulos
7. Pré-processamento usando NLTK
8. Pré-processamento usando Spacy
9.Análise de tópicos usando LDA
10.Análise de NER usando Spacy
11.Visualização dos tópicos usando tokens e entidades.

## [Introdução](#introduction)

Uma tarefa importante para cientistas de dados é realizar o agrupamento de dados, sem conhecimento prévio. Ao trabalhar com um grande volume de documentos, uma das primeiras perguntas que você deseja responder sem precisar ler todos os documentos é “do que eles estão falando?” No fundo, você está interessado nos tópicos gerais dos documentos, ou seja, quais palavras são frequentemente utilizadas juntas. A modelagem de tópicos busca resolver esse problema utilizando técnicas estatísticas, onde cada tópico possui uma distribuição de probabilidades de features (palavras, n-grams, etc). A modelagem de tópicos é conhecida há muito tempo e ganhou imensa popularidade nas últimas duas décadas, principalmente, com a publicação do trabalho seminal do cientista da computação David Blei, em 2003, onde ele descreve o Latent dirichlet allocation (LDA). Nesse trabalho, vamos utilizar o LDA, um método estocástico para descobrir tópicos, que permite muitas modificações. 

## [Dataset](#dataset)
Utilizaremos notícias da seção "Mercado" extraídas da Folha de S. Paulo no ano de 2016. Para baixar os dados será necessário o uso do gerenciador de downloads da Kaggle. Para utilizar o gerenciador, é necessário criar uma conta no site Kaggle.com. Com a conta criada, basta obter um token de acesso, no formato kaggle.json.

``` python
# Instalando o gerenciador kaggle e fazendo o upload do arquivo kaggle.json
!pip install -q kaggle
!rm -rf kaggle.json
from google.colab import files

files.upload()

# Crie a pasta .kaggle 
!rm -rf .kaggle
!mkdir .kaggle
!cp kaggle.json .kaggle/
!chmod 600 .kaggle/kaggle.json

# Baixe o dataset
!mv .kaggle /root/
!kaggle datasets download --force -d marlesson/news-of-the-site-folhauol

#Criar o DataFrame com os dados lidos diretamente da plataforma Kaggle
import pandas as pd
from tqdm.auto import tqdm
tqdm.pandas()

df = pd.read_csv("news-of-the-site-folhauol.zip")
```

## [Verificando as Estatísticas do Corpus](#estatisticas-corpus)

```python
df.info()

```


## Referências
-BLEI, David M., Andrew Y. Ng, and Michael I. Jordan. "Latent dirichlet allocation." Journal of machine Learning research 3.Jan (2003): 993-1022.

-SARKAR, Dipanjan. Text Analytics with python. New York, NY, USA:: Apress, 2016.

-ALBRECHT, Jens; RAMACHANDRAN, Sidharth; WINKLER, Christian. Blueprints for Text Analytics Using Python. O'Reilly Media, 2020.

 
--- 
Visit my [LinkedIn](https://www.linkedin.com/in/wfaquieri/ "Stay in touch!")!
