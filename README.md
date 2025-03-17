#Opentelemetry-Jaeger-Zipkin
# springboot-opentelemetry-jaeger
##Jaeger.. 
https://github.com/shashanksdixit/observability/tree/main
https://medium.com/@blackhorseya/deploying-opentelemetry-and-jaeger-with-helm-on-kubernetes-d86cc8ba0332

https://www.infracloud.io/blogs/opentelemetry-auto-instrumentation-jaeger/
# jvm-otel
##Step
docker compose up -d

Access Jaeger UI: localhost:16686
Access Zipkin UI: localhost:9412
Test ms-one trace: curl -X POST -d "{\"customerName\":\"binod\"}" -H "Content-Type: application/json" http://172.29.90.174:8080/customer
Test ms-two trace: curl http://localhost:8080/customer
