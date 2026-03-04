# RTP Relational Tech MCP Server

An MCP server that carries relational tech principles, patterns, and the Studio library to any AI builder tool.

> "We are the river — carrying stories, tools, learning, and relationships across many local gardens, while honoring that each garden must be tended by those who live there."

Built by the [Relational Tech Project](https://relationaltechproject.org). Made in the Outer Sunset, for neighborhoods everywhere.

---

## What This Does

When you connect this server to your AI tool (Claude Code, Lovable, Dyad, Cursor, or anything that supports [MCP](https://modelcontextprotocol.io)), it gives your AI access to:

**Knowledge** — RTP's core frameworks embedded directly: relational soil, embedded design methodology, the 1:100 ratio, three-layer neighborhood architecture, builder spectrum, measurement framework (agency, belonging, trust), playbooks, and challenge guides.

**The Studio Library** — Live access to tools, stories, prompts, and community notes from the [Relational Tech Studio](https://studio.relationaltechproject.org), the growing commons where builders share what they're creating.

**Guided Workflows** — Pre-built prompts that walk builders through embedded design, relational soil assessment, personalized action plans, and remixing existing tools for new neighborhoods.

The result: when a builder asks their AI to help design a community tool, the AI doesn't just generate generic software. It guides them through embedded design — asking about their neighborhood, mapping assets, centering relationships, and building the smallest useful thing with (not for) their neighbors.

---

## Quick Start

### Prerequisites

- [Node.js](https://nodejs.org) 18 or newer
- An AI tool that supports MCP (Claude Code, Claude Desktop, Cursor, etc.)

### Install and Run

```bash
# Clone the repo
git clone https://github.com/relationaltechproject/rtp-mcp-server.git
cd rtp-mcp-server

# Install dependencies
npm install

# Build
npm run build

# Run (for testing — normally your AI tool starts it automatically)
npm start
```

### Connect to Claude Code

Add to your `.mcp.json` (in your project root or `~/.claude/.mcp.json` for global access):

```json
{
  "mcpServers": {
    "rtp-relational-tech": {
      "command": "node",
      "args": ["/path/to/rtp-mcp-server/dist/index.js"]
    }
  }
}
```

### Connect to Claude Desktop

Go to Settings → Developer → Edit Config, and add:

```json
{
  "mcpServers": {
    "rtp-relational-tech": {
      "command": "node",
      "args": ["/path/to/rtp-mcp-server/dist/index.js"]
    }
  }
}
```

### Connect to Cursor

Go to Settings → MCP Servers → Add Server:

- Name: `rtp-relational-tech`
- Command: `node /path/to/rtp-mcp-server/dist/index.js`

### Connect to Other Tools

Any tool that supports MCP's stdio transport can connect. The server reads from stdin and writes to stdout using the MCP protocol.

---

## What's Inside

### Resources (Knowledge)

The server embeds RTP's core frameworks as MCP resources that AI tools can read:

| Resource | What It Contains |
|---|---|
| `core-principles` | Technology accountable to people, the river metaphor, relationships first, asset-based approach, speed of trust |
| `relational-tech-practice` | The four dimensions: purpose, process (embedded design), math (1:100), path (scale deep, spread horizontal) |
| `three-layers` | Neighborhood infrastructure layers (relational, information, action) with the Outer Sunset as reference |
| `builder-spectrum` | Five stages of a builder's journey: curious → experimenting → building → sustaining → scaling |
| `measurement-framework` | Measuring what matters: agency, belonging, and trust |
| `embedded-design-guide` | Complete guide to the embedded design methodology |
| `playbooks` | Step-by-step playbooks: communication channels, gatherings, calendars, mutual aid, asset mapping |
| `challenges-guide` | Navigating trust, burnout, scale, access, language barriers, conflict, momentum |
| `network-and-community` | RTP network, adjacent movements, connection patterns for builders |

### Tools (Dynamic Queries)

The server connects to the live Relational Tech Studio library:

| Tool | What It Does |
|---|---|
| `search-studio-library` | Search the full Studio library — tools, stories, prompts, and community notes. Filter by category (relational tech vs. building tech). |
| `get-tool-details` | Look up a specific tool with its linked prompts, community notes, and usage guidance. |
| `find-patterns-by-context` | Describe a builder's situation and get matched to relevant patterns, tools, and guidance from both embedded knowledge and the live library. |

### Prompts (Guided Workflows)

Pre-built interaction patterns that encode RTP's design methodology:

| Prompt | What It Does |
|---|---|
| `design-neighborhood-tool` | Walks through the full embedded design process: understanding place, mapping assets, listening for needs, designing the smallest useful thing. |
| `assess-relational-soil` | Helps a builder understand agency, belonging, and trust in their neighborhood — what exists and where to cultivate more. |
| `create-builder-action-plan` | Generates a personalized action plan in three time horizons: this week, this month, this quarter. |
| `remix-existing-tool` | Guides adapting an existing tool or pattern for a new neighborhood context. |

---

## Architecture

```
RTP Relational Tech MCP Server
├── Resources (embedded knowledge)
│   ├── Core principles & frameworks
│   ├── Embedded design methodology
│   ├── Three-layer neighborhood model
│   ├── Builder spectrum & measurement
│   ├── Playbooks & challenge guides
│   └── Network & community connections
├── Tools (live Studio API)
│   ├── search-studio-library
│   ├── get-tool-details
│   └── find-patterns-by-context
└── Prompts (guided workflows)
    ├── design-neighborhood-tool
    ├── assess-relational-soil
    ├── create-builder-action-plan
    └── remix-existing-tool
```

The server uses **stdio transport** for local connections. Knowledge is embedded directly in the server (core frameworks change slowly), while dynamic content (tools, stories, community notes) is pulled live from the Studio's Supabase API.

---

## For Builders

You don't need to be technical to benefit from this. If you're using an AI tool that supports MCP, connecting this server means your AI partner understands relational tech principles and can draw from the growing commons of tools and stories in the Studio.

Some things you might ask your AI once this is connected:

- "Help me design a community calendar for my neighborhood"
- "I want to start a mutual aid pod on my block — where do I begin?"
- "What relational tech tools exist for connecting neighbors?"
- "I'm feeling burned out from community organizing — what should I do?"
- "Help me remix the Outer Sunset's field guide for my neighborhood"

The AI will ground its responses in RTP's embedded design methodology — asking about your place, your relationships, and your assets before jumping to solutions.

---

## Contributing

This server is part of the relational tech commons. Contributions are welcome:

- **Add patterns**: If you've built something that works in your neighborhood, it could become an embedded resource.
- **Improve prompts**: The guided workflows get better with real builder feedback.
- **Connect new data sources**: Civic commons APIs, local data sources, and other knowledge bases can be integrated as tools.
- **Adapt for new tools**: Help test and document setup for additional AI platforms.

---

## Future Directions

- **Streamable HTTP transport** for remote access (builders connect via URL, no local install)
- **Civic commons API integrations** (Civic Tech Field Guide, Connective Tissue, Join 101, Group Hug)
- **Semantic search** over the knowledge base for better pattern matching
- **Builder profiles** so the server can remember context across sessions
- **Multi-language support** for the embedded knowledge

---

## License

MIT — use freely, remix generously, tend your garden.

---

*Made by the [Relational Tech Project](https://relationaltechproject.org) · [Studio](https://studio.relationaltechproject.org) · hello@relationaltechproject.org*
