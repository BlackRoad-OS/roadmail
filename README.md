<!-- BlackRoad SEO Enhanced -->

# roadmail

> Part of **[BlackRoad OS](https://blackroad.io)** — Sovereign Computing for Everyone

[![BlackRoad OS](https://img.shields.io/badge/BlackRoad-OS-ff1d6c?style=for-the-badge)](https://blackroad.io)
[![BlackRoad OS](https://img.shields.io/badge/Org-BlackRoad-OS-2979ff?style=for-the-badge)](https://github.com/BlackRoad-OS)
[![License](https://img.shields.io/badge/License-Proprietary-f5a623?style=for-the-badge)](LICENSE)

**roadmail** is part of the **BlackRoad OS** ecosystem — a sovereign, distributed operating system built on edge computing, local AI, and mesh networking by **BlackRoad OS, Inc.**

## About BlackRoad OS

BlackRoad OS is a sovereign computing platform that runs AI locally on your own hardware. No cloud dependencies. No API keys. No surveillance. Built by [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc), a Delaware C-Corp founded in 2025.

### Key Features
- **Local AI** — Run LLMs on Raspberry Pi, Hailo-8, and commodity hardware
- **Mesh Networking** — WireGuard VPN, NATS pub/sub, peer-to-peer communication
- **Edge Computing** — 52 TOPS of AI acceleration across a Pi fleet
- **Self-Hosted Everything** — Git, DNS, storage, CI/CD, chat — all sovereign
- **Zero Cloud Dependencies** — Your data stays on your hardware

### The BlackRoad Ecosystem
| Organization | Focus |
|---|---|
| [BlackRoad OS](https://github.com/BlackRoad-OS) | Core platform and applications |
| [BlackRoad OS, Inc.](https://github.com/BlackRoad-OS-Inc) | Corporate and enterprise |
| [BlackRoad AI](https://github.com/BlackRoad-AI) | Artificial intelligence and ML |
| [BlackRoad Hardware](https://github.com/BlackRoad-Hardware) | Edge hardware and IoT |
| [BlackRoad Security](https://github.com/BlackRoad-Security) | Cybersecurity and auditing |
| [BlackRoad Quantum](https://github.com/BlackRoad-Quantum) | Quantum computing research |
| [BlackRoad Agents](https://github.com/BlackRoad-Agents) | Autonomous AI agents |
| [BlackRoad Network](https://github.com/BlackRoad-Network) | Mesh and distributed networking |
| [BlackRoad Education](https://github.com/BlackRoad-Education) | Learning and tutoring platforms |
| [BlackRoad Labs](https://github.com/BlackRoad-Labs) | Research and experiments |
| [BlackRoad Cloud](https://github.com/BlackRoad-Cloud) | Self-hosted cloud infrastructure |
| [BlackRoad Forge](https://github.com/BlackRoad-Forge) | Developer tools and utilities |

### Links
- **Website**: [blackroad.io](https://blackroad.io)
- **Documentation**: [docs.blackroad.io](https://docs.blackroad.io)
- **Chat**: [chat.blackroad.io](https://chat.blackroad.io)
- **Search**: [search.blackroad.io](https://search.blackroad.io)

---


Transactional email service for the BlackRoad ecosystem.

## Features

- **Multi-Provider** - Resend, SendGrid, Mailgun support
- **Templates** - Mustache-style template rendering
- **Queue-based** - Cloudflare Queues for reliable delivery
- **Tracking** - Email status and delivery tracking
- **Webhooks** - Handle bounces and complaints
- **Bulk Sending** - Send to multiple recipients

## Quick Start

```bash
# Install
npm install

# Configure
export RESEND_API_KEY=re_xxx

# Deploy
wrangler deploy
```

## API Endpoints

### Send Email
```bash
POST /send
{
  "to": "user@example.com",
  "subject": "Hello!",
  "html": "<h1>Welcome</h1>"
}
```

### Send with Template
```bash
POST /send/template
{
  "to": "user@example.com",
  "template": "welcome",
  "data": {"name": "John", "company": "Acme"}
}
```

### Bulk Send
```bash
POST /bulk
{
  "emails": [
    {"to": "a@example.com", "subject": "Hi A", "html": "..."},
    {"to": "b@example.com", "subject": "Hi B", "html": "..."}
  ]
}
```

### Check Status
```bash
GET /status/:id
```

### Templates
- `GET /templates` - List templates
- `POST /templates` - Create template
- `GET /templates/:id` - Get template
- `DELETE /templates/:id` - Delete template

## Template Syntax

Use `{{variable}}` for dynamic content:

```html
<h1>Hello {{name}}!</h1>
<p>Welcome to {{company}}</p>
```

## Webhooks

Configure provider webhooks to:
- `POST /webhooks/resend`
- `POST /webhooks/sendgrid`
- `POST /webhooks/mailgun`

## License

Proprietary - BlackRoad OS, Inc.
