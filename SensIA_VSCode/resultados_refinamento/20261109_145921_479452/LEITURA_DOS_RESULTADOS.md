# Resultado da segunda rodada — 9 de novembro de 2026

Foram executados 51 ajustes: 17 configurações com três sementes (42, 123, 2026). A seleção usou a média do F1 macro na validação. Não foram calculadas novas métricas de teste.

Melhor configuração: 128 neurônios, alpha=0.1, 60 épocas. F1 macro médio de validação: 0.6545; desvio padrão entre sementes: 0.0052. O modelo salvo usa a semente 42, com F1 de validação 0.6532. O desvio entre sementes não representa incerteza entre diferentes amostras.

Comparação das melhores configurações:

```
 neuronios  alpha  epocas  f1_validacao_media  f1_validacao_desvio  f1_validacao_min  f1_validacao_max  f1_treino_media  gap_medio  repeticoes
       128   0.10      60              0.6545               0.0052            0.6500            0.6602           0.8057     0.1512           3
       128   0.03      20              0.6510               0.0087            0.6414            0.6585           0.7972     0.1462           3
       128   0.10      20              0.6496               0.0040            0.6452            0.6528           0.7586     0.1090           3
        32   0.01      20              0.6491               0.0035            0.6454            0.6525           0.7560     0.1069           3
       128   0.10      30              0.6460               0.0071            0.6381            0.6518           0.7795     0.1334           3
       128   0.03      30              0.6418               0.0029            0.6388            0.6445           0.8266     0.1848           3
```

A configuração de 128 neurônios, alpha=0.1 e 20 épocas teve média 0.6496. O ganho de 60 épocas foi aproximadamente 0.0049 (0.49 ponto de F1), pequeno e insuficiente para declarar superioridade consistente. A referência de 32 neurônios continua competitiva. Alpha=1.0 piorou fortemente os resultados desta grade. Não há motivo para ampliar indiscriminadamente épocas ou complexidade.

Próximo trabalho recomendado: revisar os erros de validação e comparar um classificador linear usando os mesmos embeddings e splits. Education apresentou F1 0.3692 no modelo salvo; houve 12 casos previstos como Lifestyle, 11 como News & Politics e 11 como Science & Technology. Hobbies & Interests e Entertainment também apresentam confusão recorrente. Esses resultados sugerem investigar ambiguidade e informação disponível nas descrições, sem provar problemas nos rótulos.

Abra erros_validacao.csv para ler as descrições e confusoes_validacao.csv para ver os pares mais frequentes. Não altere rótulos apenas para concordar com as previsões. Os exemplos de validação já influenciam o desenvolvimento; reserve dados novos para uma avaliação final independente.

Artefatos: modelo_refinamento.joblib, configuracao.json, comparacao_medias.csv, execucoes_por_semente.csv, relatorio_validacao.csv, erros_validacao.csv, confusoes_validacao.csv, epocas_regularizacao.png e matriz_validacao.png.
