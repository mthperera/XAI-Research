# Respostas às Questões de Pesquisa

> Análise baseada nos notebooks `03_pre_research.ipynb`, `04_research_v1.ipynb` e `05_research_v2.ipynb`.  
> Total de respondentes: **22 médicos**.

---

## 1. Quais são as principais características sócio-demográficas dos respondentes da pesquisa?

### Gênero e Categoria
| Atributo | Distribuição |
|---|---|
| Feminino | 54,5% (12 respondentes) |
| Masculino | 45,5% (10 respondentes) |
| Especialista | 95,5% (21 respondentes) |
| Residente | 4,5% (1 respondente) |

### Local de Trabalho
Proporção calculada sobre o total de menções (39), já que cada médico pode indicar mais de um local.

| Local | Proporção |
|---|---|
| Consultório particular (*private\_clinic*) | ~36% |
| Hospital público (*public\_hospital*) | ~23% |
| Hospital privado (*private\_hospital*) | ~21% |
| Hospital escola (*teaching\_hospital*) | ~21% |

### Especialidades Médicas (mais frequentes)
Proporção calculada sobre o total de menções (23), já que um médico pode ter mais de uma especialidade.

| Especialidade | Proporção |
|---|---|
| Psiquiatria | ~26% (6 menções) |
| Dermatologia | ~9% |
| Ginecologia e Obstetrícia | ~9% |
| Radiologia e Diagnóstico por Imagem | ~9% |
| Demais especialidades (Pediatria, Infectologia, Geriatria, etc.) | ~4% cada (1 menção) |

### Idade e Tempo de Experiência Profissional
| Estatística | Idade (anos) | Experiência (anos) |
|---|---|---|
| n | 22 | 22 |
| Média | 46,2 | 18,7 |
| Mediana | 45,5 | 17,5 |
| Desvio-padrão | 12,6 | 13,2 |
| Mínimo | 25 | 1 |
| Máximo | 73 | 45 |

A distribuição etária apresenta dois grupos predominantes: médicos mais jovens (25–40 anos) e médicos com mais de 50 anos. O perfil de experiência reflete essa bimodalidade, com concentração de respondentes tanto com poucos anos de prática (1–10 anos) quanto com mais de 10 anos.

---

## 2. Os respondentes têm experiência prévia com inteligência artificial ou algoritmos de apoio à decisão clínica?

A escala utilizada foi de 1 (*Nunca*) a 5 (*Muito frequentemente*) para o uso de IA, e de 1 (*Nenhum conhecimento*) a 5 (*Conhecimento muito avançado*) para o nível de conhecimento em XAI.

| Dimensão | Pergunta | Média | Mediana | Moda | DP |
|---|---|---|---|---|---|
| **pre-usage** | Frequência de uso de IA/algoritmos de apoio clínico | 2,50 | 2,0 | 2 (*Raramente*) | 1,01 |
| **pre-knowledge** | Nível de conhecimento sobre XAI | 2,00 | 2,0 | 2 (*Conhecimento muito básico*) | 0,53 |

**Conclusão:** A maioria dos respondentes faz uso *raro* de sistemas de IA e possui conhecimento *muito básico* sobre explicabilidade (XAI). O `pre-knowledge` apresentou distribuição bastante concentrada no valor 2 (16 de 22 respondentes), com máximo observado de 3 (conhecimento intermediário) — nenhum respondente relatou conhecimento avançado ou muito avançado.

---

## 3. Os respondentes têm conhecimento e experiência prévia com ferramentas de XAI?

A escala utilizada foi de 1 (*Nenhuma experiência*) a 5 (*Experiência extensa*).

| Dimensão | Pergunta | Média | Mediana | Moda | DP |
|---|---|---|---|---|---|
| **pre-tools** | Experiência com ferramentas de IA explicável | 1,86 | 2,0 | 2 (*Experiência muito limitada*) | 0,77 |

Aproximadamente 36% dos respondentes (8 de 22) informaram *nenhuma experiência* (valor 1) com ferramentas de XAI. Nenhum respondente relatou experiência significativa ou extensa (valores 4 ou 5); o máximo observado foi 3 (experiência moderada), por 5 respondentes.

**Conclusão:** O nível de experiência com ferramentas de XAI é muito baixo, com a maioria dos respondentes entre "nenhuma" e "muito limitada" experiência. Este é um grupo de usuários sem conhecimento técnico em XAI, o que torna ainda mais relevante avaliar a acessibilidade das explicações SHAP.

---

## 4. Qual é a opinião dos respondentes sobre os gráficos de explicação do SHAP avaliados na pesquisa?

O questionário utilizou escala Likert de 1 (*Discordo totalmente*) a 5 (*Concordo totalmente*). Foram avaliadas duas figuras: **Figura 1 (explicação global — SHAP Global)** e **Figura 2 (explicação local — SHAP Local)**.

A confiabilidade interna dos instrumentos foi avaliada pelo **Alfa de Cronbach**:
- SHAP Global (Fig. 1): α = **0,951** → confiabilidade *excelente*
- SHAP Local (Fig. 2): α = **0,919** → confiabilidade *excelente*

---

### 4.1 A complexidade da explicação é adequada ao usuário? (*user-aware*)
| | Fig. 1 (Global) | Fig. 2 (Local) |
|---|---|---|
| Média | 3,64 | 3,95 |
| Mediana | 4 (Concordo) | 4 (Concordo) |
| Moda | 4 | 4 |

A maioria dos respondentes concorda que a linguagem e complexidade das explicações são adequadas à prática profissional, com avaliação levemente superior para a explicação local.

---

### 4.2 As explicações apresentam informações relevantes para a tomada de decisão clínica? (*context-aware*)
| | Fig. 1 (Global) | Fig. 2 (Local) |
|---|---|---|
| Média | 3,59 | 3,91 |
| Mediana | 4 (Concordo) | 4 (Concordo) |
| Moda | 4 | 4 |

Ambas as explicações são percebidas como contextualmente relevantes, com a explicação local recebendo avaliação mais positiva.

---

### 4.3 A explicação é objetiva? (*objectivity*)
| | Fig. 1 (Global) | Fig. 2 (Local) |
|---|---|---|
| Média | 3,45 | 3,77 |
| Mediana | 4 (Concordo) | 4 (Concordo) |
| Moda | 4 | 4 |

A objetividade foi percebida como positiva em ambas as figuras, ainda que com mais dispersão nas respostas para a Fig. 1.

---

### 4.4 A explicação é clara e fácil de entender? (*understandability*)
| | Fig. 1 (Global) | Fig. 2 (Local) |
|---|---|---|
| Média | 3,36 | 3,55 |
| Mediana | 3 (Neutro) | 4 (Concordo) |
| Moda | 3 | 4 |

Esta é a dimensão com avaliação mais baixa para a Fig. 1. A explicação global teve mediana e moda de 3 (neutro), indicando divisão de opiniões sobre sua clareza.

---

### 4.5 A explicação apresenta informações suficientes para compreender como o sistema chegou à decisão? (*informative*)
| | Fig. 1 (Global) | Fig. 2 (Local) |
|---|---|---|
| Média | 3,32 | 3,55 |
| Mediana | 4 (Concordo) | 4 (Concordo) |
| Moda | 4 | 4 |

Apesar da média relativamente mais baixa para a Fig. 1, a mediana de 4 (Concordo) indica que mais da metade dos respondentes concorda que a explicação é suficientemente informativa.

---

### Resumo geral das avaliações (escala 1–5)
| Dimensão | Fig. 1 (Global) Média | Fig. 2 (Local) Média |
|---|---|---|
| Orientado ao usuário (*user-aware*) | 3,64 | 3,95 |
| Orientado ao contexto (*context-aware*) | 3,59 | 3,91 |
| Objetividade (*objectivity*) | 3,45 | 3,77 |
| Compreensível (*understandability*) | 3,36 | 3,55 |
| Informativo (*informative*) | 3,32 | 3,55 |
| **Soma total (máx. 25)** | **17,36** | **18,73** |

---

## 5. Existe correlação entre as características sócio-demográficas dos respondentes e a opinião sobre os gráficos SHAP?

Sim, mas o padrão depende da figura avaliada. As correlações entre as variáveis demográficas (idade e anos de atuação) e as **médias** das avaliações foram calculadas pelo coeficiente de **Pearson**; as correlações no nível dos itens individuais e com o conhecimento prévio em XAI foram calculadas por **Spearman** (variáveis ordinais). A análise revela:

- **Idade e anos de atuação** têm correlação negativa moderada e estatisticamente significativa com a avaliação da **explicação global (Fig. 1)**:
  - anos de atuação vs. média Fig. 1: **r = −0,55** (p = 0,008)
  - idade vs. média Fig. 1: **r = −0,56** (p = 0,007)
  - no nível das dimensões individuais (Spearman) a associação é ainda mais forte, chegando a **ρ = −0,67** (anos de atuação vs. *user-aware* Fig. 1, p = 0,001) e **ρ = −0,53** (anos de atuação vs. *understandability* Fig. 1, p = 0,011).

- Para a **explicação local (Fig. 2)**, essas correlações são fracas e não significativas:
  - anos de atuação vs. média Fig. 2: r = −0,24 (p = 0,276)
  - idade vs. média Fig. 2: r = −0,29 (p = 0,190)

- **Conhecimento prévio em XAI** (`pre-usage`, `pre-knowledge`, `pre-tools`, `preResearchSum`) apresenta apenas correlações negativas fracas, nenhuma atingindo magnitude moderada. As mais notáveis:
  - `preResearchSum` vs. *understandability* Fig. 2: **−0,38**
  - `pre-usage` vs. *objectivity* Fig. 2: **−0,29**
  - `preResearchSum` vs. *objectivity* Fig. 2: **−0,26**

**Interpretação:** Médicos mais velhos e com mais anos de prática clínica tendem a avaliar a explicação global de forma mais crítica, enquanto a explicação local é avaliada de modo semelhante independentemente da idade ou do tempo de atuação. As correlações com o conhecimento prévio em XAI são fracas, sugerindo que esse fator tem pouca influência sobre a avaliação.

**Conclusão:** Há correlação sócio-demográfica relevante, porém restrita à explicação global: idade e tempo de atuação reduzem a avaliação da Fig. 1 de forma moderada e significativa. Esse efeito praticamente desaparece na explicação local (Fig. 2), que se mostra mais robusta ao perfil do respondente.

---

## 6. Existe diferença entre o gráfico de explicação global versus o gráfico de explicação local?

Descritivamente, sim. A **Figura 2 (explicação local — SHAP Local)** recebeu avaliação média superior à **Figura 1 (explicação global — SHAP Global)** em todas as cinco dimensões avaliadas:

| Dimensão | Global (Fig. 1) | Local (Fig. 2) | Δ (Local − Global) |
|---|---|---|---|
| user-aware | 3,64 | 3,95 | +0,31 |
| context-aware | 3,59 | 3,91 | +0,32 |
| objectivity | 3,45 | 3,77 | +0,32 |
| understandability | 3,36 | 3,55 | +0,19 |
| informative | 3,32 | 3,55 | +0,23 |
| **Soma total** | **17,36** | **18,73** | **+1,37** |

A diferença é consistente na direção (local > global em todas as dimensões), sendo mais expressiva em *context-aware* e *objectivity* (Δ = +0,32) e menor em *understandability* (Δ = +0,19).

A dimensão compreensível (*understandability*) da Fig. 1 foi a única com mediana = 3 (Neutro), enquanto todas as dimensões da Fig. 2 tiveram mediana = 4 (Concordo).

Porém, essa diferença não é estatisticamente significativa. O teste de Wilcoxon pareado entre as médias por respondente (media_fig1 vs. media_fig2) resultou em p = 0,105 (> 0,05), com médias de 3,47 (global) e 3,75 (local). Ou seja, embora a explicação local seja consistentemente mais bem avaliada, com n = 22 não há evidência estatística suficiente para afirmar que a diferença se sustenta na população.

**Conclusão:** A explicação local do SHAP (Fig. 2), que apresenta a contribuição de cada variável para um caso específico, é percebida de forma mais favorável em todas as dimensões (mais adequada, relevante, objetiva, compreensível e informativa), sugerindo que é a mais apropriada para uso clínico por ser orientada ao caso individual do paciente. Contudo, essa vantagem é uma tendência descritiva que não alcançou significância estatística (Wilcoxon p = 0,105), o que recomenda cautela na interpretação e/ou ampliação da amostra para confirmação.
