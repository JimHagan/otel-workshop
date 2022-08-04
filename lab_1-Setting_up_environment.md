# Lab 1: Setting up your environment

Now that you have a local version of this repository saved on your device after completing the [Getting Started](https://github.com/Bijesse/otel-workshop) requirements, it is time to set up your environment to run the Hipster Shop application. This app consists of 9 microservices that have been instrumented with OpenTelemetry, and 1 microservice that has been instrumented with an APM agent.

## Quick background information on the technologies used in this lab:
* **OpenTelemetry** is an open standard for generating and exporting telemetry from your services to help you analyze your software's performance and behavior. It is a vendor-agnostic observability framework. 
* **Minikube** is a lightweight Kubernetes implementation that creates a virtual machine on your local machine. 
* **Skaffold** is a command line tool that simplifies the development workflow for building, pushing, and deploying your application by organizing common development stages into one command, which we'll use later in this lab. 

## Start Minikube
Run the following terminal command to spin up your local Kubernetes cluster:
```bash
minikube start --memory 8192 --cpus 6
```  

Please note, this application is very resource-heavy. You may need to adjust your [Docker Resource settings](https://docs.docker.com/desktop/mac/) to move forward.

## Check Kubernetes
Check that your cluster is up and running using the following command:
```bash
kubectl get nodes
```

If the deployment was successful, you should see a node called `minikube` in a table, along with some basic information about the cluster.

## Export environment variables 
1. Sign into your [New Relic](https://one.newrelic.com) account
2. Locate your **ingest license** key from your account's [API keys list](https://one.newrelic.com/api-keys), and copy the key. Replace all instances of `<NEWRELIC_INGEST_LICENSE_KEY>` below with this value
3. Run the following commands to export the environment variables below, which configure the generated OpenTelemetry data to be sent to your account. Save these commands in a notes file for later reference

```bash
export OTEL_EXPORTER_OTLP_ENDPOINT=https://otlp.nr-data.net:4317
export OTEL_EXPORTER_OTLP_METRICS_ENDPOINT=https://otlp.nr-data.net:4317
export OTEL_EXPORTER_OTLP_TRACES_ENDPOINT=https://otlp.nr-data.net:4317
export OTEL_EXPORTER_OTLP_HEADERS=api-key=<NEWRELIC_INGEST_LICENSE_KEY>
export NEW_RELIC_API_KEY=<NEWRELIC_INGEST_LICENSE_KEY>
export NEW_RELIC_LICENSE_KEY=<NEWRELIC_INGEST_LICENSE_KEY>
export NEW_RELIC_HOST=collector.newrelic.com
```

## Run Skaffold

*Note: this step can take up to 15 minutes the first time you run this command because Docker has to build and push each of the microservices*

```bash
skaffold dev
```
 
Once all the microservices and load generator are deployed successfully, you will see a constant flow of log messages running in your terminal window. The load generator is generating data from your application, and Skaffold is logging information about the application activity in the terminal. 

You can navigate to [localhost:3000](*) to see a live version of your application **<-- needs updating. this is not true yet**

If any errors occur during deployment, run `skaffold dev` one more time before retracing your steps to see what may have gone wrong.

## View your data in New Relic
1. Navigate to your [New Relic account](https://one.newrelic.com).
2. Locate `Services - OpenTelemetry` under `All entities`.
3. You should see 9 microservices running and receiving data. You should also see a 10th service under `Services - APM`. 


## That's it
Well done! You've set up a local version of Hipster Shop that has been instrumented with both OpenTelemetry and an APM agent. It's now time to move on to lab 2 of the workshop: [Debugging a slow trace](lab_2-Debugging-a-slow-trace.md).
