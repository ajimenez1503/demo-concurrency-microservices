# demo-concurrency-microservices
A demo of microservices

### Run
```shell
cd eureka-naming-server
./mvnw clean spring-boot:run

```

```shell
cd forex
./mvnw clean spring-boot:run
./mvnw clean spring-boot:run -Dspring-boot.run.arguments=--server.port=8000
./mvnw clean spring-boot:run -Dspring-boot.run.arguments=--server.port=8001
```
```shell
cd currencyconversion
./mvnw clean spring-boot:run
```

### Request
```shell
curl http://localhost:8000/currency-exchange/from/EUR/to/INR | json_pp 
curl http://localhost:8001/currency-exchange/from/EUR/to/INR | json_pp 
curl http://localhost:8100/currency-converter/from/EUR/to/INR/quantity/10000 | json_pp 
curl  http://localhost:8100/currency-converter-feign/from/EUR/to/INR/quantity/10000 | json_pp
```
