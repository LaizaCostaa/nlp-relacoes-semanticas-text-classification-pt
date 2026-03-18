#  Ambiguity Detection in NLP: Limits of Traditional vs Semantic Models

Este projeto investiga como diferentes abordagens de NLP lidam com a **detecção de ambiguidade semântica** em textos em português.

O foco não é apenas performance, mas compreender **os limites dos modelos na captura de fenômenos linguísticos complexos**.

---

## Objetivo

Avaliar se modelos tradicionais e baseados em embeddings conseguem distinguir entre:

- textos ambíguos
- textos não ambíguos

---

## Motivação

Durante a análise inicial, observou-se que:

- uma mesma frase pode apresentar múltiplas relações semânticas
- ambiguidade pode coexistir com sinonímia e antonímia na mesma frase
- a classificação multi-classe não representava bem o fenômeno

Isso levou à reformulação do problema para um cenário binário: **Ambiguidade vs Não Ambiguidade**

---

## Abordagens utilizadas

### 1. Baseline — TF-IDF + Logistic Regression
- Representação baseada em frequência de palavras
- Modelo linear simples

### 2. SLM — Embeddings + Logistic Regression
- Representação semântica com Sentence Transformers
- Modelo mais sensível a contexto

---

## Resultados principais

| Modelo | Accuracy | Observação |
|------|--------|-----------|
| TF-IDF | ~0.77 | Alto viés para ambiguidade |
| SLM | ~0.67 | Melhor equilíbrio entre classes |

Embora o modelo baseado em TF-IDF apresente maior acurácia, ele falha em distinguir corretamente os casos não ambíguos.
Já o modelo com embeddings semânticos reduz esse viés, evidenciando que métricas globais nem sempre refletem a qualidade real do modelo.
---

## Principais insights

- Modelos tradicionais tendem a classificar a maioria dos textos como ambíguos
- Embeddings semânticos melhoram a separação entre classes
- Mesmo com modelos mais avançados, a ambiguidade continua difícil de detectar

---

## Limitações

- Dataset pequeno
- Rótulos simplificados (uma classe por frase)
- Possível sobreposição semântica entre categorias

---

## Próximos passos

- Explorar classificação multi-label
- Testar modelos maiores (LLMs)
- Refinar critérios de anotação

---

## Tecnologias

- Python
- Pandas / NumPy
- Scikit-learn
- Sentence Transformers
- Matplotlib

---


A ambiguidade se mostrou um fenômeno complexo, desafiando abordagens tradicionais de NLP.
