<img width="2535" height="380" alt="707560415-c69afcc9-ef14-4780-99a4-e74768a01db7" src="https://github.com/user-attachments/assets/dbf5db0a-aab6-45ac-aea9-d86590895fee" />

# Tiamat - Apresentação final de aprendizado de máquina

**Discente**: Raquel Bentes Lima

**Docente**: Prof.Dr. Daniel Roberto Cassar

**Disciplina**: Aprendizado de máquina (*machine learning*)

**Instituição**: Ilum Escola de ciência


## Descrição do projeto

Neste projeto é avaliada a predição do *target* `aveOralM` a partir com conjunto de dados *Infrared Thermography Temperature* do banco de dados do *UCI Irvine Machine Learning Repository*, composto por 1020 amostras e 33 variáveis preditoras. Os dados foram divididos em treino (816 amostras) e teste (204 amostras) com o tratamento de valores ausentes em `Distance` e codificação dentro dos pipelines para evitar vazamento.

Para realizar tal tarefa, um total de cinco algoritmos foi utilizado (Ridge, k-NN, Árvore de decisão, Floresta aleatória e Gradiente Boosting) e seus hiperparâmetros foram comparados com o uso do Optuna.

## Estrutura do repositório
- `Tiamat(5).ipynb`: notebook principal com todo o desenvolvimento ;
- 


## Instalações e Instruções
Requer Python3. Para as bibliotecas e o dataset, basta abrir o notebook em um ambiente Jupyter e executar as células em ordem, de cima para baixo.

## Introdução

Este repositório põe em evidÊncia o notebook `Tiamat(5)`, que explora o dataset Infrared Thermography Temperature, extraído do repositório UCI Machine Learning. A base reúne variáveis como idade, gênero e medições térmicas da face para estimar a temperatura oral a partir de duas variáveis-alvo: aveOralF e aveOralM (sendo esta última o foco desta análise). Na etapa de modelagem, utilizamos a biblioteca Optuna para otimizar os hiperparâmetros de cinco algoritmos de regressão — Ridge, k-NN, Árvore de Decisão, Floresta Aleatória e Gradient Boosting —, avaliando o desempenho por meio de validação cruzada com o objetivo de minimizar o erro (RMSE).

## Metodologia

**Baseline**: Referência com RMSE de 0.5221 e desvio padrão de 0.0534 na validação cruzada.

**Modelos Padrão vs. Otimizados** (`Optuna`): Comparação de modelos em validação cruzada com hiperparâmetros padrão e após otimização via Optuna (reconstruindo os pipelines vencedores e avaliando as 5 notas por fold com ddof=1).

**Escolha do Modelo Final**: Seleção baseada na comparação fold a fold entre os finalistas da validação cruzada.

**Avaliação Final e Interpretabilidade**: Teste único no conjunto X_teste / y_teste (com gráfico de valor real vs. previsto) e análise de importância por permutação (permutation importance).


## Conclusões

Infere-se, portanto, que os modelos obtidos via otimização `Optuna` superaram o valor do baseline, saindo de 0,5221°C para valores próximos à metade. Além disso, uma análise *fold a fold* permitiu avaliar a consistência entre partições antes do teste final, evitando data leakage e mantendo o conjunto de teste reservado para a avaliação final e o gráfico de real vs. previsto.
 
