# Análise de Dados Cinematográficos para PProductions - Desafio Indicium

## 📝 Visão Geral do Projeto

Este projeto foi desenvolvido como parte do desafio de **Cientista de Dados** para o programa *Lighthouse da Indicium*. O objetivo é realizar uma análise detalhada sobre um dataset cinematográfico para orientar o estúdio de Hollywood **"PProductions"** sobre qual tipo de filme deve ser o próximo a ser desenvolvido. A análise abrange desde a limpeza e tratamento dos dados até a construção de um modelo preditivo para a nota do IMDB.

## 📂 Estrutura do Repositório

O projeto está organizado da seguinte forma:

-   **/data**: Contém os datasets utilizados.
    -   `desafio_indicium_imdb.csv`: O dataset original fornecido.
    -   `dataset-final.csv`: O dataset limpo e pré-processado, pronto para a modelagem.
      
-   **/models**: Armazena o modelo de machine learning treinado e salvo.
    -   `random_forest_imdb.pkl`: Modelo de regressão para prever a nota do IMDB.
      
-   **/notebooks**: Contém o Jupyter Notebook com toda a análise.
    -   `notebook-desafioCD.ipynb`: Notebook com o passo a passo da análise exploratória (EDA), respostas às perguntas de negócio e desenvolvimento do modelo.
      
-   `README.md`: Este documento, com a descrição completa do projeto.
-   `requirements.txt`: Lista de dependências Python para garantir a reprodutibilidade do ambiente.

## 🛠️ Como Instalar e Executar o Projeto

Para executar este projeto localmente, siga os passos abaixo:

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/joaofernandesw/LH_CD_JOAOFERNANDES](https://github.com/joaofernandesw/LH_CD_JOAOFERNANDES)
    cd LH_CD_JOAOFERNANDES
    ```

2.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Execute o Jupyter Notebook:**
    Abra o *Jupyter Notebook* (ou semelhantes) para abrir o arquivo `EDA-desafiocd.ipynb`.

## Analise exploratoria dos dados (EDA)

Uma análise foi feita para identificar as características que definem um filme de sucesso, com base em avaliações de público e crítica, desempenho comercial e elenco envolvido.

- **Métricas de Sucesso (Notas e Faturamento)**:
    - **IMDB Rating**: As notas do público são consistentemente altas (média de 7.94), indicando um viés de seleção no dataset (apenas os melhores filmes). Filmes com notas acima de 8.5 são excepcionais.
    - **Meta Score**: A crítica especializada tende a ser mais rigorosa que o público, com uma distribuição de notas mais ampla, mas mesmo assim indica o viés de sobrevivencia. 
    - **Faturamento (Gross)**: Na análise é possível encontrar outliers, onde blockbusters com arrecadação astronômica elevam a média. O ajuste pela inflação revelou que clássicos antigos tiveram um sucesso comercial ainda mais expressivo do que os números brutos sugerem. 

- **Características dos Filmes**:
    - **Gênero**: O **Drama** é o gênero dominante, presente em mais de 72% dos filmes da lista, frequentemente combinado com **Crime**, **Aventura** e **Comédia**. Gêneros de nicho como *Film-Noir* e *Western* possuem notas altíssimas, indicando um viés de sobrevivência de clássicos icônicos.
    - **Duração (Runtime)**: Existe um "ponto ideal" de duração em torno de **123 minutos (2h03m)**. Filmes muito longos são um risco, mas podem gerar grande aclamação quando a história justifica a extensão.
    - **Década de Lançamento**: Observa-se um **viés de recência**, com um aumento significativo de filmes a partir da década de 1990, impulsionado pelo maior volume de produção e acesso à avaliação online.

- **Talentos Envolvidos (Diretores e Elenco)**:
    - **Diretores**: O sucesso está fortemente associado a uma elite de diretores, como **Alfred Hitchcock**, **Steven Spielberg** e **Martin Scorsese**, que aparecem repetidamente na lista. A análise de duplas revelou parcerias icônicas, como **Scorsese & De Niro**, como um forte indicador de sucesso.
    - **Elenco**: Utilizando um "Star Score" ponderado, foi identificado que protagonistas de peso como **Robert De Niro** e **Tom Hanks** são cruciais. Além disso, um elenco de apoio forte, com atores que consistentemente elevam a qualidade das produções, é um fator determinante.

## 🤖 Modelagem Preditiva: Previsão da Nota IMDB

Foi desenvolvido um modelo de regressão para prever a nota do IMDB de um filme com base em suas características.

-   **Features Utilizadas**: Meta_score, No_of_Votes, Gross_Adjusted, Runtime, e features categóricas como Genre e Overview (tratadas com *One-Hot Encoding* e *Bigramas*).
-   **Modelo Escolhido**: *[Random Forest]*
-   **Métrica de Performance**: O *Root Mean Squared Error (RMSE)* foi a métrica principal, pois penaliza erros maiores de forma mais significativa, o que é crucial para previsões de notas. O modelo final alcançou um **RMSE de [0.19]**.

### Exemplo de Previsão

Para o filme *"The Shawshank Redemption"*, com as características fornecidas no desafio, a nota do IMDB prevista pelo modelo foi:

-   **Nota Prevista**: [8.74]

## 💻 Tecnologias Utilizadas

-   **Python3**
-   **Pandas & NumPy** para manipulação de dados
-   **Matplotlib & Seaborn** para visualização
-   **Scikit-learn** para modelagem de machine learning
-   **NLTK** para processamento de linguagem natural
-   **Google Colab** como ambiente de desenvolvimento
