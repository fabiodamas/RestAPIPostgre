# RestAPI with Nodejs

A Rest API with Nodejs. The application is based on post: 
> https://developer.okta.com/blog/2019/03/27/build-rest-api-with-node-and-postgres#add-user-authentication-to-your-node-api


### Docker and postgres:
```shell
docker network create --driver bridge postgres-network

docker run --name teste-postgres --network=postgres-network -e "POSTGRES_PASSWORD=123456" -p 5432:5432 -v /home/fabio/Desenvolvimento/PostgreSQL:/var/lib/postgresql/data -d postgres

docker run --name teste-pgadmin --network=postgres-network -p 15432:80 -e "PGADMIN_DEFAULT_EMAIL=fabio.damas@gmail.com" -e "PGADMIN_DEFAULT_PASSWORD=123456" -d dpage/pgadmin4
```


### Endereço pgadmin: 
> http://localhost:15432 


### Create new server on PGADMIN with values below:
Configuração | Valor
------------ | -------------
**host** | teste-postgres
**port** | 5432
**username** | postgres
**senha**| 123456

### URL for test the application
curl -s http://localhost:3000/titles?s=Harry+Potter

curl -sH 'Content-Type: application/json' http://localhost:3000/services
curl -sH 'Content-Type: application/json' http://localhost:3000/services -XPOST -d '{"name":"Netflix"}'
curl -sH 'Content-Type: application/json' http://localhost:3000/services/2 -XDELETE

curl -sH 'Content-Type: application/json' http://localhost:3000/my-titles -XPOST -d '{"serviceId":3,"titleId":"tt0241527","location":"Bookshelf"}'
curl -sH 'Content-Type: application/json' http://localhost:3000/my-titles/2 -XPUT -d '{"location":"Internet"}'
curl -sH 'Content-Type: application/json' http://localhost:3000/my-titles/1 -XDELETE
curl -sH 'Content-Type: application/json' http://localhost:3000/my-titles



### Links reference
* https://medium.com/@renato.groffe/postgresql-pgadmin-4-docker-compose-montando-rapidamente-um-ambiente-para-uso-55a2ab230b89





 







