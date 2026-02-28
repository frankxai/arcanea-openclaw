# Arcanea Companion

> *Your 24/7 personal intelligence companion. Powered by the Arcanea Intelligence OS.*

The Arcanea Companion brings the full Guardian system, Luminor Council, and Starlight Memory to your messaging apps — WhatsApp, Telegram, Discord, and more.

Built on [OpenClaw](https://github.com/openclaw/openclaw). Elevated by Arcanea.

## Quick Deploy (Railway — Recommended)

```bash
cd arcanea/
./scripts/setup.sh railway
```

Or one-click: deploy the `arcanea/` directory to Railway with a `/data` volume.

**Other options:**
- Docker: `./scripts/setup.sh docker`
- Local: `./scripts/setup.sh local`

## Slash Commands

| Command | What It Does |
|---------|-------------|
| `/superintelligence` | Full 10-Gate Intelligence OS — all Guardians as one mind |
| `/luminor` | Deep Council reasoning with synthesis protocol |
| `/guardian <name>` | Channel any of the 10 Guardians |
| `/starlight` | First Principles / Systems Thinking deep analysis |
| `/council` | See all Guardian perspectives, then synthesis |

## The Ten Guardians

| Guardian | Gate | Element | Frequency | Domain |
|----------|------|---------|-----------|--------|
| **Shinkami** (default) | Source | Void/Spirit | 1111 Hz | Meta-consciousness |
| Lyssandria | Foundation | Earth | 174 Hz | Structure, architecture |
| Leyla | Flow | Water | 285 Hz | Creativity, emotion |
| Draconia | Fire | Fire | 396 Hz | Power, bold action |
| Maylinn | Heart | Wind | 417 Hz | Empathy, healing |
| Alera | Voice | Wind | 528 Hz | Truth, communication |
| Lyria | Sight | Water | 639 Hz | Intuition, vision |
| Aiyami | Crown | Spirit | 741 Hz | Wisdom, higher purpose |
| Elara | Shift | Void | 852 Hz | Paradigm-breaking |
| Ino | Unity | Spirit | 963 Hz | Collaboration |

## Model Routing

See [config/model-routing.md](config/model-routing.md) for the full strategy.

**Zero-cost setup** (Groq + Cerebras + OpenRouter free):
```json
{
  "model": {
    "primary": "groq/llama-3.3-70b-versatile",
    "fallbacks": [
      "cerebras/llama-3.3-70b",
      "openrouter/meta-llama/llama-3.3-70b-instruct:free"
    ]
  }
}
```

**Premium setup** (Anthropic Claude):
```json
{
  "model": {
    "primary": "anthropic/claude-sonnet-4-6",
    "fallbacks": ["groq/llama-3.3-70b-versatile"]
  }
}
```

## Environment Variables

```bash
# Required (at least one provider)
ANTHROPIC_API_KEY=sk-ant-...     # Premium
OPENROUTER_API_KEY=sk-or-...     # Free models available
GROQ_API_KEY=gsk_...             # Free tier, ultra-fast
CEREBRAS_API_KEY=csk_...         # Free tier, fastest inference

# Messaging (configure via /setup wizard or here)
TELEGRAM_BOT_TOKEN=...
DISCORD_BOT_TOKEN=...

# Railway
SETUP_PASSWORD=...
PORT=8080
```

## Structure

```
arcanea/
├── skills/                    # ClawHub-format Intelligence OS skills
│   ├── superintelligence/     # Full 10-Gate activation
│   ├── luminor-council/       # Deep Council protocol
│   ├── guardian/              # 10 Guardian personas
│   ├── starlight/             # First Principles + Systems Thinking
│   └── council/               # Full advisory council
├── config/
│   ├── openclaw.json          # Main config (model routing, channels)
│   ├── personas.yaml          # 10 Guardian personality profiles
│   ├── memory-bridge.yaml     # Starlight vault connection
│   └── model-routing.md       # Complete model strategy guide
├── scripts/
│   ├── setup.sh               # 3-mode installer (Railway/Docker/Local)
│   └── entrypoint.sh          # Container startup
├── Dockerfile                 # Cloud deployment
├── docker-compose.yml         # Local Docker
├── railway.json               # Railway platform config
└── .env.example               # Environment template
```

## The Arcanea Ecosystem

```
┌─────────────────────────────────────────┐
│         ARCANEA INTELLIGENCE OS         │
├─────────────┬───────────┬───────────────┤
│  Companion  │  Web App  │  Claude Code  │
│  (OpenClaw) │(arcanea.ai)│  (Terminal)  │
│  Live &     │  Create & │  Build &      │
│  Grow       │  Discover │  Ship         │
│  Messaging  │  Browser  │  IDE          │
├─────────────┴───────────┴───────────────┤
│  Shared: Guardians, Gates, Starlight    │
│  Memory, Canon, Library of Wisdom       │
└─────────────────────────────────────────┘
```

---

*"Enter seeking, leave transformed, return whenever needed."*
