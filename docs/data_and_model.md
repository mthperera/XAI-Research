# Dados e modelo

Pipeline implementado em dois notebooks: [`01_data_cleaning.ipynb`](../notebooks/01_data_cleaning.ipynb) (limpeza) e [`02_model_training.ipynb`](../notebooks/02_model_training.ipynb) (treinamento).

## Dados

[COVID-19 Dataset (Kaggle)](https://www.kaggle.com/datasets/meirnizri/covid19-dataset), disponibilizado pelo Governo do México — 1.048.575 pacientes.

## Pré-processamento

- **Alvo (ÓBITO):** derivado de `DATE_DIED`, em que `9999-99-99` indica sobrevivente. Resultado: 7,34% de óbitos (conjunto fortemente desbalanceado).
- **Variáveis:** as 17 da tabela de [questionnaire.md](questionnaire.md), as mesmas apresentadas nas explicações das Figuras 1 e 2.
- **Binárias:** recodificadas para 0 = Não / 1 = Sim; os códigos de ausência (97/98/99) viram 0 (ex.: INTUBADO só é registrado para hospitalizados). IDADE ausente recebe a mediana.

## Treinamento

Um único `CatBoostClassifier`, treinado assim:

- **Divisão estratificada 64/16/20** (treino/validação/teste). A validação escolhe o limiar de decisão; o teste é usado uma única vez, na avaliação final.
- **Desbalanceamento:** o treino é balanceado por *undersampling* aleatório 1:1 da classe majoritária (98.486 registros); validação e teste mantêm a distribuição real.
- **Hiperparâmetros:** 200 iterações, `learning_rate=0.03`, `depth=5`, Logloss.
- **Limiar de decisão:** escolhido na validação maximizando o F1 da classe óbito (limiar = 0,846).

## Resultados no teste

| Métrica | Valor |
|---|---|
| AUC-ROC | 0,947 |
| PR-AUC | 0,670 (prevalência: 0,073) |
| F1 (óbito) | 0,62 |
| Sensibilidade (óbito) | 0,65 |
| Precisão (óbito) | 0,59 |
| Acurácia | 0,94 |

- **Ponto de operação:** o limiar F1 equilibra sensibilidade e precisão. Se a prioridade for capturar mais óbitos, o limiar que maximiza o F2 na validação leva a sensibilidade de 0,83 (precisão 0,42; F1 0,56) com o mesmo modelo.