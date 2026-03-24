# Classificação de Relevância e Análise de Sentimento de Publicações no X de Congressistas Brasileiros sobre Armas de Fogo

## Descrição

Este repositório contém o material de replicação do Trabalho de
Conclusão de Curso intitulado *"Classificação de Relevância e Análise de
Sentimento de Publicações no X de Congressistas Brasileiros sobre Armas
de Fogo"*.

Material de replicação do TCC apresentado na USP-Esalq como parte dos
requisitos para obtenção do MBA em Data Science & Analytics.

O estudo investiga o discurso de congressistas brasileiros na plataforma
X (Twitter) entre 2019 e 2023, com base em duas tarefas principais de
Processamento de Linguagem Natural (PLN):

-   Classificação de relevância: identificação de publicações
    relacionadas ao tema armas/violência\
-   Análise de sentimento: classificação das publicações em três
    categorias (positivo, negativo e incerto)

Os modelos foram desenvolvidos a partir de arquiteturas de aprendizado
profundo baseadas no BERTimbau.

------------------------------------------------------------------------

## Objetivo do Repositório

Disponibilizar os códigos, modelos e instruções necessárias para
permitir a reprodutibilidade das etapas metodológicas descritas no
trabalho.

O conjunto de dados original não é disponibilizado, em função de
restrições relacionadas aos termos de uso da plataforma e à preservação
do corpus para investigações futuras.

------------------------------------------------------------------------

## Metodologia (Resumo)

-   Coleta de publicações de congressistas brasileiros no X
    (2019--2023)\
-   Filtragem por palavras-chave relacionadas a armas de fogo\
-   Anotação manual de uma amostra de 3.000 publicações para
    classificação de relevância\
-   Treinamento de modelos baseados em BERTimbau\
-   Transfer learning para análise de sentimento a partir do dataset
    CoVid-Pol\
-   Avaliação com métricas como F1-macro e acurácia\
-   Aplicação dos modelos ao conjunto completo de dados

------------------------------------------------------------------------

## Resultados Principais

-   Classificação de relevância:
    -   F1-macro: aproximadamente 0,91\
    -   Acurácia: aproximadamente 89%
-   Análise de sentimento:
    -   F1-macro: aproximadamente 0,67\
    -   Acurácia: aproximadamente 87%

Os resultados indicam bom desempenho na identificação de conteúdo
relevante e maior dificuldade na tarefa de análise de sentimento,
especialmente em classes minoritárias.

------------------------------------------------------------------------

## Estrutura do Repositório

``` bash
├── data/
│   └── (dados não disponibilizados)
├── notebooks/
├── models/
├── src/
├── requirements.txt
└── README.md
```

------------------------------------------------------------------------

## Requisitos

Recomenda-se o uso de Python 3.10 ou superior.

Instalação das dependências:

``` bash
pip install -r requirements.txt
```

Principais bibliotecas utilizadas:

-   transformers\
-   torch\
-   scikit-learn\
-   pandas\
-   numpy

------------------------------------------------------------------------

## Reprodução das Análises

### 1. Preparação dos dados

Como o dataset original não é disponibilizado, recomenda-se a coleta de
dados por meio da API da plataforma X ou fontes equivalentes, seguida da
aplicação de filtros por palavras-chave relacionadas ao tema.

### 2. Pré-processamento

``` bash
python src/preprocessing.py
```

### 3. Treinamento dos modelos

Classificação de relevância:

``` bash
python src/train.py --task relevancia
```

Análise de sentimento:

``` bash
python src/train.py --task sentimento
```

### 4. Avaliação

``` bash
python src/evaluate.py
```

### 5. Aplicação dos modelos

``` bash
python src/predict.py
```

------------------------------------------------------------------------

## Reprodutibilidade

Este repositório fornece os elementos necessários para replicação do
pipeline metodológico, incluindo etapas de processamento, treinamento,
avaliação e aplicação dos modelos. A ausência do dataset original não
impede a reprodução das etapas descritas.

------------------------------------------------------------------------

## Referências

-   Souza, F.; Nogueira, R.; Lotufo, R. (2020). BERTimbau\
-   Barberia et al. (2025a; 2025b). CoVid-Pol\
-   Liu, B. (2010). Sentiment Analysis\
-   Mohammad et al. (2017)

------------------------------------------------------------------------

## Autor

Pedro Henrique Schmalz

------------------------------------------------------------------------

## Contato

Dúvidas e sugestões podem ser encaminhadas via GitHub.
