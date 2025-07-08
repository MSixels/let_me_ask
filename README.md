# Let me Ask

Este projeto foi desenvolvido durante o evento **NLW Agents #20** da RocketSeat.

## Visão Geral

Let me Ask é uma aplicação backend construída com Node.js e Fastify, utilizando Drizzle ORM para interação com o banco de dados PostgreSQL. O projeto segue uma arquitetura modular, com rotas bem definidas e um ambiente de desenvolvimento configurado para facilitar a execução e o teste.

## Tecnologias Utilizadas

- **Node.js**: Ambiente de execução JavaScript.
- **Fastify**: Framework web rápido e de baixo overhead para Node.js.
- **Drizzle ORM**: ORM TypeScript para Node.js, compatível com PostgreSQL.
- **PostgreSQL**: Sistema de gerenciamento de banco de dados relacional.
- **TypeScript**: Superset do JavaScript que adiciona tipagem estática.
- **Zod**: Biblioteca de validação de esquemas TypeScript-first.
- **Docker & Docker Compose**: Para orquestração de contêineres e ambiente de desenvolvimento isolado.

## Padrões de Projeto

O projeto adota uma estrutura de pastas que reflete uma abordagem modular, separando as responsabilidades em:

- `src/db`: Contém a configuração do banco de dados, esquemas (Drizzle ORM) e migrações.
- `src/http/routes`: Define as rotas da API, mantendo a lógica de negócio separada da camada de transporte.
- `src/env.ts`: Gerenciamento de variáveis de ambiente.

## Setup e Configuração

Para configurar e executar o projeto localmente, siga os passos abaixo:

### Pré-requisitos

Certifique-se de ter o Docker e o Docker Compose instalados em sua máquina.

### 1. Clonar o Repositório

```bash
git clone https://github.com/MSixels/let_me_ask.git
cd let_me_ask
```

### 2. Configurar Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto, baseado no `.env.example`, e preencha com as informações do seu ambiente. Exemplo:

```
DATABASE_URL="postgresql://docker:docker@localhost:5432/let_me_ask"
PORT=3333
```

### 3. Iniciar o Banco de Dados com Docker Compose

```bash
docker-compose up -d
```

Este comando irá iniciar um contêiner PostgreSQL e o pgAdmin (opcional, para gerenciamento do banco de dados).

### 4. Instalar Dependências

```bash
npm install
```

### 5. Executar Migrações do Banco de Dados

```bash
npx drizzle-kit migrate
```

### 6. Popular o Banco de Dados (Opcional)

Para popular o banco de dados com dados de exemplo:

```bash
npm run db:seed
```

### 7. Iniciar a Aplicação

Para iniciar a aplicação em modo de desenvolvimento (com `watch`):

```bash
npm run dev
```

Ou em modo de produção:

```bash
npm start
```

A aplicação estará disponível em `http://localhost:3333` (ou na porta configurada no seu `.env`).

## Rotas da API

- `GET /health`: Verifica a saúde da aplicação.
- `GET /rooms`: Retorna uma lista de salas (exemplo de rota).

## Contribuição

Sinta-se à vontade para contribuir com este projeto. Para isso, faça um fork do repositório, crie uma nova branch para suas alterações e envie um pull request.

## Licença

Este projeto está licenciado sob a licença ISC. Veja o arquivo `LICENSE` para mais detalhes. (Assumindo licença ISC com base no package.json)


