## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Criação do documento, descrição da visão geral, adição de Requisitos Funcionais e não Funcionais | Diógenes Dantas Lélis Júnior, Daniela Soares de Oliveira, Mariana Pereira da Silva | 23/09/2025 |


## Visão geral
Nesse artefato foram colocados os Requisitos Funcionais e Não Funcionais do projeto escolhido pelo grupo, que consiste em um Agente Jurídico para Programas Sociais (Sistema RAG), cujo objetivo é construir um agente de inteligência artificial que atua como um consultor jurídico para programas sociais. O sistema irá consultar a legislação e os dados de elegibilidade da API de Dados Abertos para informar ao cidadão a qual benefício ele tem direito e, mais importante, o porquê.

## Requisitos
Requisitos funcionais descrevem as ações específicas que um sistema ou aplicativo deve ser capaz de executar. Eles são as capacidades concretas e as operações que o software deve realizar para atender às necessidades e expectativas do usuário.
Enquanto os requisitos funcionais delineiam o que um software deve fazer, os requisitos não funcionais especificam como o software deve fazer isso. Eles são cruciais para garantir a qualidade e a eficiência do software, abrangendo aspectos como desempenho, segurança, confiabilidade e usabilidade. Esses requisitos não estão diretamente ligados às funções específicas do software, mas sim à sua operação e ambiente.

### 📌 Requisitos Funcionais (RF)

| ID   | Requisito Funcional          | Descrição |
|------|------------------------------|-----------|
| RF01 | Coleta de informações do usuário | O sistema deve solicitar idade, número de filhos, profissão/situação de trabalho, renda pessoal, renda familiar e escolaridade, tipo de necessidade especial, estado civil e se é profissional autônomo (Sim/Não - caso Sim, tipo de trabalho) |
| RF02 | Coleta opcional de localização | O sistema pode solicitar estado/município, caso algum programa seja regional. |
| RF03 | Armazenamento temporário dos dados | O chatbot deve guardar as informações fornecidas durante a sessão de conversa. |
| RF04 | Validação de dados | O sistema deve validar formatos (ex.: renda numérica, idade positiva) e solicitar correções quando necessário. |
| RF05 | Busca de programas sociais | O sistema deve consultar a base de conhecimento/documentos de elegibilidade para encontrar programas compatíveis. |
| RF06 | Geração de resposta personalizada | O chatbot deve listar programas elegíveis e justificar de forma simples os motivos da elegibilidade. |
| RF07 | Fornecimento de informações adicionais | O chatbot deve fornecer link oficial ou instruções de cadastro em cada programa social. |
| RF08 | Histórico da sessão | O chatbot deve manter o contexto da conversa atual, permitindo perguntas adicionais sobre os programas. |
| RF09 | Fallback em caso de falha | Caso nenhum programa seja encontrado, o chatbot deve informar claramente e indicar canais oficiais (ex.: CRAS, Gov.br). |
| RF10 | Gerador de Arquivo PDF | O chatbot deve fornecer a opção de gerar um PDF com as instruções de cadastro em cada programa social. |

---

### 📌 Requisitos Não Funcionais (RNF)

| ID    | Requisito Não Funcional | Descrição |
|-------|--------------------------|-----------|
| RNF01 | Confiabilidade | As respostas devem ser fundamentadas em fontes oficiais (Gov.br, legislações, documentos públicos). |
| RNF02 | Privacidade e segurança (LGPD) | Dados do usuário não devem ser armazenados permanentemente sem consentimento; devem ser processados apenas durante a sessão. |
| RNF03 | Usabilidade | O chatbot deve usar linguagem clara, simples e acessível a pessoas com baixo nível de escolaridade. |
| RNF04 | Disponibilidade | O sistema deve estar disponível 24/7 para atender os usuários. |
| RNF05 | Escalabilidade | O sistema deve suportar múltiplos acessos simultâneos sem perda de desempenho. |
| RNF06 | Tempo de resposta | O sistema deve responder instantaneamente após a entrada do usuário. |
| RNF07 | Manutenibilidade | A base de conhecimento deve ser fácil de atualizar quando houver mudanças de regras ou novos programas. |
| RNF08 | Auditabilidade | O sistema deve manter logs anônimos das consultas para auditoria, sem comprometer dados sensíveis do usuário. |