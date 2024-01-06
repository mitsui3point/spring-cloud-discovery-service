## Eureka Service Discovery
* [spring boot initializer](https://start.spring.io/)
* Eureka Server
  * application.yml
  ```yml
  server:
    port: ....
  
  spring:
    application:
      name: ....
  
  # Eureka Client settings
  # Eureka 서버 자체는 기동하고, 자기 자신의 정보를 다른 마이크로서비스가 Eureka 서버로부터 어떤 정보를 주고 받는 그런 역할을 할 필요가 없기 때문에 register-with-eureka, fetch-registry false
  eureka:
    client:
      register-with-eureka: false # Server 역할하는 자신을 Client 목록으로 등록할지 여부
      fetch-registry: false
  ```
  * Application.java
  ```java
  @SpringBootApplication
  @EnableEurekaServer //Eureka server 를 기동하기 위한 annotation
  public class Application {
  
      public static void main(String[] args) {
          SpringApplication.run(Application.class, args);
      }
  
  }
  ```
  
  