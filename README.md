# API de usuarios em memoria com NestJS

API REST simples para cadastrar, listar, consultar e excluir usuarios. Os dados ficam somente em memoria, portanto sao apagados sempre que a aplicacao e reiniciada.

## Requisitos

- Node.js 20 ou superior
- npm

## Como executar

```bash
npm install
npm run start:dev
```

A API ficara disponivel em `http://localhost:3000`.

## Endpoints

### Criar usuario

`POST /users`

```json
{
  "name": "Nicholas Villela",
  "email": "nicholas@example.com"
}
```

Resposta `201 Created`:

```json
{
  "id": 1,
  "name": "Nicholas Villela",
  "email": "nicholas@example.com"
}
```

### Listar todos os usuarios

`GET /users`

Resposta `200 OK`:

```json
[
  {
    "id": 1,
    "name": "Nicholas Villela",
    "email": "nicholas@example.com"
  }
]
```

### Consultar um usuario

`GET /users/1`

Resposta `200 OK` quando o usuario existe. Caso contrario, a API retorna `404 Not Found`.

### Excluir um usuario

`DELETE /users/1`

Resposta `204 No Content` quando a exclusao e concluida. Caso o usuario nao exista, a API retorna `404 Not Found`.

## Validacao

No cadastro, `name` e obrigatorio e `email` precisa ter um formato de e-mail valido. Campos extras tambem sao rejeitados.
