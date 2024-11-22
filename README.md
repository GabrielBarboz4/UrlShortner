# UrlShortner
Projeto desenvolvido com o curso gratuito de Java da Rockseat, onde é realizada a criação de uma função que ira encurtar URL de paginas, codificando e armazenando as requisições dentro de um S3 da AWS.

Esse arquivo corresponde a uma função lambda 'GenerateShortnerUrl' que é responsável por receber as informações de originalUrl e expirationTime, que serão transformadas em um código. Esse código será utilizado por outra função lambda que ira fazer a consulta dos dados dentro do bucket.

Para criar um URL encurtado basta enviar uma requisição para o seguinte link: 

<https://7nkukb0h4c.execute-api.us-east-1.amazonaws.com/create>

repassando o seguinte body:

{
	"originalUrl": "https://test.mywebsite", -- url que será encurtado
	"expirationTime": "1732988188" -- timestemp atual
}

O retorno será o seguinte

{
	"code": "5a2ba963"
}

Este "code" sera utilizado pela função lambda 'RedirectUrlShortenet' para encontrar o objeto no bucket
