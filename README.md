# RAG e Rede Neural

Implementação de soluções de Retrieval-Augmented Generation (RAG) e de uma Rede Neural MLP (Multi-Layer Perceptron) como entregas do 2º Challenge da Residência em IA.

## Retrieval-Augmented Generation (RAG)

## Rede Neural
Foi implementada uma MLP (Multi-Layer Perceptron) utilizando TensorFlow/Keras, com o objetivo de classificar vídeos de acordo com suas respectivas categorias. 


### Arquitetura da MLP

### Hiperparâmetros
Realizou-se um GridSearch para investigar diferentes configurações, considerando o número de neurônios nas camadas ocultas e o coeficiente de regularização L2. A configuração selecionada foi composta por 128 neurônios na 1° camada oculta, 32 neurônios na segunda camada oculta e sem regularização (L2 = 0).

#### Camadas
A rede neural possui quatro camadas:
- **entrada:** recebe os _embeddings_ das descrições dos vídeos. Possui 1024 neurônios;
- **1° camada oculta:** possui 128 neurônios, função de ativação ReLU ;
- **2° camada oculta:** possui 32 neurônios, função de ativação ReLU;
- **saída:** possui 9 neurônios, função de ativação Softmax.

## Estrutura dos arquivos

| Arquivo | Descrição |
|---|---|
| `RAG` | Contém os códigos-fonte da implementação do RAG. |
| `Rede Neural` | Contém os códigos-fonte da implementação da rede neural MLP e a pasta com os embeddings utilizados como dados de entrada do modelo. |

(não terminado!)
