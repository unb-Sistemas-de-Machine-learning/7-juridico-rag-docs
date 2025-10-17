## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Criação do documento, descrição da visão geral | Diógenes Dantas Lélis Júnior | 18/10/2025 |
| 1.1    | Adição de Requisitos Funcionais e Não Funcionais | Diógenes Dantas Lélis Júnior | 18/10/2025 |
| 1.2    | Adição do ML canva | Diógenes Dantas Lélis Júnior e Métricas de Sucesso | 19/10/2025 |


## Visão geral
Este documento descreve os requisitos funcionais e não funcionais derivados do ML Canva desenvolvido pelo grupo, bem como as métricas de sucesso que serão utilizadas para avaliar o desempenho e o impacto social do modelo.

A abordagem utiliza classificação multi-rótulo, permitindo que um único usuário possa ser associado a diferentes programas simultaneamente. O modelo será integrado a um chatbot inteligente, que apresentará as recomendações de forma simples e acessível, informando também a descrição e a localização dos programas disponíveis.

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

---

### Métricas de Sucesso
| ID    | Tipo | Descrição |
|-------|--------------------------|-----------|
| MTR01 | Métrica de Impacto | Taxa de aceitação das recomendações (feedback positivo via chatbot). |
| MTR02 | Métrica de Impacto | Juntar as informações para saber a quantidade de pessoas que conhecem os programas, por meio de perguntas ao usuário |
| MTR03 | Métrica de Impacto | Perguntar ao usuário se são realmente elegíveis ao programas sociais informados |

## ML Canva
<iframe width="768" height="432" src="https://miro.com/app/live-embed/uXjVJHkbCC4=/?embedMode=view_only_without_ui&moveToViewport=2275,-1293,3567,2763&embedId=983399899643" frameborder="0" scrolling="no" allow="fullscreen; clipboard-read; clipboard-write" allowfullscreen></iframe>
