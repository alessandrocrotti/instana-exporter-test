# Instana exporter test

This small project is a POC to test Instana Open Telemetry, sending spans directly to Instana Backoffice, using open telemetry standard modules.

This repository is based on Open Telemetry basic tracker node (https://github.com/open-telemetry/opentelemetry-js/tree/main/examples/basic-tracer-node) changing the exporter from Jeager to Instana.

## How to run it

Install dependencies

```
npm i
```

Since this project needs some environment variable, create a new file `.env` (which is git ignored) with at least this:

```
OTEL_EXPORTER_OTLP_ENDPOINT="https://otlp-blue-saas.instana.io:4317"
# you have to set your instana key manually taking the value from Instana backoffice > ... > Agents > Install Agents > Windows > Instana Agent key
OTEL_EXPORTER_OTLP_HEADERS="x-instana-key=SET_YOUR_KEY_HERE,x-instana-host=otlp-blue-saas.instana.io"
```

Then, you can run it.

```
npm run start
```

## How to change exporter

There are 3 exporters

| Exporter module                          | Protocol   | Endpoint Port |
| ---------------------------------------- | ---------- | ------------- |
| @opentelemetry/exporter-trace-otlp-grpc  | gRPC       | 4317          |
| @opentelemetry/exporter-trace-otlp-proto | http/proto | 4318          |
| @opentelemetry/exporter-trace-otlp-http  | http/json  | 4318          |

If you want to change kind of exporter, uncomment the right module into `index.js` and comment the other two. Update your endpoint with the right port into `.env`
