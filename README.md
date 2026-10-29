# Backend — Gestão de Resíduos | Amparo-SP

## Sobre o projeto

O **Backend de Gestão de Resíduos** é um projeto acadêmico desenvolvido no curso técnico de Desenvolvimento de Sistemas do SENAI. A proposta consiste em implementar uma API para auxiliar a Prefeitura de Amparo-SP no monitoramento de pontos de descarte irregular de resíduos.

O sistema permite registrar usuários e ocorrências de descarte, classificando os resíduos conforme seu tipo, nível de risco e situação de tratamento. Dessa forma, o projeto busca organizar as informações e facilitar o acompanhamento das ocorrências identificadas no município.

## Objetivos

- Desenvolver uma API para gerenciamento de usuários e ocorrências.
- Implementar operações CRUD (criar, consultar, atualizar e excluir registros).
- Implementar autenticação de usuários por login.
- Consultar e atualizar informações sobre os pontos de descarte irregular.
- Apresentar um resumo com a quantidade total de ocorrências tratadas.
- Modelar a estrutura do sistema por meio de diagramas de banco de dados e de classes.

## Requisitos funcionais

| Código | Requisito | Descrição |
|---|---|---|
| RF001 | CRUD de usuários | Cadastrar, consultar, atualizar e excluir usuários. |
| RF002 | Login | Permitir a autenticação de usuários cadastrados. |
| RF003 | CRUD de resíduos | Gerenciar as ocorrências de descarte irregular. |
| RF004 | Resumo de ocorrências | Exibir a contagem total de resíduos com status **Tratado**. |

## Requisito não funcional

**NF001 — Diagrama de Classes:** desenvolver o diagrama utilizando o [draw.io](https://app.diagrams.net/) e salvar a imagem no formato PNG dentro da pasta `docs`.

## Modelagem do banco de dados

O banco de dados utilizado é o `gestao_residuos`, composto por duas tabelas principais:

- **usuario:** armazena o identificador, nome, e-mail e senha dos usuários.
- **ocorrencia:** registra o usuário responsável, o local do descarte, o tipo de resíduo, o nível de risco, a data e o status da ocorrência.

Os registros de ocorrência são relacionados aos usuários por meio de uma chave estrangeira (`usuarioId`).

### Classificação das ocorrências

| Campo | Valores |
|---|---|
| Tipo de resíduo | Definido conforme o descarte identificado |
| Nível de risco | Baixo, Médio ou Alto |
| Status | Novo, Tratado ou Pendente |

## Tecnologias e ferramentas

- **JavaScript** — implementação da lógica do back-end.
- **Node.js** — ambiente de execução.
- **Express** — estruturação do servidor e das rotas da API.
- **MySQL** — armazenamento e gerenciamento dos dados.
- **SQL** — criação, relacionamento e população das tabelas.
- **Visual Studio Code** — ambiente de desenvolvimento.
- **draw.io** — elaboração dos diagramas do sistema.

## Estrutura do projeto

```text
backend_residuos/
├── db/
│   └── script.sql
├── docs/
│   ├── der_residuos.png
│   └── diagrama_classes.png
├── src/
│   ├── controllers/
│   │   ├── ocorrencia.js
│   │   └── usuario.js
│   ├── db.js
│   └── routes.js
└── server.js
```

## Como executar

1. Instale o [Node.js](https://nodejs.org/) e o [MySQL](https://dev.mysql.com/downloads/).
2. Clone o repositório e acesse a pasta do projeto.
3. Execute o script `db/script.sql` no MySQL para criar e popular o banco de dados.
4. Configure a conexão com o banco de dados no arquivo `src/db.js`.
5. Instale as dependências necessárias:

   ```bash
   npm init -y
   npm install express mysql2
   ```

6. Inicie o servidor:

   ```bash
   node server.js
   ```

7. Utilize uma ferramenta como o [Postman](https://www.postman.com/) para testar as rotas da API.

> **Observação:** os comandos acima pressupõem que o projeto utilize Express e o driver `mysql2`. Ajuste a instalação e a configuração conforme a implementação realizada.

