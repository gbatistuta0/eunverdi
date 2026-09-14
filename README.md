### Hi there 👋

I'm Batuhan. iOS and full-stack engineer. I build products with SwiftUI, React Native, Expo, Next.js, Node.js, TypeScript, PostgreSQL and Prisma, and I build the operating layer that lets coding agents work inside those codebases under explicit constraints.

## How I work with AI

I do not use AI as autocomplete or a chat window. I treat coding agents as untrusted workers inside a governed system.

**Context is part of the system.** Every repository I maintain carries a machine-readable playbook: architecture boundaries, naming, copy rules, forbidden terminology, implementation conventions. Next to it sit architecture decision records and repo-local skills for ORM patterns, API design, security review and coding standards. Nothing is re-explained by hand.

**I build the tool layer, not only consume it.** I have written MCP servers that expose structured capabilities to any agent client: one drives iOS build, simulator, StoreKit 2 and multi-language localization pipelines; another exposes 28 device-level tools (screen hierarchy, tap, type, flow record, failure bundle, PR verdict) over a Go runner. Recorded flows compile once to Maestro YAML and replay with zero model calls, so the thousandth regression run costs the same as the first.

**Multi-agent, multi-provider.** Work is decomposed into bounded units with a single dominant risk, executed in isolated git worktrees so parallel agents cannot contaminate each other. A remote coordinator dispatches to specialised workers from an autonomous kanban. Implementation, review and verification are routed across AI providers by task shape and cost behind a common tool interface, and a change is never reviewed by the model family that wrote it. When a provider degrades or reprices, the routing table changes, not the pipeline.

**Design to production as a closed loop.** A design frame enters as the specification. An agent constrained to the design system implements it, the build renders on a real simulator or device, and the screen is diffed pixel-by-pixel against the frame with a perceptual threshold. A failing diff is a structured report fed straight back to the implementing agent under a fixed iteration budget. A passing diff hands off to a test agent that walks the flow, records it as a replayable regression and posts the verdict as a pull-request check. Production failures re-enter the same loop. Humans sit at approval points, not in the execution path.

**Discipline by hooks, not intentions.** A pre-tool hook budgets context, blocks subagent delegation where a project forbids it, and gates code exploration through a graph index so agents query symbols and call chains instead of reading whole files. Sessions are narrow by rule and reset on written triggers. When the default path is expensive I replace it: screenshot-based UI automation in a hybrid mobile app cost about 10,000 tokens per step; a Chrome DevTools Protocol bridge exposing DOM text brought it to about 300 and removed coordinate guessing.

**Persistent memory across sessions and machines.** A git-backed vault with a fixed topology that humans and agents read through the same router file. Session-start hooks inject identity, the last-session bridge, open threads and binding rules; a session-end hook writes a daily log; an evening job compiles logs into a machine-readable knowledge base. Corrections become rules that every future session loads. Decisions are stored with context, alternatives and outcome so the "why" outlives the code.

**AI output is never evidence.** Work carries a fixed evidence vocabulary (IMPLEMENTED / SIMULATOR VERIFIED / NATIVE VERIFIED / DEFERRED) that only the person who observed the evidence may raise. A fix is proven by reintroducing the regression and watching the test fail. False alarms are logged as incidents with the file and line that disproved them. Build results, runtime behaviour, source inspection and real-device verification are the gates.

## Stack

SwiftUI · Swift Concurrency · React Native · Expo · Next.js · Node.js · TypeScript · Go · PostgreSQL · Prisma · pnpm / Turborepo · MCP · Maestro

📫 [LinkedIn](https://www.linkedin.com/in/ensar-batuhan/)
