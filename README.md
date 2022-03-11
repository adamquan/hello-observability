# Hello Observability
Simple [Spring Boot](https://spring.io/guides/gs/spring-boot) application to demonstrate collecting and correlating logs, metrics and traces with [Prometheus](https://prometheus.io/), [OpenTelemetry](https://opentelemetry.io/), and [Grafana Cloud](https://grafana.com/products/cloud/). It is built using [Maven](https://spring.io/guides/gs/maven/). 

Refer to this [documentation](https://docs.google.com/document/d/1uU9BbLH3OrBRLPAOQyQ5W2MeeTup5F2m2x1Qs4QGsnA/edit?usp=sharing) for details.

You can build a jar file and run it from the command line.

```
git clone https://github.com/adamquan/hello-observability.git
cd hello-observability/hello-observability
./mvnw package
java -jar target/*.jar
```

You can then access Hello Observability here: http://localhost:8080/

<img width="1042" alt="hello-observability" src="./images/hello-observability.png">

Or you can run it using Docker:

```
docker build -t hello-observability .
docker run -d -p 8080:8080 --name hello-observability hello-observability
```

## Running everything locally

You can run the whole stack locally inside Docker, after building the application container:

```
cd hello-observability/local
docker-compose up
```

## Sending logs, metrics and traces to Grafana Cloud

You can also run the application locally, together with the Grafana Agent and the load runner, and send logs, metrics and traces to Grafana Cloud. You do need to configure the `cloud/config/agent.yaml` file with your Grafana Cloud information.

```
cd hello-observability/cloud
docker-compose up
```
