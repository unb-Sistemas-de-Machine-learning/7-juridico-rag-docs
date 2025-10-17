## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Coleta e armazenamento de dados |Daniela Soares | 17/10/2025  |


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