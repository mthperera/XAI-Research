# Explicabilidade de Modelos Preditivos na Saúde: Uma Análise dos Gráficos de Explicação Local e Global do SHAP

Análise das respostas de um questionário aplicado a 22 médicos para avaliar explicações de IA explicável (SHAP) sobre um modelo de predição de óbito por COVID-19. Compara a explicação **global** (Figura 1) com a **local** (Figura 2).

## Como rodar

Requer Python 3.12 ou superior.

1. Crie e ative um ambiente virtual na raiz do projeto:

   ```bash
   # Windows (PowerShell)
   python -m venv env
   .\env\Scripts\Activate.ps1

   # macOS / Linux
   python3 -m venv env
   source env/bin/activate
   ```

2. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

3. Abra os notebooks da pasta `notebooks/` no VS Code (com a extensão *Jupyter*), selecione `env` como kernel e execute as células na ordem (`01` → `05`). O notebook `01` baixa o dataset da Kaggle automaticamente na primeira execução.

O diretório `env/` é ignorado pelo Git. Para rodar os notebooks pelo navegador em vez do VS Code, instale o Jupyter à parte (`pip install jupyterlab`) e rode `jupyter lab`.

## Estrutura

- `data/`
  - `raw/survey_responses.json` — respostas do questionário (22 médicos), já tratadas.
  - `raw/covid.csv` e `processed/covid.csv` — dataset COVID-19 bruto e limpo (gerados pelo notebook `01`).
- `notebooks/`
  - `01_data_cleaning.ipynb` — baixa o dataset COVID-19 da Kaggle (salva em `data/raw/`) e trata os dados: 17 variáveis do questionário, binárias em 0/1 e alvo ÓBITO (salva em `data/processed/`).
  - `02_model_training.ipynb` — treina o CatBoost com o treino balanceado por undersampling 1:1 e limiar de decisão ajustado na validação.
  - `03_pre_research.ipynb` — perfil sócio-demográfico dos respondentes e perguntas de conhecimento prévio em IA/XAI.
  - `04_research_v1.ipynb` — primeira análise das respostas das figuras SHAP: estatísticas descritivas, correlações e Alfa de Cronbach.
  - `05_research_v2.ipynb` — análise estendida: médias agregadas (global vs. local), correlações com o perfil do respondente e teste de Wilcoxon.
- `docs/`
  - `questionnaire.md` — o questionário: perguntas, escalas, codificação dos valores e figuras apresentadas.
  - `research_questions.md` — as questões de pesquisa (RQs).
  - `research_findings.md` — as respostas às questões de pesquisa.
  - `data_and_model.md` — pré-processamento, raciocínio do treinamento (divisão, hiperparâmetros, tratamento do desbalanceamento) e resultados do modelo.
  - `imgs/` — figuras SHAP.
- `requirements.txt` — dependências (numpy, pandas, matplotlib, scipy, catboost, scikit-learn, kagglehub).
