## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Coleta e armazenamento de dados | Daniela Soares | 17/10/2025  |
| 1.1    | Adiciona técnicas de amostragem | Diógenes Júnior | 18/10/2025  |


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

## Balanceamento de Classes

## Feature Engineering