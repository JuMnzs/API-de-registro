# API de registro

## Pré-requisitos

- Node.js 18+
- MySQL
- npm


## Módulos instalados

- `bcryptjs`
- `express`
- `mysql2`
- `dotenv`
- `ts-node-dev`

## Descrição

Este repositório contém uma API simples de registro (cadastro) em Node.js/TypeScript. Abaixo há instruções rápidas para instalar, configurar e executar o projeto localmente.

## Instalação

1. Instale dependências:

```bash
npm install

```

## Scripts e execução

Você pode adicionar um script `dev` no `package.json` para desenvolvimento com reinício automático:

```json
{
  "scripts": {
    "dev": "ts-node-dev --respawn --transpile-only src/server.ts"
  }
}
```

Ou executar diretamente com `npx`:

```powershell
npx ts-node-dev --respawn --transpile-only src/server.ts
```



## Notas e próximos passos

- Verifique se você tem a pasta `src` e um arquivo de entrada (ex: `src/index.ts`).
- Ajuste as variáveis do `.env` conforme seu banco de dados.
- Posso ajudar a adicionar o script `dev` no `package.json` ou a gerar arquivos iniciais (ex: `src/index.ts`, conexão com MySQL, rotas de registro/login). Deseja que eu faça isso agora?
 
## Banco de dados

Adicione o seguinte SQL para criar o banco e a tabela de usuários:

```sql

CREATE DATABASE registerAPI;

USE registerapi;

CREATE TABLE user (

id INT AUTO_INCREMENT PRIMARY KEY,
name VARCHAR(30) NOT NULL,
email VARCHAR(30) NOT NULL UNIQUE,
password VARCHAR(255) NOT NULL,
created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
updated_at DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);

```

``` Insomnia ou Postman


  Rota: http://localhost:3000/auth/register
  Body:

  {
	"name": "Julio",
	"email": "julio1@email.com",
	"password": "123456"
  }

```
---