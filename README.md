# Config Server

This is a fully functioning spring cloud config server implementation.

It is designed to divide config up by spring profile so that you can run the same client application and vary the config by the spring profile you choose when running that application. 

You can run this server by running `java -jar config_server.jar`

If started unchanged and once running you can test the server by executing `curl http://localhost:8888/app1/default` The output should be a json object showing 

spring.cloud.config.server.git.uri=https://github.com/paulhopkins11/config_server_sample_config.git
                    
