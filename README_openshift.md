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

Create a service:

```bash
oc apply -f ./openshift/service.yaml
```

Check service details:

```bash
oc describe service discovery-service
```