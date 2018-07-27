# configuration-repository
A configuration repository, for spring cloud config server

This repository serves a configuration service for different microservices deployed in pivotal cloud foundry.

Steps

1. Open CLI, and run cf create-service p-config-server trial config-server -c {"git": { "uri": "https://github.com/gopikrishhnaChokkalamani/configuration-repository.git", "searchPaths": "configuration/"} }'

2. in the spring boot app, add the below dependencies in pom.xml 
https://docs.pivotal.io/spring-cloud-services/1-2/config-server/

\<dependency><br>
			\<groupId>org.springframework.cloud\</groupId><br>
			\<artifactId>spring-cloud-dependencies\</artifactId><br>
			\<version>Edgware.SR2\</version><br>
			\<type>pom\</type><br>
			\<scope>import\</scope><br>
		\</dependency><br><br>
		\<dependency><br>
			\<groupId>io.pivotal.spring.cloud\</groupId><br>
			\<artifactId>spring-cloud-services-dependencies\</artifactId><br>
			\<version>1.6.3.RELEASE\</version><br>
			\<type>pom\</type><br>
			\<scope>import\</scope><br>
		\</dependency><br><br>
		\<dependency><br>
			\<groupId>org.springframework.boot\</groupId><br>
			\<artifactId>spring-boot-starter-actuator\</artifactId><br>
		\</dependency><br><br>
		\<dependency><br>
			\<groupId>io.pivotal.spring.cloud\</groupId><br>
			\<artifactId>spring-cloud-services-starter-config-client\</artifactId><br>
			\<version>1.6.3.RELEASE\</version><br>
\</dependency><br>

3. in bootstrap.yml, add the below key<br>
security:<br>
  basic:<br>
    enabled: false<br>
    
 
