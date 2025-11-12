# django-ml-app

[![Python](https://img.shields.io/badge/python-3.11%2B-blue)](https://www.python.org/)

Aplicação Django simples que demonstra a integração de um modelo de Machine Learning (Random Forest) para predição (ex.: Iris dataset). Ideal para exemplos, testes e demonstrações locais.

## ✅ Principais pontos

- Projeto Django com um app `predictor` que carrega um modelo salvo (`predictor/model/iris_rf.joblib`) e expõe um formulário web para realizar predições.
- Script de treinamento: `train.py` (re-treina e salva o modelo).
- Configuração para Windows/PowerShell descrita abaixo.

## Estrutura do repositório

- `manage.py` - comando do Django
- `train.py` - script para treinar/re-treinar o modelo
- `mlapp/` - configuração do projeto Django
- `predictor/` - app com views, forms, serviços e modelo salvo
  - `predictor/model/iris_rf.joblib` - modelo salvo (exemplo)
- `templates/predictor/predict_form.html` - template do formulário
- `db.sqlite3` - banco de dados (local)

## Requisitos

- Python 3.11+ (ou versão compatível com as dependências usadas)
- Recomenda-se criar um ambiente virtual (`venv`).
- Dependências principais: Django, scikit-learn, joblib, numpy, scipy

Sugestão de `requirements.txt` (exemplo):

```
Django>=4.2
scikit-learn>=1.2
joblib>=1.2
numpy>=1.24
scipy>=1.10
```

Posso criar esse arquivo `requirements.txt` automaticamente se quiser — me avise.

## Instruções rápidas (Windows PowerShell)

1) Abra o PowerShell e vá para a pasta do projeto:

```powershell
cd C:\Users\leona\Desktop\django-ml-app
```

2) Criar/ativar um ambiente virtual (recomendado):

```powershell
python -m venv .venv
. .\.venv\Scripts\Activate.ps1
```

3) Instalar dependências:

```powershell
pip install -r requirements.txt
```

# django-ml-app — apresentação para portfólio

Uma aplicação Django demonstrando a integração de um modelo de Machine Learning (Random Forest) para tarefas de classificação (ex.: Iris dataset). Este README foi pensado para apresentação em portfólio: destaca objetivo, resultados, arquitetura e pontos técnicos, sem instruções passo a passo.

Visão curta

- Objetivo: provar a capacidade de integrar um modelo de ML treinado em uma aplicação web Django e expor uma interface simples de predição.
- Foco para portfólio: clareza do problema, abordagem, arquitetura e resultados observados.

Destaques

- Modelo: Random Forest treinado e salvo em `predictor/model/iris_rf.joblib` (exemplo).
- Estrutura: app Django (`predictor`) que encapsula a carga do modelo, lógica de predição e templates para interação.
- Código principal: `train.py` (treinamento), `predictor/services.py` (carregamento do modelo e lógica de predição) e `predictor/views.py` (integração com templates).

Resumo técnico

- Dataset: Iris (classificação de espécies) — usado como exemplo didático.
- Algoritmo: Random Forest (escolha por simplicidade, performance e interpretabilidade básica).
- Artefatos gerados: modelo serializado (`.joblib`) e endpoints web para inferência.

Resultados (exemplo)

- Acurácia obtida no conjunto de validação: ~98% (valor ilustrativo — confira `train.py` para métricas exatas do treinamento que foi realizado neste repositório).
- Observações: métricas detalhadas (precision/recall/f1, matriz de confusão) podem ser encontradas/geradas pelo script de treino.

Arquitetura (visão de alto nível)

- Web (Django)
  - Views / Forms: interface do usuário para enviar features
  - Services: carregamento do modelo e wrapper de inferência
  - Templates: UI simples para demonstração
- ML
  - Script de treino (`train.py`) que prepara dados, treina o modelo e salva o artefato

Arquivos de interesse (para apresentação)

- `train.py` — código do treinamento e geração de métricas
- `predictor/services.py` — funções que carregam o modelo e realizam predições
- `predictor/views.py` e `templates/predictor/predict_form.html` — fluxo de entrada/saída para o usuário
- `predictor/model/iris_rf.joblib` — exemplo do modelo salvo
