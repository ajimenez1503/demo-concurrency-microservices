# demo-concurrency-microservices
A demo of microservices

### Run
```
cd forex
./mvnw clean spring-boot:run
```
```
cd currencyconversion
./mvnw clean spring-boot:run
```

### Request
```
curl http://localhost:8000/currency-exchange/from/EUR/to/INR | json_pp 
curl http://localhost:8100/currency-converter/from/EUR/to/INR/quantity/10000 | json_pp 
curl  http://localhost:8100/currency-converter-feign/from/EUR/to/INR/quantity/10000 | json_pp
```
