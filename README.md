# registry-service: 
### step1. DI:
#### (1). Eureka Server
`it is an application that holds the information about all client-service applications.`
#### (2). Configuration
```
server.port=8761

eureka.client.register-with-eureka=false
eureka.client.fetch-registry=false
```
#### (3). Added annotation
`@EnableEurekaServer`
```
@SpringBootApplication
@EnableEurekaServer
public class RegistryServiceApplication {

	public static void main(String[] args) {
		SpringApplication.run(RegistryServiceApplication.class, args);
	}

}
```
