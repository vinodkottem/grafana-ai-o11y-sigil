# Grafana AI Observability Sigil

This repository contains a minimal Go example for sending OpenAI chat completions and recording the LLM generation metadata to Grafana Cloud AI Observability using the Sigil SDK.

## Sample project

The main sample application is under `sample/`. See `sample/README.md` for the full getting-started guide, environment variable setup, and how to run the example.

## Initial Sigil setup

1. Enable Grafana Cloud AI Observability for your Grafana Cloud stack.
2. Configure the Sigil HTTP export endpoint in `SIGIL_ENDPOINT`.
3. Configure authentication using:
   - `GRAFANA_INSTANCE_ID` for the Grafana instance or tenant ID
   - `GRAFANA_CLOUD_TOKEN` for the Grafana Cloud API token
4. Provide your OpenAI API key in `OPENAI_API_KEY`.
5. The sample app uses the Sigil SDK with OpenTelemetry auto-export to send traces, metrics, and AI generation events.

## Views and dashboard descriptions

The sample is intended to show what you can expect to see in Grafana AI Observability:

- **Generations overview**: aggregated LLM requests, token usage, and model performance
- **Conversation and prompt traces**: link prompts, responses, and generation spans for observability
- **Model usage and cost metrics**: monitor input/output token counts, latency, and model selection
- **Error and stop reason insights**: capture completion stop reasons and API-level failures

See the `sample/img/` folder for example dashboard screenshots and sample views from the Go getting-started project.

## Run the sample

```bash
cd sample
go run .
```

After running, check Grafana Cloud AI Observability and the Sigil dashboards for the recorded generation.
