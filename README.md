# mongoose

## Tarefa

> (19) Cadastro de professores
1. 
**Comando**
curl -X POST http://localhost:3000/professor -H "Content-Type: application/json" -d 
"{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": 
\"07494812857\"}"
**Resposta**
{"nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","_id":"68363a98eea4a95a509e459d","__v":0}
2. 
**Comando**
curl -X POST http://localhost:3000/professor -H "Content-Type: application/json" -d 
"{\"nome\": \"Carlos Silva\", \"email\": \"carlos.silva@fatec.sp.gov.br\", \"cpf\": \"  63479695051\"}"
**Resposta**
{"nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","_id":"68363b2ceea4a95a509e459f","__v":0}
3. 
**Comando**
curl -X POST http://localhost:3000/professor -H "Content-Type: application/json" -d 
"{\"nome\": \"Odete Roitman\", \"email\": \"odete.roitman@fatec.sp.gov.br\", \"cpf\": \"
 32082128016\"}"
**Resposta**
{"nome":"Odete Roitman","email":"odete.roitman@fatec.sp.gov.br","cpf":"32082128016","_id":"68363b56eea4a95a509e45a1","__v":0}

> (20) Testando unique no cadastro de professores
**Comando**
curl -X POST http://localhost:3000/professor -H "Content-Type: application/json" -d 
"{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": 
\"07494812857\"}"
**Resposta**
{"message":"CPF ou e-Mail já em uso"}

> (21) Testando a validação de CPF
**Comando**
curl -X POST http://localhost:3000/professor -H "Content-Type: application/json" -d 
"{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec.sp.gov.br\", \"cpf\": 
\"12345678910\"}"
**Resposta**
{"message":"12345678910 não é um CPF válido"}

> (22) Testando a validação do e-mail
**Comando**
curl -X POST http://localhost:3000/professor -H "Content-Type: application/json" -d 
"{\"nome\": \"Henrique Louro\", \"email\": \"henrique.louro@fatec\", \"cpf\": \"12345678910\"}"
**Resposta**
{"message":"henrique.louro@fatec não é um formato de e-mail válido"}

> (23) Listando professores
**Comando**
curl -X GET http://localhost:3000/professor
**Resposta**
[{"_id":"68363a98eea4a95a509e459d","nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},{"_id":"68363b2ceea4a95a509e459f","nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0},{"_id":"68363b56eea4a95a509e45a1","nome":"Odete Roitman","email":"odete.roitman@fatec.sp.gov.br","cpf":"32082128016","__v":0}]

> (24) Update professor
**Comando**
curl -X PUT http://localhost:3000/professor -H "Content-Type: application/json" -d 
"{\"id\":\"68363b56eea4a95a509e45a1\",\"nome\": \"Odetinha Roitman\", \"email\": 
\"odetinha.roitman@fatec.sp.gov.br\", \"cpf\": \" 32082128016\"}"
**Resposta**
{"_id":"68363b56eea4a95a509e45a1","nome":"Odetinha Roitman","email":"odetinha.roitman@fatec.sp.gov.br","cpf":"32082128016","__v":0}

> (25) Deletando professor
**Comando**
curl -X DELETE http://localhost:3000/professor -H "Content-Type: application/json" -d 
"{\"id\":\"68363b56eea4a95a509e45a1\"}"
**Resposta**
{"message":"Professor excluído com sucesso"}

> (26) Listando professores novamente
**Comando**
curl -X GET http://localhost:3000/professor
**Resposta**
[{"_id":"68363a98eea4a95a509e459d","nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},{"_id":"68363b2ceea4a95a509e459f","nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0}]

> (27) Cadastro de disciplinas
1. 
**Comando**
curl -X POST http://localhost:3000/disciplina -H "Content-Type: application/json" -d 
"{\"descricao\": \"Técnicas de Programação II\"}"
**Resposta**
{"descricao":"Técnicas de Programação II","_id":"68364014eea4a95a509e45ac","__v":0}
2. 
**Comando**
curl -X POST http://localhost:3000/disciplina -H "Content-Type: application/json" -d 
"{\"descricao\": \"Lógica de Programação\"}"
**Resposta** 
{"descricao":"Lógica de Programação","_id":"6836402feea4a95a509e45ae","__v":0}

> (28) Listando as disciplinas
**Comando**
curl -X GET http://localhost:3000/disciplina
**Resposta**
[{"_id":"68364014eea4a95a509e45ac","descricao":"Técnicas de Programação II","__v":0},{"_id":"6836402feea4a95a509e45ae","descricao":"Lógica de Programação","__v":0}]

> (29) Associando professores às disciplinas
1. 
**Comando**
curl -X POST http://localhost:3000/professor_has_disciplina -H "Content-Type: 
application/json" -d "{\"professor\": \"68363a98eea4a95a509e459d\", \"disciplina\": 
\"68364014eea4a95a509e45ac\"}"
**Resposta**
{"professor":"68363a98eea4a95a509e459d","disciplina":"68364014eea4a95a509e45ac","_id":"6836413aeea4a95a509e45b4","__v":0}
2. 
**Comando**
curl -X POST http://localhost:3000/professor_has_disciplina -H "Content-Type: 
application/json" -d "{\"professor\": \"68363b2ceea4a95a509e459f\", \"disciplina\": 
\"6836402feea4a95a509e45ae\"}"
**Resposta**
{"professor":"68363b2ceea4a95a509e459f","disciplina":"6836402feea4a95a509e45ae","_id":"68364173eea4a95a509e45b8","__v":0}

> (30) Listando professores e disciplinas
**Comando**
curl -X GET http://localhost:3000/professor_has_disciplina
**Resposta**
[{"_id":"6836413aeea4a95a509e45b4","professor":{"_id":"68363a98eea4a95a509e459d","nome":"Henrique Louro","email":"henrique.louro@fatec.sp.gov.br","cpf":"07494812857","__v":0},"disciplina":{"_id":"68364014eea4a95a509e45ac","descricao":"Técnicas de Programação II","__v":0}},{"_id":"68364173eea4a95a509e45b8","professor":{"_id":"68363b2ceea4a95a509e459f","nome":"Carlos Silva","email":"carlos.silva@fatec.sp.gov.br","cpf":"63479695051","__v":0},"disciplina":{"_id":"6836402feea4a95a509e45ae","descricao":"Lógica de Programação","__v":0}}]
