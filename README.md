![alt text](image.png)

# 📝 Visão Geral

- Este projeto foi desenvolvido para a Sweet Lift Taxi com o objetivo de otimizar a alocação de motoristas em aeroportos durante horários de pico.
- Através da análise de dados históricos, construímos um modelo de Machine Learning capaz de prever a demanda de corridas para a próxima hora, garantindo eficiência operacional e redução no tempo de espera dos passageiros.

# 🎯 O Desafio

- O principal desafio técnico deste projeto foi lidar com Séries Temporais, realizando o resampling dos dados e identificando padrões de sazonalidade e tendência.
- Métrica Alvo: REQM (Raiz do Erro Quadrático Médio) $\le 48$ no conjunto de teste.
- Critérios de Sucesso: Equilíbrio entre a precisão da predição e o tempo de processamento do modelo.

# 🛠️ Tecnologias e Metodologia

O projeto foi estruturado seguindo as melhores práticas de análise de dados e desenvolvimento:
- Tratamento de Exceções (Try-Except): O projeto utiliza blocos de tratamento de erros para operações críticas, como o carregamento de dados. Isso evita interrupções inesperadas e fornece mensagens claras para o usuário.
- Preparação & ETL: Coleta e nova amostragem dos dados (taxi.csv) em intervalos de uma hora para análise temporal.
- Análise Exploratória (EDA): Identificação de componentes de tendência e sazonalidade horária/diária.
- Modelagem: treinamento de diversos modelos (SARIMAX, LinearRegression, RandomForestRegressor e XGBoost) com ajuste fino de hiperparâmetros.
- Avaliação: Validação rigorosa utilizando uma amostra de teste de 10%.

# 🧬 Pipelines de Machine Learning

Em vez de scripts soltos, utilizamos Pipelines para organizar o fluxo de dados. Isso garante que:
- O pré-processamento seja aplicado de forma idêntica aos dados de treino e teste.
- Não ocorra vazamento de dados (data leakage).
- O código seja modular e fácil de manter.

# 📊 Estrutura dos Dados

O dataset contém:
- datetime: Registro temporal da ocorrência.
- num_orders: Quantidade de pedidos (nossa variável alvo).

# 📈 Resultados e Conclusão
Após testar múltiplos modelos (SARIMAX, LinearRegression, RandomForest e XGBoost), o modelo final foi selecionado com base no equilíbrio entre:
- Qualidade de Predição: Atingindo um REQM inferior a 48 no conjunto de teste.
- Velocidade: Otimização do tempo de treinamento e predição para uso em tempo real.