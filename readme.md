# Instana exporter test

This small project is a POC to test Instana Exporter module (https://github.com/instana/nodejs/tree/main/packages/opentelemetry-exporter), sending spans directly to Instana Backoffice.

This repository is based on Open Telemetry basic tracker node (https://github.com/open-telemetry/opentelemetry-js/tree/main/examples/basic-tracer-node) changing the exporter from Jeager to Instana.

## How to run it

Install dependencies

```
npm i
```

Since this project needs some environment variable, create a new file `.env` (which is git ignored) with at least this:

```
INSTANA_ENDPOINT_URL="https://otlp-blue-saas.instana.io:4317"
# you have to set it manually taking the value from Instana backoffice > ... > Agents > Install Agents > Windows > Instana Agent key
INSTANA_AGENT_KEY="SET_YOUR_KEY_HERE"
```

Then, you can run it.

```
npm run start
```
