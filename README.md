<div align="center">

# Librechat Deployment

[![License](https://img.shields.io/github/license/rudolfjs/librechat-deploy?label=license&style=for-the-badge)](LICENSE)
[![Docker](https://img.shields.io/badge/docker-257bd6?style=for-the-badge&logo=docker&logoColor=white)](https://hub.docker.com/)

</div>

Deployment of local Librechat service on docker.
---

# Installation

This deployment only requires docker to be installed. 

Please see installation instructions [here](https://docs.docker.com/engine/install/).

# Deployment

1. Clone this repository to your local workstation.

2. Review the `docker-compose.yaml` file and `.env`
    * Please see [Librechat documentation](https://www.librechat.ai/docs/configuration) for configuration 
    
3. To deploy the Open WebUI service and the `pipeline`service:

```bash
docker compose up -d
```

Once completed, you can access the web service on `localhost:3080`

# RAG

Use RAG with OpenAI Embedding (default)

1. Add the following to oyur `.env` file:

```env
RAG_API_URL=http://host.docker.internal:8000
```

2. If your OpenAI API key is set to “user_provided,” also add this to your .env file to provide an OpenAI API key:

```env
RAG_OPENAI_API_KEY=sk-your-openai-api-key-example
```

# Configuration

1. Create administrator user
    * The first user you register will be admin
    * This is a local user only, therefore you can use a dummy email (i.e. user@email.com)
    * Password stored locally.