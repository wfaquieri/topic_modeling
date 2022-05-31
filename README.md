# Topic Modeling

![image](img.png)

Esse notebook servirá de guia para a execução de uma análise de tópicos completa, usando o algoritmo de LDA e recursos para interpretação dos resultados.

## Introdução

Uma tarefa importante para cientistas de dados é realizar o agrupamento de dados, sem conhecimento prévio. Ao trabalhar com um grande número de documentos, uma das primeiras perguntas que você responder fazer sem precisar ler todos eles é “do que eles estão falando?” Você está interessado nos tópicos gerais dos documentos, ou seja, quais palavras (idealmente semânticas) são frequentemente utilizadas juntas. A modelagem de tópicos busca resolver esse problema utilizando técnicas estatísticas. Cada tópico possui uma distribuição de probabilidades de features (palavras, n-grams, etc). A modelagem de tópicos é conhecida há muito tempo e ganhou imensa popularidade nas últimas duas décadas, principalmente, com a publicação do trabalho seminal do cientista da computação David Blei, em 2003, onde ele descreve o Latent dirichlet allocation (LDA). Nesse trabalho, vamos focar no LDA, um método estocástico para descobrir tópicos, que permite muitas modificações. 

## Dataset
Utilizaremos notícias da seção "Mercado" extraídas da Folha de S. Paulo no ano de 2016. Para baixar os dados será necessário o uso do gerenciador de downloads da Kaggle. Para utilizar o gerenciador, será necessário criar uma conta no site Kaggle.com. Com a conta criada, obtenha um token de acesso, no formato kaggle.json.

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
```



As seguintes tarefas serão realizadas:

1. Download dos dados provenientes do kaggle
2. Seleção dos dados relevantes para a nossa análise
3. Instalação das principais ferramentas e importação de módulos
4 Pré-processamento usando NLTK
4 Pré-processamento usando Spacy
5.Análise de tópicos usando LDA
6.Análise de NER usando Spacy
7.Visualização dos tópicos usando tokens e entidades.


## Referências
-BLEI, David M., Andrew Y. Ng, and Michael I. Jordan. "Latent dirichlet allocation." Journal of machine Learning research 3.Jan (2003): 993-1022.

-SARKAR, Dipanjan. Text Analytics with python. New York, NY, USA:: Apress, 2016.

-ALBRECHT, Jens; RAMACHANDRAN, Sidharth; WINKLER, Christian. Blueprints for Text Analytics Using Python. O'Reilly Media, 2020.

 
--- 
Visit my [LinkedIn](https://www.linkedin.com/in/wfaquieri/ "Stay in touch!")!
