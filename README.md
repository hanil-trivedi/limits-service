# limits-service
limits-service is microservice which defines limits and gets its application configurations from ms-"git-localconfig-repo"


1. to connect to the spring-cloud-config-server running on localhost:8888 , 
  i. add the spring-cloud-starter-config in pom
  ii. in the properties file add below ,      
      
      #when using spring-cloud-starter-config in pom, config below to specify how spring-cloud-starter-config needs to connect to spring-cloud-config-server
      so we are importing cloud-config from configserver as below and its running on http://localhost:8888
      put optional so that in case configserver not running, app doesn't fail
                    spring.config.import=optional:configserver:http://localhost:8888
      
      
      #add the name of the properties file which is present at the local GIT repo in configServer so when application starts the limits service will use below name as        id to interact with config server and get the configuration
                    spring.application.name=limits-service
