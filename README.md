# example-spring-template

My template for initializing Spring Boot application

## Directory structure

Here is the basic skeleton for your app repo that each of the starter templates conforms to:

```bash
├── api-service
│   ├── src
│   │   ├── integration-test
│       ├── main
│       ├── test
│       ├── build.gradle # Define app dependencies here
├── config
├── gradle
│   ├── wrapper
├── helm
├── performance-test
├── docker-compose.yml
├── Dockerfile
├── build.gradle # Define global dependencies here
```

- Your app's source code is nested beneath the `api-service` directory. 
  It composes of submodule for main logic, unit testing, and integration testing. 
  Note that for app-specific dependencies, it is recommended to configure in `build.gradle` within this directory.  

- You can configure coding standards, dependency vulnerability checks in `config` directory. 
  I already provided **checkStyle** with simple Java rules.
  
- For compatibility with Kubernetes, Simple Helm chart is located in `helm` directory.
  However, other Kubernetes dependencies (e.g. `spring-cloud-starter-kubernetes`) is not included within this template. 
  Please kindly add it if necessary.
  
- Your app's performance testing scripts, written in Scala, is nested beneath the `perfomance-test` directory. 
  Please follow the Gatling DSL guideline [here](https://gatling.io/docs/current/).
  
- It is also recommended updating `docker-compose.yml` if your app requires external components, 
  such as database, and message queue to test locally.
  
- The `build.gradle` in root path is used for defining global configuration. In this case, I provided 
  simple SonarQube and Docker build & publish plugins.