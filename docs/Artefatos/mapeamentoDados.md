## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Daniela Soares  | Mapeamento e Rotulação dos Dados| 19/10/2025 |


## Visão geral

Foi desenvolvida uma **tabela de mapeamento de dados** para organizar os critérios extraídos das páginas oficiais dos programas sociais (gov.br), garantindo que o modelo RAG utilize informações estruturadas e coerentes com os requisitos do projeto.

As variáveis foram rotuladas automaticamente por meio de expressões regulares e palavras-chave, utilizando Python e bibliotecas como **BeautifulSoup e re**. Cada campo representa um critério específico de elegibilidade, como renda, idade ou composição familiar, e é armazenado em formato **JSON**, facilitando a integração ao modelo.

#### Tabela de Mapeamento

| **Rótulo**            | **Descrição**                                         | **Exemplo**                                   |
| --------------------- | ----------------------------------------------------- | --------------------------------------------- |
| **renda**             | Limite de renda per capita permitido                  | `{"tipo": "per_capita", "limite": 218.0}`     |
| **idade**             | Faixa etária mínima para o programa                   | `{"minima": 65}`                              |
| **familia**           | Cadastro Único e composição familiar                  | `{"cadastro_unico": true}`                    |
| **condicionalidades** | Requisitos adicionais (vacinação, frequência escolar) | `["vacinação", "frequência escolar"]`         |
| **restrições**        | Vedações, como acúmulo de benefícios                  | `{"no_acumulo": ["aposentadoria", "pensão"]}` |



O processo de rotulação permite que cada programa seja estruturado em JSON, criando uma **base de conhecimento organizada** que o RAG utiliza para cruzar com o perfil do cidadão. Os dados estão **devidamente rotulados** e a tabela reflete fielmente os critérios oficiais, assegurando consistência e precisão na recomendação dos programas sociais.

```
{
  "programa": "Bolsa Família",
  "rotulos": {
    "renda": { "tipo": "per_capita", "limite": 218.0 },
    "idade": {},
    "familia": { "cadastro_unico": true },
    "condicionalidades": ["frequência escolar", "vacinação", "pré-natal"],
    "restricoes": {}
  },
  "categoria_gerada": "Baixa Renda"
}
```