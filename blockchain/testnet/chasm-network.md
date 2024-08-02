# Chasm Network

Inference Scout is a tool that runs inference tasks given by Chasm's Orchestrator. It allows you to leverage powerful language models and contribute to Chasm Network.

## Prerequisites

### API Keys

* Obtain a Groq API key from the [Groq Console](https://console.groq.com/keys)
* (Optional) Obtain an Openrouter API key from Openrouter
* Obtain `SCOUT_UID` and `WEBHOOK_API_KEY` from the Chasm Website

### Server Specifications

* 1 vCPU
* 1GB RAM
* 20GB Disk
* Static IP

### Suggested Requirements:

* 2 vCPU
* 4GB RAM
* 50GB SSD
* Static IP

## Obtaining your SCOUT\_UID and WEBHOOK\_API\_KEY

* Go to [https://scout.chasm.net/private-mint](https://scout.chasm.net/private-mint)

<figure><img src="https://docs.node.codecrafters.id/content/images/2024/07/image.png" alt="" height="464" width="1040"><figcaption></figcaption></figure>

* Click `_mint(scout)`
* Log in to the website and retrieve your webhook API key and UID as the first step.

<figure><img src="https://docs.node.codecrafters.id/content/images/2024/07/image-1.png" alt="" height="1250" width="2000"><figcaption></figcaption></figure>

## Software Requirements

1. Install Docker: Follow the [Docker Installation Guide](https://docs.docker.com/engine/install/ubuntu/)
2. Set up the environment file: Use `nano .env` or `vim .env` to create a file with the following content:

```
PORT=3001
LOGGER_LEVEL=debug

# Chasm
ORCHESTRATOR_URL=https://orchestrator.chasm.net
SCOUT_NAME=
SCOUT_UID=
WEBHOOK_API_KEY=
# Scout Webhook Url, update based on your server's IP and Port
# e.g. http://123.123.123.123:3001/
WEBHOOK_URL=

# Chosen Provider (groq, openai)
PROVIDERS=groq
MODEL=gemma2-9b-it
GROQ_API_KEY=

# Optional
OPENROUTER_API_KEY=
OPENAI_API_KEY=
```

💡Do not use single quotes (') or double quotes (") in your .env file, as Docker has issues with them.

#### Setup Guide

\


1. Get Required Credentials from Chasm
2. Prepare the `.env` File (as shown above)
3. Verify Scout Ranking: Check your scout ranking at the [Leaderboard](https://scout.chasm.net/leaderboard). Note: The node status may take up to an hour to update.

Monitor Scout Performance:Copy

```
docker stats scout
```

Restart Docker Container (if needed):Copy

```
docker stop scout
docker rm scout
docker run -d --restart=always --env-file ./.env -p 3001:3001 --name scout johnsonchasm/chasm-scout
```

Test LLM Functionality:Copy

```
source ./.env
curl -X POST \
     -H "Content-Type: application/json" \
     -H "Authorization: Bearer $WEBHOOK_API_KEY" \
     -d '{"body":"{\"model\":\"gemma2-9b-it\",\"messages\":[{\"role\":\"system\",\"content\":\"You are a helpful assistant.\"}]}"}' \
     $WEBHOOK_URL
```

Test Server Response:Copy

```
curl localhost:3001
```

Expected response: `OK`

Verify Server Status:Copy

```
docker logs scout
```

Run the Docker Container:Copy

```
docker run -d --restart=always --env-file ./.env -p 3001:3001 --name scout chasmtech/chasm-scout
```

Pull the Docker Image:Copy

```
docker pull chasmtech/chasm-scout:latest
```

## Troubleshooting

**Environment Variables**

Double-check that all required environment variables are correctly set in the `.env` file.

**Additional Resources**

* **Optimization Guide:** Follow the [optimization guide](https://network-docs.chasm.net/chasm-scout-season-0/competitive-scout-optimization) for performance improvements.
* **Update Guide:** Follow the [update guide](https://network-docs.chasm.net/chasm-scout-season-0/updating-inference-scouts) for updating your scout.

This guide should help you set up and run the Chasm Scout server effectively. For more detailed instructions and troubleshooting, refer to the original repository and additional resources provided.
