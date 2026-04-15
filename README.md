# 📰 Classificação de Riscos em Notícias para Instituições Financeiras

Modelo de Machine Learning para classificação automática de notícias em categorias de risco, desenvolvido como Trabalho de Conclusão de Curso (TCC).

## 📋 Sobre o Projeto

A identificação e o monitoramento de notícias externas é um processo vital para a gestão de riscos das instituições financeiras. Este trabalho propõe o desenvolvimento de um modelo de Machine Learning capaz de classificar notícias em **seis categorias de risco**:

| Código | Categoria |
|--------|-----------|
| C1 | Risco Econômico |
| C2 | Risco Político |
| C3 | Risco Regulatório |
| C4 | Risco Cibernético |
| C5 | Risco Socioambiental |
| C6 | Sem Relação |

## 🗂️ Estrutura do Repositório

```
classificacao_riscos/
├── Projeto/
│   └── modelo_classificacao_riscos_exec.ipynb   # Notebook principal do modelo
├── bases/
│   └── noticias_tcc_2025.xlsx                   # Base de dados com 1.463 notícias
├── imagens/
│   ├── distribuicao_classes_balanceadas.png      # Distribuição após balanceamento
│   ├── grafico_comparativo_modelos.png           # Comparativo entre modelos
│   ├── grafico_distribuicao_categorias.png       # Distribuição original das categorias
│   ├── grafico_distribuicao_categorias_BALANCEADAS.png
│   ├── grafico_radar_modelos.png                 # Gráfico radar de métricas
│   ├── grafico_ranking_acuracia.png              # Ranking de acurácia
│   ├── matrizes_confusao.png                     # Matrizes de confusão dos modelos
│   ├── nuvem_palavras.png                        # Nuvem de palavras do corpus
│   ├── stopwords_lista_tcc.png                   # Lista de stopwords utilizadas
│   └── tabela_tokens_stopwords.png               # Estatísticas de tokens
└── README.md
```

## ⚙️ Pipeline de Pré-processamento

O pipeline foi implementado sobre a plataforma **Apache Spark** e contempla as seguintes etapas:

1. **Limpeza textual** — remoção de URLs, caracteres especiais e normalização
2. **Tokenização** — segmentação do texto em tokens individuais
3. **Remoção de stopwords** — lista personalizada com 232 termos em português
4. **Vetorização TF-IDF** — representação numérica dos textos via CountVectorizer + IDF

## 📊 Base de Dados

- **1.463 notícias** coletadas de portais diversos
- Rotulação manual para composição da base de treinamento
- Aplicação de **undersampling** na classe majoritária (C6), reduzindo de 50,8% para 28,0%
- Dataset balanceado final: **1.000 registros**

## 🤖 Modelos Avaliados

| Modelo | Acurácia | F1-Score | Precisão | Recall |
|--------|----------|----------|----------|--------|
| **Naive Bayes** | **80,72%** | **0,8065** | **78,64%** | **82,37%** |
| Random Forest | 60,00% | 55,31% | 58,10% | 48,29% |
| Decision Tree | 58,90% | 0,5652 | 58,10% | 49,92% |

O **Naive Bayes** obteve o melhor desempenho em todas as métricas avaliadas, demonstrando-se uma ferramenta viável para suporte à tomada de decisão no monitoramento de riscos.

## 🛠️ Tecnologias Utilizadas

- **Python 3.11**
- **Apache Spark (PySpark)** — processamento distribuído e pipeline de ML
- **Jupyter Notebook** — ambiente de desenvolvimento
- **Matplotlib** — geração de gráficos e visualizações

## 🚀 Como Executar

1. Instale as dependências:
   ```bash
   pip install pyspark matplotlib jupyter
   ```

2. Certifique-se de ter o **Java JDK 11+** instalado e configurado

3. Abra o notebook:
   ```bash
   jupyter notebook Projeto/modelo_classificacao_riscos_exec.ipynb
   ```

4. Execute as células sequencialmente

## 📚 Referências

- Manning, C. D., Raghavan, P., & Schütze, H. (2008). *Introduction to Information Retrieval*. Cambridge University Press.
- Mitchell, T. M. (1997). *Machine Learning*. McGraw-Hill.
- Breiman, L. (2001). Random Forests. *Machine Learning*, 45(1), 5-32.
- Hastie, T., Tibshirani, R., & Friedman, J. (2009). *The Elements of Statistical Learning*. Springer.

## 📄 Licença

Este projeto foi desenvolvido para fins acadêmicos como Trabalho de Conclusão de Curso.

---

*Desenvolvido por alc182 — 2025*
