# microservices-eureka-client
Central service registry demo project to allow service-discovery

### Try it out

Start the server

```
https://github.com/vicenteneto/microservices-eureka-server
```

Start up a client

```
cd eureka-client
mvn spring-boot:run
```

Visit the client directly at http://localhost:8080/

The `/whoami` endpoint will show the client's self-knowledge of its application name and port

```
{
  "springApplicationName":"eureka-client",
  "serverPort":"8080"
}
```

The `/instances` endpoint will take up to a minute to update, but should eventually
show all the instances of `eureka-client` that have been registered with the
Eureka Discovery Client.

```
[
  {
    "host":"hostname",
    "port":8080,
    "serviceId":"EUREKA-CLIENT",
    "uri":"http://hostname:8080",
    "secure":false
  }
]
```

You can also visit the Eureka dashoboard again now and see it listed there.
