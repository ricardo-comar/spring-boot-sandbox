# spring-boot-sandbox

Simple project to link a couple of embeddable resources (MQ, database, etc) into a spring boot application, activated by maven and spring boot "profile" feature.

Created using Spring Boot 2.1.6, with Maven 3 and [Actuator](http://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-endpoints.html#production-ready-endpoints). 

Also has a sample project with docker-compose to start a local instance of similar resources, to demonstrate de integration of the sample project with them, and the embedded components (when activated by maven "sandbox" profile) providing the same functionality, to enable the sample project run without running the docker instances.   

## Usage
- Add the desired project(s) (spring-boot-sandbox-local-*) to your pom.xml, with scope _runtime_.
- Create on folder _src/test/resources_ a spring profile configuration file (for each component), named _appication-local-*-config.(properties/yaml)_ to specify your desired configurations (described below)   
- TODO: pom.xml with profile

### Local DB - H2
- TODO

### Local API - Wiremock
- TODO

### Local MQ - Kafka
- TODO

### Sample
- Open two consoles 
- On first, run `docker-compose up` to start an ActiveMQ instance
- On secont, start main application with `mvn spring-boot:run`and keep it running. You can test it's API with swagger on _http://localhost:8080/swagger_.
- To enable embedded components, stop and run in sandbox mode by activating the maven profile with `mvn spring-boot:run -P sandbox`
- You can stop the docker instances and check it's still working just fine :)
