## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Coleta e armazenamento de dados | Daniela Soares | 17/10/2025  |
| 1.1    | Adiciona técnicas de amostragem | Diógenes Júnior | 18/10/2025  |
| 1.2    | Adição do Data Augmentation e Balanceamento de Classes | Diógenes Júnior | 19/10/2025  |


## Visão geral

##  Coleta e Armazenamento dos Dados Automatizados

###  Justificativa Técnica

#### 1. **Coleta Automatizada dos Dados**
O código realiza a **coleta automática** de informações diretamente de **fontes oficiais do governo** (`gov.br`) usando as bibliotecas `requests` e `BeautifulSoup`:

```python
response = requests.get(url)
soup = BeautifulSoup(response.text, "html.parser")
```

Em seguida, faz **raspagem (web scraping)** com BeautifulSoup:

```
soup = BeautifulSoup(response.text, "html.parser")
```
Isso permite extrair automaticamente o texto completo das páginas dos programas sociais, sem intervenção manual.
Ou seja, os dados são coletados de forma automatizada diretamente da fonte oficial (gov.br).

#### 2.Extração automatizada de informações relevantes

O código busca **critérios específicos (como renda máxima, idade mínima, exigência de Cadastro Único etc.)** com expressões regulares e buscas de palavras-chave:

```
re.search(r"r\$\s*([0-9]+)\s*,?\.?([0-9]*)", texto)
"cadastro único" in texto
```
As regras são aplicadas automaticamente para cada programa listado no dicionário urls.

- Isso significa que o processo de interpretação e estruturação dos dados também é automatizado.

#### 3.Armazenamento automatizado e estruturado

Após a extração, os dados são organizados em um dicionário Python e convertidos para JSON:

```
print(json.dumps(todos_criterios, indent=2, ensure_ascii=False))
```

O JSON é um formato padronizado e facilmente armazenável, que pode ser salvo, transmitido ou usado por outros sistemas. Portanto, há armazenamento estruturado e automatizado das informações coletadas.

## Técnica de Amostragem

### Teste do chatbot com personagens fictícios

#### Amostragem Estratificada
1. Como funciona: Divide os dados em estratos (grupos) com base em uma característica relevante, e então amostra dentro de cada estrato proporcionalmente.

2. Como é aplicada 
    - Crie personagens fictícios que representem algumas as combinações possíveis ou relevantes de renda, escolaridade, número de filhos, cadastro único etc.
    - Por exemplo, uma estratificação por:
        - Renda: baixa, média, alta
        - Escolaridade: fundamental, médio, superior
        - Número de filhos: 0, 1–2, 3 ou mais

3. Isso garante que você teste o chatbot em vários cenários possíveis, não apenas nos mais comuns.

### Coleta de dados reais dos usuários

#### Amostragem Aleatória Simples
1. Como funciona: Cada registro tem a mesma probabilidade de ser selecionado

2. Como é aplicada
    - Selecionar aleatoriamente um subconjunto para responder ao questionário após o uso do chatbot.
    - Vantagem: fácil de implementar e garante representatividade geral.

3. Isso permite entender se o chatbot está conseguindo recomendar os programas sociais corretos

### Tabela Resumo
| Cenário | Técnica Sugerida | Motivo         | 
|--------|-----------------|---------------------|
| Teste do chatbot com personagens fictícios | Estratificada | Garantir cobertura de todos os tipos de usuários e testar casos críticos |
| Coleta de dados reais (conhecimento/elegibilidade) | Aleatória simples | Garantir representatividade geral e a validação das respostas do chatbot |

## Rotulação dos Dados

## Data Augmentation
O principal desafio não era a falta de dados de treinamento para um modelo, mas sim a falta de uma base de conhecimento estruturada, centralizada e acessível sobre os programas sociais. O RAG, por definição, é uma forma de aumentar a capacidade de um modelo de linguagem (LLM, como o Gemini Pro) ao fornecer-lhe dados externos (os requisitos dos programas sociais).

O grupo resolveu priorizar a criação de um Corpus de Conhecimento Relevante (Grounding Data) em vez do treinamento de um modelo do zero.

A "Criação de Dados": Isso foi feito através de uma abordagem de Engenharia de Dados e Conteúdo, que envolveu:

1.  Extração de Fonte: Realização de Web Scraping em documentos oficiais (Editais, Decretos, Portarias) para coletar os requisitos.

2.  Estruturação de Dados: Transformação dos dados semiestruturados/não estruturados (texto dos editais) em um formato estruturado (JSON), definindo esquemas claros

3.  Indexaação para RAG: A conversão desse JSON em chunks e embeddings para o banco de dados vetorial, garantindo que o LLM possa recuperar as regras exatas do programa em tempo de execução.

## Balanceamento de Classes
O projeto lida com um tipo de desbalanceamento, mas a solução não se concentra no balanceamento de classes tradicional e sim na cobertura de requisitos (RAG). O grupo preciso diferenciar onde o desbalanceamento poderia ocorrer e como a arquitetura RAG e a estruturação do JSON mitiga esse risco.

1.  Contexto do "Desbalanceamento" no Projeto
| Nível  | Descrição do Desbalanceamento       | Impacto Potencial  |
|--------|-----------------|---------------------|
| Na Base de Conhecimento   | Alguns programas são muito mais complexos ou têm editais muito mais longos que outros. Exemplo: O edital do Bolsa Família pode ser muito maior em volume de texto (e, portanto, em chunks indexados) do que o do Pé-de-Meia. | O modelo pode ter um "viés de volume", recuperando mais facilmente informações do programa maior, mesmo que a pergunta do usuário seja sobre o programa menor. | 
| Nas Interações/Testes (Dados do Usuário)  | a maioria dos usuários se enquadra na classe "Elegível ao Bolsa Família" ou "Não Elegível a nada". A classe minoritária é o usuário que atende aos requisitos de programas muito específicos e com pouca publicidade. | O grupo pode se concentrar demais nos casos comuns, deixando o chatbot falhar em cenários raros, mas críticos (ex: requisitos muito específicos do BPC). | 

## Feature Engineering