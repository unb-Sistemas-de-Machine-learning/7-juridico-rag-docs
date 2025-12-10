## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Criação do documento | Diógenes Dantas Lélis Júnior | 09/12/2025 |


## Visão geral
Nesse documento serão apresentadas as ferramentas que foram utilizadas para a criação do Agente Jurídico para Programas Sociais

### Ferramentas Utilizadas
| Logo | Ferramenta | Função no Projeto | Justificativa de Uso |
|------|------------|------------------|---------------------|
| ![Llama logo](./images/llama.png) | **Llama (LLM)** | Geração de respostas com base no contexto dos documentos recuperados | Modelo multimodal com ótima compreensão textual, reduz alucinações quando usado com RAG |
| ![RagFlow logo](./images/logo.svg) | **RAGFlow** | Orquestração do pipeline RAG (indexação, chunking, embeddings e recuperação) | Facilita a implementação da arquitetura RAG e integração com modelos externos |  
| ![Panel (HoloViz) logo](./images/logo_horizontal_dark_theme.png) | **Panel (HoloViz)** | Desenvolvimento da interface web para interação com o sistema | Permite criação rápida de dashboards e UIs em Python, sem necessidade de frameworks complexos |

