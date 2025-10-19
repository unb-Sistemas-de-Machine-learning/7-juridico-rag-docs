## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Adicionando user storys | Mariana Pereira |  19/10/2025 |


## Histórias de Usuário

Este documento descreve os User Stories (ou histórias de usuário), uma técnica utilizada para descrever funcionalidades do sistema sob a perspectiva do usuário final. Elas têm o objetivo de capturar o valor que determinada funcionalidade entrega, expressando de forma simples quem precisa da funcionalidade, o que deseja e por que isso é importante. Além disso, cada User Story é acompanhada de critérios de aceitação, que definem as condições necessárias para que a funcionalidade seja considerada completa e validada, garantindo clareza, rastreabilidade e alinhamento entre equipe e stakeholders.

## RF01 – Coleta de informações do usuário

**User Story:**  
Como um **cidadão interessado em saber meus direitos**, quero **informar meus dados pessoais e socioeconômicos** para que o chatbot possa **analisar minha situação e indicar benefícios sociais compatíveis**.

**Critérios de Aceitação:**
- O chatbot deve solicitar: nome, idade, sexo, número de filhos, profissão/situação de trabalho, quantidade de pessoas no domicílio, renda pessoal e familiar, escolaridade, necessidade especial, estado civil e se é autônomo.  
- Caso o usuário selecione “Sim” para autônomo, o sistema deve solicitar o tipo de trabalho.  

---

## RF02 – Coleta opcional de localização

**User Story:**  
Como um **usuário**, quero **informar minha localização (estado/município)** para que o sistema **verifique se há programas sociais regionais disponíveis**.

**Critérios de Aceitação:**
- O chatbot deve perguntar de forma opcional a localização.  
- Caso o usuário informe, os resultados devem incluir programas locais.  
- Caso o usuário não informe, o chatbot deve continuar normalmente.

---

## RF03 – Armazenamento temporário dos dados

**User Story:**  
Como **usuário do chatbot**, quero que **meus dados sejam armazenados temporariamente durante a conversa**, para que o sistema **mantenha o contexto sem exigir reenvio de informações**.

**Critérios de Aceitação:**
- As informações devem ser mantidas apenas durante a sessão ativa.  
- Se o usuário reiniciar o chat, os dados anteriores devem ser descartados.  
- O sistema deve conseguir relembrar respostas anteriores dentro da conversa atual.

---

## RF04 – Validação de dados

**User Story:**  
Como um **usuário**, quero que **o sistema valide automaticamente os dados inseridos**, para que eu **corrija informações incorretas antes da análise**.

**Critérios de Aceitação:**
- Idade e renda devem aceitar apenas números positivos.  
- O chatbot deve exibir mensagens de erro claras e orientar o usuário na correção.

---

## RF05 – Busca de programas sociais

**User Story:**  
Como **usuário**, quero que **o chatbot busque na base de conhecimento os programas sociais elegíveis** de acordo com meus dados, para que **eu saiba quais benefícios posso solicitar**.

**Critérios de Aceitação:**
- A busca deve ser feita em documentos ou base de dados previamente configurados.  
- O sistema deve considerar critérios de elegibilidade (idade, renda, etc.).  
- Devem ser retornados apenas programas compatíveis.

---

## RF06 – Geração de resposta personalizada

**User Story:**  
Como **usuário**, quero que **o chatbot me mostre uma lista personalizada de programas sociais** com **explicações simples sobre por que me enquadro em cada um**, para **entender meus direitos facilmente**.

**Critérios de Aceitação:**
- Cada programa exibido deve conter uma breve justificativa da elegibilidade.  
- O chatbot deve utilizar linguagem acessível e não técnica.  
- A resposta deve ser apresentada de forma organizada (lista ou blocos).

---

## RF07 – Fornecimento de informações adicionais

**User Story:**  
Como **usuário**, quero que **o chatbot me forneça links oficiais e instruções de cadastro**, para que **eu possa acessar diretamente as plataformas dos programas sociais**.

**Critérios de Aceitação:**
- Cada programa listado deve conter um link oficial (Gov.br ou site estadual).  
- Caso o link não exista, o chatbot deve indicar como buscar mais informações.  
- As instruções devem ser atualizadas e claras.

---

## RF08 – Histórico da sessão

**User Story:**  
Como **usuário**, quero que **o chatbot mantenha o histórico da conversa**, para que **eu possa fazer perguntas complementares sem precisar reinformar meus dados**.

**Critérios de Aceitação:**
- O chatbot deve manter o contexto até o término da sessão.  
- O usuário pode perguntar sobre um programa mencionado anteriormente.  
- O histórico deve ser descartado ao encerrar a sessão.

---

## RF09 – Fallback em caso de falha

**User Story:**  
Como **usuário**, quero que **o chatbot me avise quando não encontrar programas disponíveis**, para que **eu saiba onde buscar ajuda ou informações adicionais**.

**Critérios de Aceitação:**
- Caso nenhum programa seja identificado, deve ser exibida uma mensagem clara.  
- O chatbot deve sugerir canais oficiais (ex.: CRAS, Gov.br).  

---

## RF10 – Gerador de Arquivo PDF

**User Story:**  
Como **usuário**, quero **gerar um arquivo PDF com a lista de programas sociais e instruções de cadastro**, para que **eu possa salvar e consultar as informações posteriormente**.

**Critérios de Aceitação:**
- O chatbot deve oferecer opção de exportar as informações em PDF.  
- O PDF deve conter os programas listados, justificativas e links oficiais.  
- O arquivo deve ser legível e possuir formatação organizada.

