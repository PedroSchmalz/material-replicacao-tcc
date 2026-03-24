# Classificação de Relevância e Análise de Sentimento de Publicações no X de Congressistas Brasileiros sobre Armas de Fogo

## Citação

Se este repositório for utilizado em trabalhos acadêmicos, solicita-se a citação do seguinte trabalho:

Schmalz, Pedro (2026). Armas, Violência e Política: Classificação de Relevância e Análise de Sentimento de Publicações de Congressistas Brasileiros no X. Trabalho de Conclusão de Curso em Data Science & Analytics, USP-Esalq.

## Descrição

Este repositório contém o material de replicação do Trabalho de Conclusão de Curso intitulado *"Armas, Violência e Política: Classificação de Relevância e Análise de Sentimento de Publicações de Congressistas Brasileiros no X"*.

O material complementa a dissertação apresentada como requisito parcial para obtenção do **MBA em Data Science & Analytics** pela USP-Esalq em 2026.

### Escopo da Pesquisa

Este estudo investiga o discurso de congressistas brasileiros na plataforma X (antigo Twitter) entre 2019 e 2023, utilizando duas tarefas principais de **Processamento de Linguagem Natural (PLN)**:

- **Classificação de Relevância**: Identificação automatizada de publicações relacionadas a armas de fogo e violência
- **Análise de Sentimento**: Classificação em três categorias (positivo, negativo, incerto/neutro)

Os modelos foram desenvolvidos usando arquiteturas de aprendizado profundo baseadas em **BERTimbau**, um modelo BERT otimizado para o português.



## Objetivo do Repositório

Disponibilizar os códigos, modelos treinados e documentação necessária para **reproduzir as etapas metodológicas** descritas no trabalho e aplicar os modelos em novos dados.

⚠️ **Nota sobre os dados**: O conjunto de dados original não é disponibilizado devido a restrições dos termos de uso da plataforma X e à preservação do corpus para futuras investigações.


## Metodologia (Resumo)

1. Coleta de publicações de congressistas brasileiros no X (2019–2023)
2. Filtragem por palavras-chave relacionadas a armas de fogo
3. Anotação manual de amostra de 3.000 publicações (classificação de relevância)
4. Treinamento de modelos baseados em BERTimbau com validação cruzada
5. Transfer learning para análise de sentimento utilizando dataset CoVid-Pol
6. Avaliação quantitativa (F1-macro, acurácia, matriz de confusão)
7. Aplicação dos modelos ao conjunto completo de dados

## Resultados Principais

### Classificação de Relevância
- **F1-macro**: ~0,91
- **Acurácia**: ~89%

### Análise de Sentimento
- **F1-macro**: ~0,67
- **Acurácia**: ~87%

**Interpretação**: O desempenho excelente na classificação de relevância indica que o modelo identifica com confiabilidade publicações sobre armas. O resultado menor na análise de sentimento reflete a dificuldade geral em detectar nuances de sentimento em textos políticos, especialmente em classes minoritárias.

------------------------------------------------------------------------

## Estrutura do Repositório

```bash
├── data/
│   ├── raw/              # Dados originais (não disponibilizados)
│   ├── processed/        # Dados processados
│   └── annotations/      # Dados anotados manualmente
├── notebooks/            # Jupyter notebooks com análises e treinamento
│   ├── 01_exploratory_data_analysis.ipynb
│   ├── 02_data_preprocessing.ipynb
│   ├── 03_model_training_relevance.ipynb
│   └── 04_model_training_sentiment.ipynb
├── models/               # Modelos treinados (em formato .pt ou .pkl)
│   ├── relevance_model/
│   └── sentiment_model/
├── src/                  # Código-fonte modular
│   ├── data_loader.py
│   ├── preprocessing.py
│   ├── model.py
│   └── evaluation.py
├── requirements.txt      # Dependências do projeto
├── LICENSE               # Licença MIT
└── README.md             # Este arquivo
```

---

## Como Usar

### Instalação

Recomenda-se Python 3.10 ou superior.

```bash
# Clone o repositório
git clone <url-do-repositorio>
cd material-replicacao-tcc

# Crie um ambiente virtual (optional but recommended)
python -m venv venv
source venv/bin/activate  # No Windows: venv\Scripts\activate

# Instale as dependências
pip install -r requirements.txt
```

### Executar os Notebooks

```bash
jupyter notebook notebooks/
```

Os notebooks devem ser executados em ordem (01 → 02 → 03 → 04).

### Usar os Modelos Treinados

```python
from transformers import AutoTokenizer, AutoModelForSequenceClassification

# Carregar modelo de relevância
tokenizer = AutoTokenizer.from_pretrained("./models/relevance_model")
model = AutoModelForSequenceClassification.from_pretrained("./models/relevance_model")

# Fazer predições
text = "Sua publicação aqui"
inputs = tokenizer(text, return_tensors="pt")
outputs = model(**inputs)
```

## Requisitos e Dependências

Principais bibliotecas:

```txt
transformers>=4.30.0
torch>=2.0.0
scikit-learn>=1.3.0
pandas>=2.0.0
numpy>=1.24.0
jupyter>=1.0.0
matplotlib>=3.7.0
seaborn>=0.12.0
```

Instale com: `pip install -r requirements.txt`

---


## Reprodutibilidade

Este repositório fornece os elementos necessários para replicação do pipeline metodológico, incluindo etapas de processamento, treinamento, avaliação e aplicação dos modelos. A ausência do dataset original não impede a reprodução das etapas descritas.

## Licença

Este projeto é disponibilizado sob a licença **MIT**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## Contato

Para dúvidas sobre o material de replicação, entre em contato com:

**Pedro Schmalz**  
Email: pedrosantanaschmalz@usp.br ou @gmail.com

[Linkedin](https://www.linkedin.com/in/pedro-schmalz/)

---

## Referências Principais

- Devlin, J., et al. (2019). *BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding*. ICLR.
- Souza, F., Nogueira, R., Lotufo, R. (2020). *BERTimbau: Pretrained BERT Models for Brazilian Portuguese*. LREC.
- Documentation: [Hugging Face Transformers](https://huggingface.co/docs/transformers/)

---

**Últimas atualizações**: Março de 2026
