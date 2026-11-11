# Rede Neural

Rede neural criada como uma das entregas do 2º Challenge da Residência em IA.

Foi implementada uma MLP (Multi-Layer Perceptron) utilizando TensorFlow/Keras, com o objetivo de classificar vídeos de acordo com suas respectivas categorias. 


## Arquitetura da MLP

### Hiperparâmetros
Realizou-se um GridSearch para investigar diferentes configurações, considerando o número de neurônios nas camadas ocultas e o coeficiente de regularização L2. A configuração selecionada foi composta por 128 neurônios na 1° camada oculta, 32 neurônios na segunda camada oculta e sem regularização (L2 = 0).

### Camadas
A rede neural possui quatro camadas:
- **entrada:** recebe os _embeddings_ das descrições dos vídeos. Possui 1024 neurônios;
- **1° camada oculta:** possui 128 neurônios, função de ativação ReLU ;
- **2° camada oculta:** possui 32 neurônios, função de ativação ReLU;
- **saída:** possui 9 neurônios, função de ativação Softmax.

(não terminado!)
