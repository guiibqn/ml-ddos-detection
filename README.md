# 🛡️ Detecção de Ataques DDoS com Machine Learning (XGBoost)

Este projeto desenvolve um modelo preditivo de Inteligência Artificial para Cibersegurança, capaz de identificar padrões anômalos e detectar ataques de Negação de Serviço (DDoS) do tipo Portmap, utilizando o dataset massivo CICDDoS2019.

> 🤝 **Nota:** Este projeto foi desenvolvido em equipe como Pesquisa Curricularizada de Graduação (PCG) na Universidade Católica de Santos.

## 💻 Tecnologias Usadas
- Linguagem: Python
- Manipulação de Dados: Pandas, NumPy
- Machine Learning: Scikit-learn, XGBoost
- Análise Exploratória: YData Profiling, Matplotlib, Seaborn
- Ambiente: Google Colab / Jupyter Notebook

## ✨ Principais Funcionalidades e Pipeline de Dados
- **Limpeza Cirúrgica:** Remoção de valores nulos/infinitos e atributos não numéricos.
- **Redução de Multicolinearidade:** Aplicação da Correlação de Pearson, removendo atributos com mais de 50% de correlação para otimizar o modelo.
- **Balanceamento de Classes:** Aplicação de Undersampling na classe de ataques (reduzida de 175.000 para 5.000 amostras) para parear com o tráfego benigno e evitar viés (bias).
- **Validação Cruzada:** Divisão do dataset em 60% para treino, 20% para validação e 20% para testes.

## 📊 Resultados e Métricas Alcançadas
O modelo XGBoost demonstrou altíssima eficácia na classificação de tráfego de rede, entregando métricas consistentes no conjunto de testes:
- **Acurácia:** ~92.12%
- **F1-Score:** 0.92
- **Precisão / Recall:** 0.92 / 0.92
- **AUC-ROC:** 0.9603 (Indicando excelente capacidade discriminativa).

A análise de importância de *features* revelou que o comportamento temporal, como o intervalo entre chegadas de pacotes (`IAT - Inter-Arrival Time`), e o tamanho inicial da janela de bytes (`Init_Win_bytes_backward`) são os maiores indicadores de ataques Portmap.

## 🧠 O que eu aprendi
Neste projeto, aprofundei meus conhecimentos na manipulação de Big Data com Pandas. Compreendi o impacto crítico do balanceamento de classes em cibersegurança e aprendi a ler e interpretar métricas complexas de avaliação (AUC-ROC e Matriz de Confusão). Também desenvolvi uma forte visão sobre como características de rede de baixo nível (como *flags* TCP e tamanhos de janela) se traduzem em vetores de ataque.

## 🛠️ Como pode ser melhorado (Próximos Passos)
- Explorar técnicas avançadas de Oversampling (como SMOTE-NC ou GANs) em substituição ao Undersampling.
- Envelopar o modelo treinado em uma API REST para receber logs de rede e realizar inferências em tempo real.
- Testar a resiliência do modelo contra datasets de intrusão mais recentes.

## 🚀 Como Rodar o Projeto
Para facilitar a execução e a avaliação, o dataset utilizado (focado no ataque Portmap e compactado em `portmap.zip`) já está incluso neste repositório.
1. Clone o repositório.
2. Instale as dependências listadas no `requirements.txt`.
3. Se estiver utilizando o Google Colab, basta fazer o upload do arquivo `portmap.zip` e do notebook para o ambiente. O código já está configurado para extrair e processar os dados automaticamente.
4. Execute as células do notebook sequencialmente.

# Integrantes do Grupo
Guilherme Augusto Boquimpani

## 📸 Preview dos Resultados e Análises
*(prints do Colab: Gráficos de EDA, Matriz de Confusão e a Árvore de Decisão do XGBoost)*
