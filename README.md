# proco-agent-skill

**Drop-in on-chain capital markets tools for LangChain, AutoGen, LlamaIndex, and CrewAI.** A single import gives any framework full Proco capability: non-custodial capital accounts, programmable USDC settlement, treasury controls, and on-chain payment execution.

→ [procohq.com](https://procohq.com)

---

## Status

`Pre-release.` API stable. Production rollout tracked alongside the [Proco SDK](https://github.com/procohq/proco-sdk) and [Proco MCP server](https://github.com/procohq/proco-mcp).

---

## What it provides

One package, four framework integrations, identical capabilities everywhere:

- **LangChain** — Tools registered via `StructuredTool`
- - **CrewAI** — Tasks register Proco actions as available tools
  - - **AutoGen** — Function map exposed via `register_function`
    - - **LlamaIndex** — `FunctionTool` set ready for any system
     
      - Underneath: the same calls hit the Proco SDK, so behaviour is identical across frameworks.
     
      - ---

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

      agent.run("Sweep end-of-day Hyperliquid margin to the Base treasury and log the settlement.")
      ```

      Get an API key at [procohq.com/sign-in](https://procohq.com/sign-in) — free sandbox, no credit card.

      ---

      ## Links

      - [Proco SDK](https://github.com/procohq/proco-sdk) — TypeScript client this skill wraps
      - - [Proco MCP server](https://github.com/procohq/proco-mcp) — same tools as a Model Context Protocol server
        - - [Examples](https://github.com/procohq/examples) — runnable integrations
          - - [Docs](https://procohq.com/docs)
           
            - ---

            ## License

            MIT
