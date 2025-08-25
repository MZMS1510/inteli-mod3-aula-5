# Resumo Executivo: Análise KNN - Acesso à Internet e Evasão Acadêmica

> **Data:** 25/08/2025 | **Análise:** K-Nearest Neighbors | **Dataset:** 500 estudantes brasileiros

---

## 🎯 **Objetivo**
Investigar se estudantes com acesso à internet ruim/instável apresentam maior risco de evasão acadêmica.

## 📊 **Principais Resultados**

### ✅ **Hipótese Confirmada Parcialmente**
| Qualidade do Acesso | Taxa de Risco de Evasão | Diferença vs "Boa" |
|---------------------|------------------------:|--------------------:|
| 🔴 **Ruim**         | **32.4%**              | **+7.5 pp**        |
| 🟡 **Instável**     | **31.0%**              | **+6.1 pp**        |
| 🟢 **Boa**          | **24.9%**              | *baseline*          |

### 🏆 **Melhor Modelo KNN**
- **Configuração**: k=21 + Distância Euclidiana
- **Acurácia**: 78.7%
- **F1-Score**: 75.9%
- **Especificidade**: >88% (excelente detecção de casos sem risco)
- **Sensibilidade**: ~35% (limitada detecção de casos com risco)

### 📈 **Performance por Estrato**
| Acesso    | Acurácia | Sensibilidade | Falsos Negativos |
|-----------|----------|---------------|------------------|
| Boa       | 81.7%    | 35.3%         | 15.5%           |
| Instável  | 78.8%    | 33.3%         | 19.2%           |
| Ruim      | 70.4%    | 40.0%         | 22.2%           |

---

## 🔍 **Insights Técnicos**

### ✅ **O que funcionou bem:**
- Distância **Euclidiana** superou Manhattan consistentemente
- **K=21** ofereceu melhor generalização
- Modelo conservador com alta precisão
- Padrão claro de deterioração com pior acesso

### ⚠️ **Limitações identificadas:**
- **Baixa sensibilidade** para detectar casos de risco
- Teste estatístico **não significativo** (p=0.267)
- **Desbalanceamento** de classes (72% sem risco)
- Amostra pode ser insuficiente para poder estatístico

---

## 💡 **Recomendações**

### 🎓 **Para Instituições de Ensino:**
1. **Monitorar** estudantes com acesso limitado à internet
2. **Implementar** programas de suporte tecnológico
3. **Disponibilizar** recursos offline alternativos
4. **Melhorar** infraestrutura de conectividade no campus

### 🔬 **Para Futuras Pesquisas:**
1. **Expandir** tamanho da amostra
2. **Incluir** métricas específicas de conectividade
3. **Testar** algoritmos ensemble (Random Forest, XGBoost)
4. **Aplicar** técnicas de balanceamento de classes (SMOTE)

### 📊 **Para Políticas Públicas:**
1. **Programas** de inclusão digital estudantil
2. **Subsídios** para conectividade e equipamentos
3. **Parcerias** com provedores para tarifas educacionais

---

## 📋 **Especificações Técnicas**

| Aspecto | Detalhes |
|---------|----------|
| **Algoritmo** | K-Nearest Neighbors (scikit-learn) |
| **Validação** | Cross-validation 5-folds estratificado |
| **Divisão** | 70% treino, 30% teste |
| **Pré-processamento** | StandardScaler + LabelEncoder |
| **Métricas** | Acurácia, Precisão, Recall, F1-Score |
| **Reprodutibilidade** | random_state=42 |

---

## 🎬 **Conclusão**

A análise **confirma parcialmente** a hipótese inicial, demonstrando uma **tendência clara** de maior risco de evasão entre estudantes com pior acesso à internet. Embora o teste estatístico não tenha alcançado significância, a **diferença prática de 7.5 pontos percentuais** é relevante para políticas educacionais.

O modelo KNN mostrou-se eficaz para **identificar estudantes sem risco**, mas precisa de melhorias para **detectar casos de risco**. As recomendações técnicas e institucionais podem contribuir tanto para melhorar os modelos quanto para reduzir a evasão acadêmica.

---

**📁 Arquivos:** `aula.ipynb` | `analise_knn_evasao_internet.md` | `dataset_educacao_graduacao_brasil_500.csv`
