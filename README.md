# fake-news-classification-kaggle

Repositório público com a implementação completa da solução para classificação de fake news, desenvolvida em **Google Colab** e organizada em notebooks, atendendo aos requisitos de:
- organização do código (EDA → preparação → treino → inferência),
- reprodutibilidade (dependências versionadas),
- documentação (passo a passo para rodar e gerar submissão Kaggle),
- artefatos do modelo (modelos serializados).

---

## Estrutura do repositório

- `notebooks/`: pipeline completo do projeto, do EDA ao modelo robusto
- `artifacts/`: modelos finais serializados (`.joblib`) 
- `submissions/`: arquivos `.csv` prontos para submissão no Kaggle

---

## Requisitos e instalação

### Opção A — Google Colab (recomendado)
1. Abra o notebook desejado em `notebooks/`.
2. Faça upload dos arquivos `train.csv` e `test.csv` (Kaggle) para o ambiente do Colab.
3. Execute as células em ordem.

### Opção B — Local (Python 3.10+)

Instale as dependências com: `pip install -r requirements.txt`

> Observação: os dados não estão incluídos neste repositório e devem ser obtidos na plataforma Kaggle.

---

## Geração de Submissão Kaggle

Os notebooks abaixo refazem o treino no conjunto completo e geram o CSV final em submissions/:

- `02_baseline_tfidf_logistic_regression.ipynb`
Saída: submissions/submission_baseline.csv

- `06_cpu_svm_word_char.ipynb`
Saída: submissions/submission_cpu_svm_word_char.csv

- `07_experiments_cpu_svm_word_char_grid.ipynb`
Saída: submissions/submission_cpu_svm_word_char_ensemble.csv (ensemble simples por média de scores)

---

## Artefatos do modelo

Modelos serializados (gerados pelos notebooks e/ou disponibilizados em artifacts/):

- `artifacts/baseline_tfidf_logreg.joblib`
- `artifacts/svm_word_char.joblib`

> Observação: Um modelo em ensemble foi testado durante os experimentos, porém apresentou o mesmo desempenho (F1) do melhor modelo individual. Por esse motivo, optou-se por manter apenas o modelo único (TF-IDF word + char + Linear SVM) como artefato final, priorizando simplicidade, reprodutibilidade e interpretabilidade.

# Autora

**Ana Beatriz Regis de Souza**  
