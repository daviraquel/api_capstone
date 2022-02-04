![Logo SOS Brasil](https://i.imgur.com/r03vPBJ.png "Logo SOS Brasil")

# API SOS Brasil

Esse é o repositório da API do projeto capstone SOS Brasil, elaborado pelo grupo 1 do facilitador Wesley.
```
URL base: https://capstone-api-grupo-1.herokuapp.com
```

# Endpoints

A API conta com 4 endpoints. O usuário consegue se registrar, fazer login, alterar seu perfil e registrar doações. Usuários não cadastrados conseguem visualizar as ONG's parceiras do projeto (/partners), bem como os números de emergência (/help)

&nbsp;

## Endpoints sem autenticação

---

Esses endpoints tem privacidade "444", o que quer dizer que podem ser vistos por todos os usuários, porém os dados são inseridos pelos devs no backend.

- ### Para acessar a lista de todos os parceiros do projeto:

```
GET /partners
```

Resposta: 200 OK

```
[
  {
    "name": "Greenpeace Brasil",
    "description": "Estamos há 26 anos no Brasil confrontando o desmatamento ilegal na Amazônia, indústrias do petróleo e de energia nuclear, produtores de transgênicos e projetos que ameaçam o meio ambiente e as comunidades tradicionais. Esse é o trabalho do Greenpeace.",
    "cnpj": "123456789",
    "cause": "Socioambiental",
    "type": "Preservação Ambiental",
    "logoWide": "https://i.ibb.co/sWWt01D/greenpeace-wide.png",
    "logoSquare": "https://i.ibb.co/p313zyf/greenpeace-sqr.png",
    "site": "https://www.greenpeace.org/brasil/conheca-o-greenpeace/?utm_term=green%20peace&utm_campaign=%5BMAIO/20%5D+Institucional&utm_source=adwords&utm_medium=ppc&hsa_acc=7235609613&hsa_cam=10034725105&hsa_grp=100522293589&hsa_ad=444409237375&hsa_src=g&hsa_tgt=kwd-10941561&hsa_kw=green%20peace&hsa_mt=b&hsa_net=adwords&hsa_ver=3&gclid=Cj0KCQiArt6PBhCoARIsAMF5wah9zx1E8Jo2_NntYNFeoZ-e-CPecgxhkZ9Bp3JeZ1UWmvgktgJOnYsaAhN_EALw_wcB",
    "id": 1
  },
  {
    "name": "CUFA",
    "description": "A CUFA (Central Única das Favelas) é uma organização brasileira reconhecida nacional e internacionalmente nos âmbitos político, social, esportivo e cultural que existe há 20 anos.",
    "cnpj": "123456789",
    "cause": "Humanitária",
    "type": "Seguridade Social",
    "logoWide": "https://i.ibb.co/tHgTT1F/cufa-wide.png",
    "logoSquare": "https://i.ibb.co/344HMSy/cufa-sqr.png",
    "site": "https://www.cufa.org.br/",
    "id": 2
  }
]
```

&nbsp;

- ### Para acessar a lista de todos os telefones de emergência cadastrados:

```
GET /help
```

Resposta: 200 OK

```
[
  {
    "defesa_civil": [
      {
        "Nome": "Defesa Civil",
        "Descrição": "Suporte à Desastres",
        "Telefone": "199",
        "Estado": {},
        "id": 1
      }
    ]
  },
  {
    "policia_militar": [
      {
        "Nome": "Polícia Militar",
        "Descrição": "Emergência Criminal",
        "Telefone": "190",
        "Estado": {},
        "id": 2
      }
    ]
  },
  {
    "bombeiros": [
      {
        "Nome": "Bombeiros",
        "Descrição": "Acidentes",
        "Telefone": "193",
        "Estado": {},
        "id": 3
      }
    ]
  },
  {
    "policia_rodoviaria_federal": [
      {
        "Nome": "Polícia Rodoviaria Federal",
        "Descrição": "Emergência Vias Federais",
        "Telefone": "191",
        "Estado": {},
        "id": 4
      }
    ]
  },
  {
    "policia_rodoviaria_estadual": [
      {
        "Nome": "Polícia Rodoviaria Estadual",
        "Descrição": "Emergência Vias Estaduais",
        "Telefone": "198",
        "Estado": {},
        "id": 5
      }
    ]
  },
  {
    "defensoria_publica": [
      {
        "Nome": "Defensoria Pública",
        "Descrição": "Suporte Júridico",
        "Telefone": "",
        "Estado": {
          "AC": "(68)-3223-2554",
          "AL": "(82)-3315-2782",
          "AP": "(96)-3131-2760",
          "AM": "(92)-3633-2955",
          "BA": "(71)-3117-9002",
          "CE": "(85)-3101-3424",
          "DF": "(61)-2196-4457",
          "ES": "(27)-3198-3300",
          "GO": "(62)-3201-3506",
          "MA": "(98)-3221-3336",
          "MT": "(65)-3648-8400",
          "MS": "(67)-3318-2502",
          "MG": "(31)-3526-0311",
          "PA": "(91)-3201-2713",
          "PB": "(83)-3218-4503",
          "PR": "(41)-3313-7390",
          "PE": "(81)-3182-3702",
          "PI": "(86)-3234-1205",
          "RJ": "(21)-2332-6190",
          "RN": "(84)-3232-7451",
          "RS": "(51)-3210-9407",
          "RO": "(69)-3217-4700",
          "RR": "(95)-2121-0280",
          "SC": "(48)-3665-5665",
          "SP": "(11)-3106-1888",
          "SE": "(79)-3205-3830",
          "TO": "(63)-3218.6736 "
        },
        "id": 6
      }
    ]
  }
]
```

- ### Cadastro de Usuário

```
POST /register
```

Requisição padrão:

```
{
  name: "teste";
  password: "123456";
	"email": "teste@teste.com",
  socialNumber: "123.123.123-12";
  typeOfUser: "CPF";
}
```

Resposta: 201 Created

```
{
  name: "teste";
  password: "123456";
	"email": "teste@teste.com",
  socialNumber: "123.123.123-12";
  typeOfUser: "CPF";
  id: 666;
}
```

&nbsp;

- ### Login de Usuário

```
POST /login
```

Requisição padrão:

```
{
	"email": "teste@teste.com",
	"password":"1234"
}
```

Resposta: 200 OK

```
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InRlc3RlQHRlc3RlLmNvbSIsImlhdCI6MTY0MzkyOTIwMiwiZXhwIjoxNjQzOTMyODAyLCJzdWIiOiI0In0.Arw_lbExiLeljIG3qa-3fkG7Gl_4DSlCPfEW-d0_Q3g",
  "user": {
    "email": "teste@teste.com",
    "name": "teste",
    "social_number": "1234",
    "id": 4
  }
}
```

&nbsp;

## Endpoints com autenticação

---

Nesses endpoints é necessário que seja informado o token no cabeçalho da requisição nesse formato:

```
Authorization: Bearer {token}
```

&nbsp;

- ### Alterar informações do usuário

```
POST /users/${id}
```

Requisição padrão:

```
{
  name: "teste";
  password: "123456";
	"email": "teste@teste.com",
  socialNumber: "123.123.123-12";
  typeOfUser: "CPF";
}
```

Resposta: 200 OK

```
{
  "email": "teste@teste.com",
  "password": "$2a$10$ccfn3eQLINoTYtb81ijFBuJbzEnP9b/vb4XEqV1v0Yvzlf1xHuGhy",
  "name": "teste",
  "social_number": "1234",
  "id": 4,
  "socialNumber": "123.123.123-12",
  "typeOfUser": "CPF"
}
```

&nbsp;

- ### Cadastrar uma doação

```
POST /donations
```

Requisição padrão:

```
{
  "date": "Thu Feb 03 2022 20:17:06 GMT-0300 (Argentina Standard Time)",
  "partner": "Greenpeace",
  "value": 200,
	"userId": 4
}
```

Resposta: 201 Created

```
{
  "date": "Thu Feb 03 2022 20:17:06 GMT-0300 (Argentina Standard Time)",
  "partner": "Greenpeace",
  "value": 200,
  "userId": 4,
  "id": 2
}
```

&nbsp;

## Colaboradores:

- ### [Davi Raquel](https://github.com/daviraquel)
- ### [Josué Alves](https://github.com/JOSUE-ASV)
- ### [Marcelo Silveira](https://github.com/marcelosj3)
- ### [Marília Calado](https://github.com/marilia-calado)
- ### [Nicholas dos Santos Faria Corrêa](https://github.com/nicholas-dos-santos)
- ### [Rodrigo Abreu](https://github.com/rodrigocezzar)
