# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /login <br/>
POST /need_help <br/>
POST /want_to_help_pf <br/>
POST /want_to_help_pj <br/>
POST /want_to_help_donation


Estes endpoints serão utilizados para cadastro dos itens relacionados a baixo:


## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

---

### Cadastro de Usuário

POST /register

http://localhost:3001/register

```
{
  "email": "rodrigo@gmail.com.br",
  "password": "123456",
  "name": "Rodrigo",
  "age": 21
}
```

---

### Login de Usuário

POST /login

http://localhost:3001/login

Para autorização:
```
'Bearer(<-- nescessário) token_aqui', 
Content-Type: 'application/json'
```

```
 {
      "email": "davi@test.com",
      "password": "123456"
}
```
---

### Preciso de ajuda

POST /need_help

http://localhost:3001/need_help

```
{
      "ocurrency": "deslizamento",
      "city": "toledo",
      "name": "Rodrigo",
			"userId": 2
}
```

---

### Quero ajudar Pessoa Física

POST/want_to_help_pf

http://localhost:3001/want_to_help_pf

Para autorização:
```
'Bearer(<-- nescessário) token_aqui', 
Content-Type: 'application/json'
```
```
{
      "specialist": "medico",
      "city": "toledo",
      "name": "Rodrigo",
			"userId": 2
}
```

---
### Quero ajudar Pessoa Júridica

POST/want_to_help_pj

http://localhost:3001/want_to_help_pj

Para autorização:
```
'Bearer(<-- nescessário) token_aqui', 
Content-Type: 'application/json'
```
```
{
      "company": "empresa SA",
      "city": "toledo",
      "name": "Rodrigo",
			"userId": 2
}
```
---

### Quero ajudar Doações

POST/want_to_help_donation

http://localhost:3001/want_to_help_donation

Para autorização:
```
'Bearer(<-- nescessário) token_aqui', 
Content-Type: 'application/json'
```

```
{
      "value": "Rodrigo",
			"userId": 2
}
```
---

