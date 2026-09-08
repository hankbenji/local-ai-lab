# Local-AI-Lab 

**Private AI infrastructure running on-premise Linux hardware.**

--

Self-hosted model serving, containerized services, and local network
access - no cloud dependencies, no subscriptions, full control.

## Quick Start 

'''bash
git clone https://github.com/hankbenji/local-ai-lab.git
cd local-ai-lab
docker compose up -d
'''

Visit 'http://localhost:3000' for the AI interface.
Visit 'https://localhost:9000' for the infrastructure dashboard. 

# Architecture

local-ai-lab/
├── infrastructure/
│ └── docker-compose.yml Service orchestration
├── projects/
│ └── local-assistant/
│ └── summarizer.sh Local AI text summarizer
└── docs/
└── hardware-specs.md Node specifications


## Services

| Service | Port | Purpose |
|---|---|---|
| Open WebUI | 3000 | Private AI chat interface |
| Portainer | 9000 | Container management dashboard |
| Ollama API | 11434 | Model inference engine |

## Models

| Model | Size | Use Case |
|---|---|---|
| TinyLlama 1.1B | 637MB | Fast lightweight responses |
| Phi3 Mini 3.8B | 2.3GB | Reasoning and analysis |

## Hardware — Node 1

| Component | Spec |
|---|---|
| OS | Zorin OS (Ubuntu 22.04 base) |
| CPU | AMD A8-7410 |
| RAM | 6.7GB |
| Storage | 916GB |

## Stack

- **Containerization:** Docker + Docker Compose
- **AI Engine:** Ollama
- **Interface:** Open WebUI
- **Dashboard:** Portainer
- **Security:** UFW Firewall
- **Languages:** Python, Bash

## Changelog

- Deployed Ollama as persistent systemd service
- Configured `OLLAMA_HOST=0.0.0.0` for network-wide model access
- Containerized Open WebUI and Portainer via Docker Compose
- Hardened system with UFW firewall
- Enabled LAN access across all devices
- Built local AI summarizer tool
