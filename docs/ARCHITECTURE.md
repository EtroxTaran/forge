# FORGE — AI Game Development Studio

**Version:** 0.1.0 (Initial Draft)  
**Date:** 2026-02-14  
**Status:** DRAFT  
**Origin:** Fork of Hive v6.0.0 — adapted for game development

---

## 1. Vision

FORGE is an AI-powered game development studio built on the same multi-agent architecture as Hive. While Hive targets web/fullstack applications, FORGE specializes in game development — from indie titles to AAA productions.

**Core Principle:** Same proven orchestration framework. Different agent loadout. Gaming-specific workflows.

---

## 2. What Carries Over from Hive (Unchanged)

These Hive components work identically in FORGE:

| Component | Hive | FORGE | Changes |
|-----------|------|-------|---------|
| N1-COMMAND | Project Manager | Project Manager / Producer | Minimal — gaming terminology |
| N2-PRODUCT | Product Owner | Game Designer | Role rename, gaming focus |
| N7-QA | Quality Assurance | QA + Playtesting | Extended with game-specific testing |
| N8-SECURITY | Security | Security + Anti-Cheat | Extended scope |
| N10-DOCS | Documentation | Documentation + GDD | Game Design Document focus |
| N11-REVIEW | Code Review | Code Review | Unchanged |
| N12-OBSERVER | Team Coach | Team Coach | Unchanged |
| N14-CHAOS | Chaos Engineering | Chaos Engineering | Adapted for game servers |
| N15-ADVOCATE | Devil's Advocate | Devil's Advocate | Unchanged |
| Consensus Engine (G5) | ✅ | ✅ | Unchanged |
| Health Dashboard (G3) | ✅ | ✅ | Unchanged |
| Status Broadcasting (S3) | ✅ | ✅ | Unchanged |
| Knowledge Base (S5) | ✅ | ✅ | Gaming knowledge |
| Self-Evaluation (S6) | ✅ | ✅ | Unchanged |
| Process Transparency (S7) | ✅ | ✅ | Unchanged |
| Sentiment Monitoring (S1) | ✅ | ✅ | Unchanged |

---

## 3. What Changes (Gaming-Specific Agents)

### 3.1 Replaced Agents

| Hive Agent | FORGE Agent | New Role |
|------------|-------------|----------|
| N3-ARCHITECT | **F3-ARCHITECT** | Game Architecture — Engine systems, networking, ECS/component architecture, memory management |
| N4-FRONTEND | **F4-GAMEPLAY** | Gameplay Programming — Player mechanics, AI behavior, UI/UX (UMG/Slate), input systems |
| N5-BACKEND | **F5-ENGINE** | Engine & Systems — C++ core, rendering pipeline, physics, audio systems, optimization |
| N6-FULLSTACK | **F6-PIPELINE** | Build & Asset Pipeline — Unreal Build Tool, asset cooking, CI/CD for games, packaging |
| N9-DEVOPS | **F9-LIVEOPS** | LiveOps & Infrastructure — Game servers, matchmaking, CDN, updates, dedicated servers |
| N13-WORKFLOWS | **F13-AUTOMATION** | Workflow Automation — Build automation, testing pipelines, asset processing workflows |
| N16-ARCHAEOLOGIST | **F16-PORTING** | Porting & Platform — Cross-platform (PC, Console, Mobile), platform-specific optimizations |

### 3.2 New Gaming-Specific Agents

| Agent | Name | Role | Description |
|-------|------|------|-------------|
| **F17-LEVELDESIGN** | Level Designer | Content | Level layout, world building, environment scripting, lighting, Unreal Editor automation |
| **F18-NARRATIVE** | Narrative Designer | Content | Story, dialogue systems, quest design, branching narratives, localization |
| **F19-BALANCE** | Balance Designer | Design | Game economy, progression systems, difficulty curves, multiplayer balancing, telemetry analysis |
| **F20-AUDIO** | Audio Engineer | Content | Sound design, music integration, spatial audio, Wwise/FMOD integration |

### 3.3 Total Agent Roster: 20 Agents

**Command:** F1-COMMAND (Producer)  
**Design:** F2-PRODUCT (Game Designer), F18-NARRATIVE, F19-BALANCE  
**Engineering:** F3-ARCHITECT, F4-GAMEPLAY, F5-ENGINE, F6-PIPELINE  
**Quality:** F7-QA, F8-SECURITY, F11-REVIEW, F14-CHAOS, F15-ADVOCATE  
**Content:** F17-LEVELDESIGN, F20-AUDIO  
**Operations:** F9-LIVEOPS, F12-OBSERVER, F13-AUTOMATION  
**Knowledge:** F10-DOCS, F16-PORTING  

---

## 4. Tech Stack

### 4.1 Primary Engine
- **Unreal Engine 5.5+** (C++, Blueprints)
- Alternative: Godot 4.x (GDScript/C#) for indie projects

### 4.2 Languages
- **C++** (Engine, Performance-critical systems)
- **Blueprints** (Gameplay prototyping, Level scripting)
- **Python** (Build tools, asset processing, automation)
- **TypeScript** (Web dashboards, companion apps, LiveOps tools)

### 4.3 Build & CI
- Unreal Build Tool (UBT)
- Unreal Automation Tool (UAT)
- Jenkins / GitHub Actions for CI/CD
- SteamPipe / Epic Games Store CLI for distribution

### 4.4 Asset Pipeline
- Perforce / Git LFS for large assets
- Unreal Asset Registry
- Substance / Quixel for materials
- Houdini for procedural generation

### 4.5 Backend / LiveOps
- Game Servers: Unreal Dedicated Server / Agones (K8s)
- Matchmaking: Open Match / custom
- Analytics: PlayFab / custom telemetry
- Database: PostgreSQL + Redis (sessions/leaderboards)

### 4.6 AI Agent Infrastructure (from Hive)
- OpenClaw for agent orchestration
- Cursor Agent CLI / Gemini CLI for coding agents
- Discord for agent communication
- Hive MCP for inter-agent messaging

---

## 5. Key Differences: Web vs. Game Development

| Aspect | Hive (Web) | FORGE (Games) |
|--------|-----------|---------------|
| **Iteration Cycle** | Minutes (hot reload) | Minutes to hours (compile + cook) |
| **Testing** | Unit + E2E + API | Unit + Integration + Playtesting + Performance Profiling |
| **Assets** | Minimal (CSS, images) | Massive (3D models, textures, audio, animations) |
| **Build Size** | MBs | GBs to 100+ GBs |
| **Deployment** | CDN + containers | Steam/Epic/Console stores |
| **Performance** | "Fast enough" | Frame-critical (16ms budget @ 60fps) |
| **State** | Stateless (HTTP) | Highly stateful (game world, physics, AI) |
| **Multiplayer** | REST/WebSocket | UDP, prediction, rollback, lag compensation |
| **User Feedback** | Analytics, A/B tests | Playtesting, telemetry, community feedback |
| **Version Control** | Git (small files) | Perforce or Git LFS (large binary assets) |

---

## 6. Workflow: How a Game Gets Built in FORGE

### 6.1 Pre-Production
1. **F1-COMMAND** + **F2-PRODUCT** define game concept, scope, target platforms
2. **F3-ARCHITECT** designs technical architecture (ECS, networking model, plugin structure)
3. **F18-NARRATIVE** drafts story bible, dialogue trees, quest structure
4. **F19-BALANCE** defines core loops, economy, progression

### 6.2 Production
1. **F5-ENGINE** builds core systems (rendering, physics, audio)
2. **F4-GAMEPLAY** implements player mechanics, AI, UI
3. **F17-LEVELDESIGN** builds worlds, scripts events, sets lighting
4. **F20-AUDIO** integrates sound effects, music, spatial audio
5. **F7-QA** continuous testing — automated + playtest sessions
6. **F8-SECURITY** anti-cheat, input validation, server authority
7. **F14-CHAOS** stress testing — what happens with 1000 players? Network dropout? GPU thermal throttle?

### 6.3 Polish & Release
1. **F19-BALANCE** tuning based on playtest data
2. **F6-PIPELINE** final builds, asset cooking, platform packaging
3. **F16-PORTING** platform-specific optimizations (console cert requirements)
4. **F9-LIVEOPS** server infrastructure, matchmaking, day-one patch
5. **F10-DOCS** player-facing docs, developer docs, postmortem

### 6.4 Live Service (Post-Launch)
1. **F9-LIVEOPS** monitors servers, hotfixes, content updates
2. **F19-BALANCE** live balancing based on telemetry
3. **F14-CHAOS** ongoing resilience testing
4. **F7-QA** regression testing for patches

---

## 7. Current AI Limitations for Game Dev

Being honest about what AI agents CAN'T do well (yet):

| Task | AI Capability (2026) | Workaround |
|------|---------------------|------------|
| 3D Modeling | ❌ Limited | Human artists / asset stores / procedural gen |
| Texturing | 🟡 Emerging (AI texture gen) | Substance + AI assist |
| Animation | ❌ Very limited | Motion capture / hand-animated |
| Music Composition | 🟡 Decent (Suno, Udio) | AI-generated + human polish |
| Sound Effects | 🟡 Emerging | Libraries + AI generation |
| Level Art | ❌ Limited | Procedural + human art direction |
| C++ Game Code | ✅ Good | Cursor/Gemini handle C++ well |
| Blueprint Scripting | 🟡 Moderate | Text-based, AI can generate |
| Game Design | ✅ Good | AI excels at systems design |
| Balancing | ✅ Excellent | Data-driven, AI's sweet spot |
| Narrative | ✅ Good | LLMs are strong at dialogue/story |
| QA/Testing | ✅ Good | Automated testing + telemetry |

**Conclusion:** FORGE v1 will be strongest in systems design, code, testing, balancing, and narrative. Visual asset creation remains human-dependent for now.

---

## 8. Supported Game Types (v1)

Ranked by AI agent feasibility:

1. **🟢 Text-heavy / Narrative games** — Visual novels, interactive fiction, RPG dialogue
2. **🟢 Strategy / Management games** — Systems-heavy, minimal art dependency
3. **🟢 Roguelikes / Procedural games** — Procedural generation is AI's strength
4. **🟡 Multiplayer backends** — Server logic, matchmaking, anti-cheat
5. **🟡 2D games** — Simpler asset pipeline, AI art is catching up
6. **🟡 Indie 3D games** — Stylized/low-poly reduces art burden
7. **🔴 AAA 3D games** — Heavy art dependency, large teams needed

---

## 9. Relationship to Hive

FORGE is NOT a replacement for Hive. They coexist:

```
┌─────────────────────────────────────┐
│          Shared Foundation           │
│  (Orchestration, MCP, Dashboard,    │
│   Consensus, Knowledge Base, etc.)  │
├──────────────────┬──────────────────┤
│      HIVE        │      FORGE       │
│   Web/Fullstack  │  Game Dev        │
│   17 Agents      │  20 Agents       │
│   N-prefix       │  F-prefix        │
│   React/Hono     │  Unreal/C++      │
└──────────────────┴──────────────────┘
```

Both share ~60% of their infrastructure. The orchestration layer, monitoring, knowledge management, and quality systems are identical. Only the domain-specific agents differ.

---

## 10. Next Steps

- [ ] Define F-agent SOUL.md files (personality, skills, tools per agent)
- [ ] Set up Unreal Engine project template
- [ ] Configure Perforce or Git LFS for asset management
- [ ] Build first prototype: pick a game type from Section 8 (recommend: Strategy/Roguelike)
- [ ] Adapt Hive MCP endpoints for game-specific events
- [ ] Research Unreal Engine + AI coding agent integration (Cursor with C++ projects)

---

*FORGE — Where AI agents hammer out games.* 🔨
