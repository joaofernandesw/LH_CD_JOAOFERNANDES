# Análise de Dados Cinematográficos para PProductions - Desafio Indicium

## 📝 Visão Geral do Projeto

Este projeto foi desenvolvido como parte do desafio de **Cientista de Dados** para o programa *Lighthouse da Indicium*. O objetivo é realizar uma análise detalhada sobre um banco de dados cinematográfico para orientar o estúdio de Hollywood **"PProductions"** sobre qual tipo de filme deve ser o próximo a ser desenvolvido. A análise abrange desde a limpeza e tratamento dos dados até a construção de um modelo preditivo para a nota do IMDB.

## 📂 Estrutura do Repositório

O projeto está organizado da seguinte forma:

-   **/data**: Contém os datasets utilizados.
    -   `desafio_indicium_imdb.csv`: O dataset original fornecido.
    -   `dataset-adjusted (1).csv`: O dataset limpo e pré-processado, pronto para a modelagem.
      
-   **/models**: Armazena o modelo de machine learning treinado e salvo.
    -   `imdb_rating_predictor.pkl`: Modelo de regressão para prever a nota do IMDB.
      
-   **/notebooks**: Contém o Jupyter Notebook com toda a análise.
    -   `analise_filmes_indicium.ipynb`: Notebook com o passo a passo da análise exploratória (EDA), respostas às perguntas de negócio e desenvolvimento do modelo.
-   `README.md`: Este documento, com a descrição completa do projeto.
-   `requirements.txt`: Lista de dependências Python para garantir a reprodutibilidade do ambiente.

## 🛠️ Como Instalar e Executar o Projeto

Para executar este projeto localmente, siga os passos abaixo:

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/joaofernandesw/LH_CD_JOAOFERNANDES.git](https://github.com/joaofernandes/LH_CD_JOAOFERNANDES.git)
    cd LH_CD_JOAOFERNANDES
    ```

2.  **Instale as dependências:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Execute o Jupyter Notebook:**
    Abra o *Jupyter Notebook* (ou *Jupyter Lab*) e navegue até a pasta `notebooks/` para abrir o arquivo `EDA-desafiocd.ipynb`.

## Analise exploratoria dos dados (EDA)

## 🤖 Modelagem Preditiva: Previsão da Nota IMDB

Foi desenvolvido um modelo de regressão para prever a nota do IMDB de um filme com base em suas características.

-   **Features Utilizadas**: `Meta_score`, `No_of_Votes`, `Gross_Adjusted`, `Runtime`, e features categóricas como `Genre` e `Director` (tratadas com *One-Hot Encoding*).
-   **Modelo Escolhido**: *[Nome do Modelo]*, escolhido após comparação com *[Outros Modelos]* por apresentar o menor RMSE.
-   **Métrica de Performance**: O *Root Mean Squared Error (RMSE)* foi a métrica principal, pois penaliza erros maiores de forma mais significativa, o que é crucial para previsões de notas. O modelo final alcançou um **RMSE de [seu valor]**.

### Exemplo de Previsão

Para o filme *"The Shawshank Redemption"*, com as características fornecidas no desafio, a nota do IMDB prevista pelo modelo foi:

-   **Nota Prevista**: `[Valor da Nota]`

## 💻 Tecnologias Utilizadas

-   **Python 3.x**
-   **Pandas & NumPy** para manipulação de dados
-   **Matplotlib & Seaborn** para visualização
-   **Scikit-learn** para modelagem de machine learning
-   **NLTK** para processamento de linguagem natural
-   **Jupyter Notebook** como ambiente de desenvolvimento
