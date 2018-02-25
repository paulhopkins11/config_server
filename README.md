# Config Server

This is a fully functioning spring cloud config server implementation.

It is designed to divide config up by spring profile so that you can run the same client application and vary the config by the spring profile you choose when running that application. 

You can build this server but running `mvn package`
You can then run this server by running `java -jar config_server.jar`

Alternatively you can run directly using `mvn spring-boot:run`

If started unchanged and once running you can test the server by executing `curl http://localhost:8888/app1/default` The output should be a json object showing 
```
{
name: "app1",
profiles: [
"default"
],
label: null,
version: "a37a88009e152a3fb94b338887cc4a87dc875460",
state: null,
propertySources: [
{
name: "file:/Users/paul_hopkins/development/config_server_sample_config/default/app1.yml",
source: {
application.info: "default : App 1"
}
},
{
name: "file:/Users/paul_hopkins/development/config_server_sample_config/default/application.yml",
source: {
application.info: "default common"
}
},
{
name: "file:/Users/paul_hopkins/development/config_server_sample_config/application.yml",
source: {
application.info: "ALL common"
}
}
]
}
```

By default this is configured to talk to https://github.com/paulhopkins11/config_server_sample_config

You can change that but starting as `java -jar config_server.jar --spring.cloud.config.server.git.uri=https://github.com/paulhopkins11/config_server_sample_config.git` and choosing an alternative location. You can also specify a local git repo such as `java -jar config_server.jar --spring.cloud.config.server.git.uri=file:~/development/config_server_sample_config`
                    
