# Agente Simples (Inicial)

Agente desenvolvido como uma das entregas do 2º Challenge da Residência em IA. Sua função é fornecer explicações sobre as métricas visuais extraídas de um vídeo, consultando uma base de conhecimento por meio da técnica de **Retrieval-Augmented Generation (RAG)**.

## 🔄 Como o Agente Funciona

O fluxo de funcionamento do agente processa as solicitações do usuário integrando raciocínio de linguagem natural, execução de ferramentas em Python e recuperação de conhecimento em bases de dados locais.

```mermaid

flowchart LR
    U["Pergunta do<br/>usuário"] --> A["Llama escolhe<br/>a ação"]
    A --> P["Python executa<br/>a ferramenta"]
    P --> G["Llama gera<br/>a resposta"]
    G --> R["Resposta ao<br/>usuário"]

    P -->|Consulta| KB["Artigos científicos<br/>Busca TF-IDF nos PDFs"]
    KB -->|Trechos recuperados| G

    V["Vídeo opcional"] --> CV["OpenCV<br/>Saturação, brilho e diferença<br/>entre frames"]
    CV --> M["Métricas disponíveis"]
    M -->|Leitura das métricas| P

    classDef claro fill:#e2eff0,stroke:#e2eff0,color:#123f50
    classDef escuro fill:#123f50,stroke:#123f50,color:#ffffff

    class U,KB,V,CV,M,R claro
    class A,P,G escuro

    linkStyle default stroke:#159ca3,stroke-width:1.5px
    
```

## Estrutura dos arquivos

| Arquivo | Descrição |
|---|---|
| `Agente_Simples.ipynb` | Notebook com os códigos e funcionamento do agente inicial |
| `SensIA` | Slides da apresentação do dia 30/10 |


