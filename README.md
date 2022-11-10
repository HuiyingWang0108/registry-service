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
### step2. DI for client-service apllications: department-service, user-service, and other microservice
```
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
</dependency>
```
### step3. Configuration for client-service apllications: department-service, user-service, and other microservice
```
eureka:
  client:
    register-with-eureka: true
    fetch-registry: true
    service-url:
      defaultZone: http://localhost:8761/eureka/
  instance:
    hostname: localhost  
```
