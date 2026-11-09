# SensIA

Projeto científico desenvolvido para o 2° Challenge da **Residência em Inteligência Artificial**, promovida pelo Instituto Eldorado em parceria com a Pontifícia Universidade Católica de Campinas (PUC-Campinas).

O projeto investiga a aplicação de técnicas de Inteligência Artificial e Aprendizado de Máquina na análise e classificação de vídeos com base na intensidade dos estímulos audiovisuais, considerando características como movimentação, cores, frequência de cortes e complexidade visual.

## Objetivo Geral

Desenvolver uma solução multiagente baseada em inteligência artificial que contribua para a promoção do bem-estar por meio da análise de estímulos visuais presentes em conteúdos audiovisuais, oferecendo informações fundamentadas em evidências científicas e recomendações personalizadas que auxiliem os usuários na escolha consciente de vídeos, de acordo com suas preferências e necessidades individuais.

## Objetivos Específicos

- Analisar e classificar os estímulos visuais presentes em vídeos, considerando características como movimento, frequência de mudanças de cena, variações de cores e luminosidade, utilizando técnicas de visão computacional. 

- Identificar a temática dos conteúdos audiovisuais, utilizando técnicas de inteligência artificial para reconhecer e classificar os temas dos vídeos analisados. 

- Fundamentar as análises em evidências científicas, por meio de uma base de conhecimento composta por artigos científicos, permitindo a apresentação de explicações e referências sobre as características dos estímulos visuais. 

- Desenvolver uma interface conversacional, permitindo que os usuários consultem informações sobre os vídeos analisados, esclareçam dúvidas e compreendam os resultados apresentados. 

- Recomendar conteúdos audiovisuais alternativos, priorizando vídeos com menor intensidade de estímulos visuais e temáticas semelhantes ao conteúdo original, respeitando as preferências individuais dos usuários. 

- Contribuir para a promoção do bem-estar, incentivando a autonomia dos usuários e a escolha consciente de conteúdos audiovisuais por meio de informações claras e acessíveis.

## Agentes

| Agente | Função Principal | 
|--------|---------|
| Agente 1 - Agente Conversacional  | Responsável por interagir com o usuário, apresentar os resultados das análises das características visuais extraídas, consultar artigos científicos por meio de RAG e fornecer explicações fundamentadas. Também coordena a comunicação com o Agente Recomendador quando receber uma recomendação de um vídeo.  |
| Agente 2 - Agente Recomendador | Responsável por consultar o dataset de vídeos previamente analisados, identificar conteúdos com temáticas semelhantes e menor intensidade de características visuais e enviar as recomendações ao Agente Conversacional.  | 
