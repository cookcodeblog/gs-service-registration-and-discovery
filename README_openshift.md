# Use OpenShift for Load balance and Service discovery

## References

- [Service Discovery and Load Balancing](https://learn.openshift.com/middleware/courses/middleware-spring-boot/microservices-2)
- <https://github.com/spring-guides/gs-service-registration-and-discovery>

## Spring Cloud way (Eureka)


Start Eureka service:

```bash
mvn -f eureka-service spring-boot:run
```

Access Eureka web console:
- <http://localhost:8761>

Start Eureka client:

```bash
mvn -f eureka-client spring-boot:run
```

Check if Eureka client registered in Eureka server via Eureka web console.


# OpenShift (Kubernetes) way

Login to OpenShift and create a new project:

```bash
# Login to OpenShift
oc login

# Create a new project
oc new-project william-spring
```



Use OpenShift S2I build to build eureka-client.

```txt
Git Repository: https://github.com/cookcodeblog/gs-service-registration-and-discovery
Context Dir: /eureka-client
Application Name: eureka-client-app
Name: eureka-client

Choose deployment
Check create service
```

Admin / Network / Service / Pods

Modify deployment, edit Pod count from 1 to 2.

