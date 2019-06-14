# slim-framework-users-api
API RESTFUL - [Slim Framework](http://www.slimframework.com/) - Users

## Banco de dados
```sql
CREATE DATABASE IF NOT EXISTS `api`;
USE `api`;

CREATE TABLE IF NOT EXISTS `pessoa` (
  `id` int(6) unsigned NOT NULL AUTO_INCREMENT,
  `nome` varchar(30) NOT NULL,
  `email` varchar(50) DEFAULT NULL,
  `dt_cadastro` datetime DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utf8;

INSERT INTO `pessoa` (`id`, `nome`, `email`, `dt_cadastro`) VALUES
	(1, 'Wellington', 'wellington@email.com', NOW()),
	(2, 'João das Coves', 'joao@email.com', NOW());
```

## Requets API
GET All users (Pega todos os usuários)
```cURL
curl -X GET http://localhost/slim-framework-users-api/pessoas/
```
GET User :id (Pega um usuario pelo parâmetro id)
```cURL
curl -X GET http://localhost/slim-framework-users-api/pessoas/1

```
POST User (Insere um novo usuario)
```cURL
curl -X POST http://localhost/slim-framework-users-api/pessoas/
	  -H 'accept: application/json'
	  -H 'content-type: application/json'
	  -d '{"nome":"Maria","email":"maria@email.com"}'

```
PUT User :id (Atualiza um usuário pelo parametro id)
```cURL
curl -X PUT http://localhost/slim-framework-users-api/pessoas/3
	  -H 'accept: application/json'
	  -H 'content-type: application/json'
	  -d '{"nome":"Maria da Silva","email":"maria@email.com"}'

```
DELETE User :id (Remove um usuário pelo parametro id)
```cURL
curl -X DELETE http://localhost/slim-framework-users-api/pessoas/2

```

## Postman 
[Link Collection](https://www.getpostman.com/collections/67d4d7a4856d68b3c29d)

#### [Fonte: clubedosgeeks - tutorial](http://clubedosgeeks.com.br/programacao/php/api-restful-com-php-e-slim-framework)
