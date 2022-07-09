

## registro candidatos ##

Method: POST
Endpoint: BASE_URL/register
body:{dados no formato abaixo, nao equecer de mandar o type, e o “myjobs” como array vazio}
RESPONSE: 201 Created

exemplo:

  "users": [
    {
      
      "id": 1,
      "type": "candidate",
      "created":"08/07/2022",
      "name": "Pedro antonio de jesus",
      "email": "joaozinho@mail.com",
      “site”:”github/pedroantonio
      "password": "$2a$10$YQiiz0ANVwIgpOjYXPxc0O9H2XeX3m8OoY1xk7OGgxTnOJnsZU7FO",
      "imgURL":"https://cdn.pixabay.com/photo/2017/01/31/21/23/avatar-2027366_960_720.png",
      "age": 32,
      "andress":"curitiba, PR",
      "bio":"Estou procurando minha primeira oportunidade",
      "class": "front end",
      “myjobs”:[ 1, 4, 2]
      "skills":[
      {
        "javascript":"javascript",
        "level": 1
      }, {
        "HTML":"HTML",
        "level": 3
      },{
        "CSS":"CSS",
        "level":2
      }, {
        "API":"API",
        "level": 1
      },{
        "HTML":"HTML",
        "level": 3
      },{
        "CSS":"CSS",
        "level":2
      }
]


## registro empresas ##

Method: POST
Endpoint: BASE_URL/register
body:{dados no formato abaixo, nao equecer de mandar o type}
RESPONSE: 201 Created

exemplo:

   users:[
     {
      "id": 2,
      "type": "company",
      "name": "Magazine luiza",
      "bio":"vendas online no varejo",
      "email": "Magazine@mail.com",
      "site":"magazineluiza.com",
      “username”:”joao”
      "function":"recruiter"
      "password":"$2a$10$YQiiz0ANVwIgpOjYXPxc0O9H2XeX3m8OoY1xk7OGgxTnOJnsZU7FO",
      "imgURL":"https://cdn.pixabay.com/photo/2017/01/31/21/23/avatar-2027366_960_720.png",
      
    }
  ]


## login ##

exemplo: 

{
“email”:”joaozinho@gmail.com”,
“senha”:”123456”
}


Method: POST
BASE_URL/login
RESPONSE: 200 OK
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXJAbWFpbC5jb20iLCNDYwOCwic3ViIjoiMyJ9.YVn_gyuu15r_mnEq-QdwbvP1Tc6ayErGxsoqrT2fTPE",
“user”{
retorna o usuario
}


## vagas de emprego ##


Method: GET                                                       Method: PATH                                        Method: POST 
Endpoint: BASE_URL/jobs                                           Endpoint: BASE_URL/jobs/id                          Endpoint: BASE_URL/jobs
precisa de um token bearer                                        precisa de um token bearer                          precisa de um token bearer
RESPONSE 200 OK                                                   RESPONSE 200 OK                                     RESPONSE 201 CREATED
exibe todas as vagas                                              se candidatar em uma vaga                           Body:{ dados no formato abaixo 
                                                                                                                      nao esquecer de mandar o type }
                                                                               Body:  {
                                              
                                                                                                 "candidates":[
                                                                                                           {
                                                                                                           "name":"pedro antonio",
                                                                                                            "id": 1
                                                                                                             }
                                                                                                     ]
                                                                                           }
                                                                                                  
    
 exemplo:
  
  "Jobs": [
    {
      "title": "Desenvolvedor front end”
      "description": “Desenvolvimento de software frontend. Acompanhamento de bugs e softwares para suporte; É desejável o conhecimento/domínio de JavaScript..”,
      “skills”:[“javascript”]
      "level": 1,
      "class": "front end",
      "devs": 2,
      "id": 1
      "userid": 2
      “candidates”:[1, 3, 7]
      “state”:”open”
      “type”: “job”
      
    }

    {
      "title": "Carrinho compras”
      "description": “criar carrinho, salvar produtos, somar preços”,
      “skills”:[“html”, “css”, “javascript”]
      "level": 2,
      "class": "front end",
      "devs": 1,
      "id": 2
      "userid": 2
      “candidates”:[5, 2, 6]
      “state”:”closed”
      “type”: “task”
      
    }
   
  ]
                                                                                                  
                                                                                                  

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.


### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"
