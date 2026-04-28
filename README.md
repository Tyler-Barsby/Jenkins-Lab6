# Jenkins Lab 6 - Webhooks

A public repo used to test Jenkins webhook triggers.

## What it does

- Triggers a Jenkins pipeline automatically on every push to main
- Prints "Hello World" to the build log

## How the webhook works

1. Code is pushed to this repo
2. GitHub sends a POST request to the Jenkins webhook URL
3. Jenkins detects the push and triggers the pipeline automatically

## Webhook setup

GitHub repo → Settings → Webhooks → Add webhook

- Payload URL: `http://<jenkins-ip>:8080/github-webhook/`
- Content type: `application/json`
- Trigger: Just the push event

## Jenkins job setup

- Build trigger: GitHub hook trigger for GITScm polling
- Pipeline: SCM → Git → this repo URL
