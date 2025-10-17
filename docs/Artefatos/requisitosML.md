## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Criação do documento, descrição da visão geral | Diógenes Dantas Lélis Júnior | 18/10/2025 |
| 1.1    | Adição de Requisitos Funcionais e Não Funcionais | Diógenes Dantas Lélis Júnior | 18/10/2025 |


## Visão geral


### 📌 Requisitos Funcionais (RF)

| ID   | Requisito Funcional          | Descrição |
|------|------------------------------|-----------|
| RF01 | Classificação Multi-rótulo | O modelo deve prever para quais programas sociais um usuário é elegível. |
| RF02 | Coleta e atualização periódico dos dados de treinamento | Deve existir um pipeline de coleta de dados com atualização anual (ou contínua). |
| RF03 | Predição em Tempo Real | O sistema deve receber os dados de entrada e emitir previsões imediatamente, sem armazenar informações sensíveis. |
| RF04 | Integração com Chatbot | O chatbot deve usar as previsões do modelo para apresentar ao usuário os programas sociais elegíveis. |
| RF05 | Simulação de Impacto | O sistema deve permitir testar o impacto do modelo (avaliar desempenho e retorno esperado). Deve remover vieses e avaliar a acurácia antes da implantação. |
| RF06 | Pré-processamento e criação de características (features) | Extração de atributos como nome, renda, escolaridade, número de filhos, estado civil, profissão, etc. Tratamento e normalização de dados para entrada no modelo.  |

---

### 📌 Requisitos Não Funcionais (RNF)

| ID    | Requisito Não Funcional | Descrição |
|-------|--------------------------|-----------|
| RF01 | Desempenho | Tempo de resposta em tempo real (< 5 segundos por requisição). |
| RF02 | Escabilidade | Deve suportar grande número de usuários simultâneos (via API ou chatbot). |
| RF03 | Privacidade e segurança dos dados | Nenhum dado pessoal deve ser armazenado indevidamente. Cumprimento da LGPD. |
| RF04 | Imparcialidade e transparência | O modelo deve evitar vieses (ex: por renda, gênero, região). |
| RF05 | Confiabilidade e monitoramento contínuo | Sistema de logs e alertas para falhas de predição. |
