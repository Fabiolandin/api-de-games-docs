# API DE GAMES
Esta api é utilizada para

## Endpoints
### GET /games
esse endpoint é responsavel por retornar a listagem de todos os games cadastrados no banco de dados
#### Parametros
Nenhum
#### Respostas
##### OK! : 200
caso esta resposta aconteça voce vai receber a listagem de todos os games.
Exemplo:
```
[
    {
        "id": 11,
        "title": "League of Legends",
        "year": 2005,
        "price": 0
    },
    {
        "id": 12,
        "title": "Days Gone",
        "year": 2021,
        "price": 199
    },
    {
        "id": 13,
        "title": "Detroit: Become Human",
        "year": 2020,
        "price": 299
    }
```
##### Falha na autenticação!: 401
caos esta resposta aconteça isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: token invalido, Token espirado
Exemplo de resposta:
```
{
    "err": "token invalido"
}
```

### POST /auth
esse endpoint é responsavel por fazer o processo de login
#### Parametros
E-mail: Email do usuario cadastrado.
password: Senha do usuario cadastrada.

Exemplo:
```
{
    "email": "flandin1990@gmail.com",
    "password": "node.js"
}
```

#### Respostas
##### OK! : 200
caso esta resposta aconteça voce vai receber o token jwt para conseguir acessar os endpoints protegidos da api.
Exemplo:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJmbGFuZGluMTk5MEBnbWFpbC5jb20iLCJpYXQiOjE3MjE0OTA2ODEsImV4cCI6MTcyMTY2MzQ4MX0.jARUxsgwV-2OAEvwGSl_BquTBIVulb0Uxif87_2HaPg"
}
```
##### Falha na autenticação!: 401
caos esta resposta aconteça isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou Email errados.
Exemplo de resposta:
```
{
   {err: Credenciais inválidas}
}
```



