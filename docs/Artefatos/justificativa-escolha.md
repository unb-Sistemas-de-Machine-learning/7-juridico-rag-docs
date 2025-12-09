## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Criação do documento | Diógenes Dantas Lélis Júnior | 09/12/2025 |


## Visão geral
Para a construção do nosso sistema de Recuperação Aumentada por Geração (RAG), optamos por utilizar o **Gemini** como modelo de linguagem e o **RAGFlow** como framework de orquestração da busca e geração.

## Coerência com o problema e os dados
Nosso problema envolve o fornecimento de respostas baseadas em documentos específicos, exigindo:

- Capacidade de **entender perguntas complexas**
- **Generalização sem alucinar** informações
- Suporte a **múltiplos formatos de documento**
- Respostas em português com **alta fluência**

O Gemini atende diretamente a essas necessidades, pois é um LLM multimodal otimizado para compreensão contextual e integração com pipelines RAG. O RAGFlow, por sua vez, facilita a indexação, chunking e recuperação eficiente dos dados, garantindo que o modelo sempre se baseie na fonte correta.

## Comparação com baseline simples
Como baseline, consideramos dois cenários:

| Abordagem | Resultado | Limitações |
|----------|-----------|------------|
| Busca por palavra-chave (sem LLM) | Recupera trechos relevantes | Não gera respostas estruturadas; depende de termos exatos |
| LLM puro (sem RAG) | Respostas mais fluídas | Pode inventar dados não presentes nos documentos ("alucinações") |

O uso de **Gemini + RAGFlow** obteve desempenho superior nesses pontos:

- Recuperação precisa das informações corretas
- Redução de alucinações em comparação ao LLM sem RAG
- Melhor compreensão semântica em relação à busca por palavras

## Justificativa clara da escolha
A escolha não foi apenas baseada em performance numérica, mas em requisitos do projeto:

| Requisito | Justificativa |
|----------|---------------|
| Integrar dados proprietários ao modelo | A arquitetura RAG garante segurança e precisão nas respostas |
| Facilidade de implementação | O RAGFlow fornece componentes prontos para pipeline e monitoramento |
| Qualidade das respostas | O Gemini demonstra melhor coerência, fluidez e contexto nas respostas |
| Evolutividade | Permite expansão do índice e troca de modelo sem reescrever o sistema |

Portanto, a combinação **RAGFlow + Gemini** foi selecionada por ser a mais alinhada ao escopo: oferecer respostas confiáveis, contextualizadas e fidelizadas ao conteúdo dos documentos indexados.
