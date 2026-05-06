# proco-agent-skill

**Drop-in financial tools for LangChain, AutoGen, LlamaIndex, and CrewAI.**

A single import gives any agent framework full Proco capability: non-custodial wallets, on-chain payments, programmable conditions, and treasury automation.

→ [procohq.com](https://procohq.com)

---

## Status

`Pre-release.` Scaffolding only. Tracked alongside the [Proco SDK](https://github.com/procohq/proco-sdk) and [Proco MCP server](https://github.com/procohq/proco-mcp).

---

## What it gives an agent framework

One package, four framework integrations, identical capabilities everywhere:

- **LangChain** — Tools registered via `StructuredTool`
- **CrewAI** — Tasks register Proco actions as available tools
- **AutoGen** — Function map exposed via `register_function`
- **LlamaIndex** — `FunctionTool` set ready for any agent

Underneath: the same calls hit the Proco SDK, so behaviour is identical across frameworks.

---

## Quickstart (LangChain example)

```bash
pip install proco-agent-skill
```

```python
from langchain.agents import initialize_agent
from proco_agent_skill.langchain import proco_tools

agent = initialize_agent(
    tools=proco_tools(api_key="sk_..."),
    llm=llm,
    verbose=True,
)

agent.run("Pay invoice INV-204 from the operations wallet when the next vendor payout completes.")
```

Get an API key at [procohq.com/sign-in](https://procohq.com/sign-in) — free sandbox, no credit card.

---

## Links

- [Proco SDK](https://github.com/procohq/proco-sdk) — TypeScript client this skill wraps
- [Proco MCP server](https://github.com/procohq/proco-mcp) — same tools as a Model Context Protocol server
- [Examples](https://github.com/procohq/examples) — runnable agent integrations
- [Docs](https://procohq.com/docs)

---

## License

MIT
