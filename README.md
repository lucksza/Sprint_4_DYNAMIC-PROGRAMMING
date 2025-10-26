# DYNAMIC PROGRAMMING - Sprint 4

## 📘 Introdução
Este projeto faz parte da **Sprint 4** e tem como objetivo aplicar **Programação Dinâmica** para resolver um problema de **controle de estoque com demanda estocástica**.  
A proposta consiste em encontrar a política ótima de pedidos que minimize o custo total esperado, considerando incertezas na demanda e possíveis atrasos na entrega (lead time).

O código foi implementado em **Python** utilizando **Jupyter Notebook (.ipynb)** e explora conceitos avançados de otimização estocástica, análise de sensibilidade e simulação.

---

## ⚙️ Estrutura do Projeto
- **codigo.ipynb** → notebook principal contendo toda a implementação da Programação Dinâmica, simulações e visualizações.  
- **Dynamic_Programming_Sprint4.docx** → relatório explicativo com capa, sumário e descrição detalhada das estruturas e algoritmos utilizados.  
- **Explicacao_Estruturas_Algoritmos_Formatado.pdf** → versão formatada do relatório em PDF.  
- **README.md** → documento de descrição do projeto (este arquivo).

---

## 🧠 Descrição da Lógica e Metodologia

### 1. Modelagem do Problema
O sistema modela o controle de estoque de um produto com demanda diária incerta, representada por uma **distribuição de Poisson**.  
Cada decisão (pedido de reposição) envolve custos fixos e variáveis, além de custos de armazenagem e penalidades por falta.

### 2. Estados e Ações
- **Estado:** nível de estoque atual e, se houver *lead time*, o pipeline de pedidos pendentes.  
- **Ação:** quantidade de itens a ser pedida no início de cada período.

### 3. Programação Dinâmica
A Programação Dinâmica define uma **função valor** que retorna o custo mínimo esperado a partir de cada estado.  
Foram implementadas duas abordagens:
- **Recursiva com memoização (`@lru_cache`)**
- **Iterativa bottom-up**, que percorre o horizonte de tempo de forma reversa.

### 4. Política Ótima
A partir da função valor, obtém-se a **política ótima**, ou seja, a quantidade ideal de itens a pedir em cada estado e período.  
Essa política é visualizada por meio de **mapas de calor** que indicam as regiões onde é vantajoso realizar novos pedidos.

### 5. Simulação
O modelo inclui uma etapa de simulação para validar o comportamento da política ótima sob diferentes demandas aleatórias, medindo custos médios e níveis de serviço.

### 6. Análise de Sensibilidade
Por meio da função `sensitivity_sweep`, o código avalia como o custo ótimo e as decisões são afetados por mudanças nos parâmetros `K` (custo fixo de pedido) e `p` (penalidade por falta).

---

## 💾 Execução do Projeto

### Requisitos
Certifique-se de ter o **Python 3.9+** instalado, juntamente com as seguintes bibliotecas:
```bash
pip install numpy matplotlib scipy
```

### Execução
1. Abra o arquivo `codigo.ipynb` no **Jupyter Notebook** ou **Google Colab**.  
2. Execute as células em sequência.  
3. Analise as saídas gráficas e tabelas de políticas ótimas.  

Se estiver utilizando o Colab, basta fazer upload do notebook e rodar diretamente no ambiente.

---

## 📊 Resultados Esperados
- Política ótima de pedidos para cada combinação de tempo e nível de estoque.  
- Comparação entre métodos recursivo e iterativo (validação de consistência).  
- Simulações de desempenho da política sob cenários estocásticos.  
- Análises gráficas (mapas de calor e curvas de sensibilidade).  

Esses resultados demonstram a eficiência da Programação Dinâmica na tomada de decisão sob incerteza.

---

## 👥 Equipe e Créditos
**Trabalho:** DYNAMIC PROGRAMMING - Sprint 4  
**Integrantes:**  

-Lucca Borges RM554608

-Ruan Vieira RM557599

-Rodrigo Carnevale RM558148

*(Preencha conforme a equipe)*

---

## 🏁 Conclusão
O projeto ilustra de forma prática a aplicação da Programação Dinâmica em problemas reais de gestão de estoque, mostrando como a análise probabilística e o uso de algoritmos otimizados podem reduzir custos e melhorar o planejamento logístico.

