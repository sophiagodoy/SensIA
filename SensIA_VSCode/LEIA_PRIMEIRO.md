# SensIA no VS Code

Este pacote executa localmente as mesmas 18 configurações do GridSearch e a avaliação com ROC-AUC por classe. Não requer Colab, GPU, Ollama ou download do BGE-M3.

## 1 Preparar os arquivos

Extraia o ZIP. No Drive, abra `SensIA/rede_macro_9classes/Embeddings` e baixe os três arquivos abaixo. Se o Google baixar outro ZIP, extraia-o também.

- embeddings_treino_descricao.csv
- embeddings_validacao_descricao.csv
- embeddings_teste_descricao.csv

Coloque os três CSVs na subpasta `Embeddings` do pacote, sem renomeá-los. Eles não estão incluídos neste ZIP.

## 2 Abrir o projeto

Use Python 3.11, 3.12 ou 3.13. No VS Code, instale as extensões **Python** e **Jupyter**, publicadas pela Microsoft. Em Arquivo > Abrir Pasta, escolha a pasta que contém `SensIA_GridSearch_Local.ipynb` e `requirements.txt`.

## 3 Instalar as bibliotecas no Windows

Abra Terminal > Novo Terminal nessa pasta e execute, uma linha por vez:

```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install --upgrade pip
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

Não precisa ativar o ambiente: os comandos usam diretamente o Python dele, evitando bloqueios de scripts do PowerShell. Se `py` não existir, mas `python --version` funcionar, substitua `py` por `python` na primeira linha.

## 4 Selecionar o kernel e executar

Abra `SensIA_GridSearch_Local.ipynb`. No canto superior direito, clique em **Select Kernel / Selecionar Kernel > Python Environments > .venv**. Escolha o ambiente desta pasta. Se ele ainda não aparecer, feche e abra o notebook após a instalação.

Execute as células de cima para baixo. A primeira célula de código informa o caminho da pasta de embeddings. Se não encontrar os CSVs, confira esse caminho ou ajuste `PASTA` para o caminho completo do seu computador.

Durante a busca, o terminal do notebook mostrará 18 ajustes. O tempo depende do computador. Os resultados ficam em `resultados_gridsearch`, ao lado de `Embeddings`, em uma nova pasta por execução.

## 5 O que será gerado

- Comparação das 18 configurações e melhor F1 macro da validação.
- Modelo salvo, configuração e hashes dos arquivos.
- Métricas e relatório por classe, matriz de confusão e previsões.
- Nove curvas ROC individuais e painel com todas as classes.

A busca preserva treino/validação e não utiliza o teste para selecionar parâmetros. Os resultados reais dependem de executar com seus CSVs. A lógica de treino foi verificada anteriormente com dados sintéticos; este pacote não contém métricas reais novas.

## Erros comuns

- `ModuleNotFoundError`: escolha o kernel da .venv usada na instalação.
- `FileNotFoundError`: confira a pasta Embeddings e os nomes dos CSVs.
- Falha de sobreposição: os conjuntos compartilham vídeos ou descrições; revise os dados antes de treinar.
- Falha no pip com Python muito novo: utilize uma das versões indicadas acima.

## Referências

- https://code.visualstudio.com/docs/datascience/jupyter-notebooks
- https://code.visualstudio.com/docs/python/environments
- As referências do método de classificação estão no notebook.


## Segunda rodada: Épocas e regularização

Abra `SensIA_Refinamento_Local.ipynb` no mesmo kernel e execute de cima para baixo. O notebook compara 16 configurações de 128 neurônios e a referência de 32 neurônios, cada uma com três sementes (51 ajustes). Seleciona pela média do F1 macro de validação, salva a variação entre sementes e exporta os erros de validação para revisão. Não calcula novas métricas de teste.

Os arquivos ficam em `resultados_refinamento`, em uma nova pasta por execução. O notebook original e os resultados anteriores são preservados.
