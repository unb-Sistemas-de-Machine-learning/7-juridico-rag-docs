## Histórico de versões

| Versão | Alteração       | Responsável         | Data Alteração |
|--------|-----------------|---------------------|----------------|
| 1.0    | Criação do documento e adição da estrutura dos diretórios | Diógenes Dantas Lélis Júnior | 10/12/2025  |


## Visão geral

Este documento descreve a organização do repositório do projeto e serve como guia rápido para
desenvolvedores e avaliadores localizarem os principais componentes (código, notebooks,
documentação e dependências). O repositório está hospedado no GitHub;

As seções a seguir mostram a estrutura de diretórios e uma breve descrição do conteúdo de cada
item para facilitar a navegação.

## Estrutura dos diretórios

```
.
├── src/
│   ├── scrapping/
│   │   ├── criterios_rotulados.json
│   │   └── scrapping.ipynb
│   └── chat/
│       └── webchat.py
├── .gitignore
├── README.md
└── requirements.txt
```

Breve descrição:

- `src/`: código-fonte do projeto.
- `src/scrapping/`: notebooks e artefatos relacionados à coleta e rotulação de dados.
- `src/chat/`: implementação do agente conversacional e componentes de integração (ex.: `webchat.py`).
- `requirements.txt`: lista de dependências Python necessárias para executar o projeto.
- `README.md`: instruções gerais de instalação, execução e descrição do projeto.

