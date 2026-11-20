# Hi there, I'm Aniket Bhanavase

### Applied AI & Agentic Systems Architect | Open-Source Systems Contributor

I am a Software Engineer and Agentic Systems Architect with **9.4+ years of distributed systems and backend engineering experience**, specializing in taking autonomous AI agents from experimental notebooks into high-throughput, mission-critical enterprise production. I bridge event-driven polyglot microservices (Python, Java 17, GCP) with frontier LLM orchestration to build deterministic, production-grade autonomous systems. Daily driving Arch Linux (**[Omarchy Agentic OS](https://github.com/basecamp/omarchy)**), I also architect native desktop extensions, hardware telemetry controllers, and low-level Linux systems tooling using frontier GenAI (**Google Antigravity & Gemini 3.8 Flash**).

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/aniket-bhanavase0208)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:abhanavase@gmail.com)
[![GitHub Stars](https://img.shields.io/github/stars/Aniket1995?style=flat&logo=github)](https://github.com/Aniket1995)
[![Location](https://img.shields.io/badge/Location-Pune%20%2F%20Hyderabad%2C%20India-blue)](https://maps.google.com)

---

## Native Linux Systems & Hardware Engineering (Agentic GenAI & Omarchy)

> *Daily driving an Arch Linux-based agentic operating system (**[Omarchy](https://github.com/basecamp/omarchy)**), I serve as the **System Architect** directing frontier GenAI agents (**Google Antigravity powered by Gemini 3.8 Flash**) to implement complete, production-grade native desktop plugins and low-level hardware controllers end-to-end. Built on top of the open-source ACPI-WMI kernel driver reverse-engineered by [Jafar Akhondali](https://github.com/JafarAkhondali).*

### 1. [omarchy-predator-turbo](https://github.com/Aniket1995/omarchy-predator-turbo) — Native Omarchy Status Bar Widget & Hardware Turbo Controller
*First-class Omarchy (Quickshell) bar widget & interactive hardware control center for Acer Predator Helios laptops*

- **GenAI-Native Implementation**: Conceived and architecturally directed by Aniket; engineered end-to-end using **Google Antigravity (Gemini 3.8 Flash)** to synthesize reactive QML desktop components, 60fps GPU turbine shader animations, and real-time hardware telemetry polling loops.
- **Architectural Decisions & Systems Design**: Designed the non-blocking state machine, sudoless permission model (`systemd-tmpfiles` / `udev` rules) for `/sys/devices/platform/acer-wmi/turbo_mode` and `/sys/class/hwmon/`, and graceful fallback to read-only monitoring mode.
- **Upstream Driver Attribution**: Built on top of the open-source ACPI-WMI kernel module driver (`facer` / `acer-predator-turbo-and-rgb-keyboard-linux-module`) authored by **[Jafar Akhondali (@JafarAkhondali)](https://github.com/JafarAkhondali)**.
- **Core Tech**: `Google Antigravity (Gemini 3.8 Flash)`, `Linux Kernel (sysfs)`, `udev / tmpfiles.d`, `Quickshell / Qt Quick / QML`, `Hardware Telemetry`.

---

### 2. [omarchy-predator-rgb](https://github.com/Aniket1995/omarchy-predator-rgb) — Native 4-Zone RGB Backlight Control Center
*First-class Omarchy (Quickshell) bar widget & interactive 4-Zone RGB keyboard control center for Acer Predator laptops*

- **GenAI-Native Implementation**: Architecturally specified and implemented end-to-end using **Google Antigravity (Gemini 3.8 Flash)**, synthesizing complex 4-zone interactive keyboard visualizers, dynamic sleep dimming, and byte-level protocol payloads for character device writes.
- **Architectural Decisions & Hardware Controls**: Designed the visual state manager, presets engine, and direct user-session communication with `/dev/acer-gkbbl-0` and `/dev/acer-gkbbl-static-0` character devices supporting all 6 hardware lighting modes (Static, Breathing, Neon Spectrum, Rainbow Wave, Color Shifting, Zoom Pulse).
- **Upstream Driver Attribution**: Built on top of the Linux character device interface exposed by **[Jafar Akhondali's](https://github.com/JafarAkhondali)** open-source DKMS driver.
- **Core Tech**: `Google Antigravity (Gemini 3.8 Flash)`, `Linux Character Devices (/dev)`, `Kernel Module Interface (facer)`, `Quickshell / Qt Quick / QML`, `Hardware Controls`.

---

## Upstream Open-Source Engineering Experience

> *I treat open-source engineering exactly like enterprise production software: analyzing large foreign codebases, resolving root-cause bugs, writing defensive regression test suites, and collaborating with distributed core maintainers.*

### 1. [Google Gemini CLI](https://github.com/google-gemini/gemini-cli) — Terminal Agent UI Reconciler
*Google's flagship open-source terminal interface for Gemini models (108,000+ GitHub Stars)*

- **Problem / Incident**: Diagnosed the root cause of a critical high-priority (P1) session-crashing infinite recursion bug (`RangeError: Maximum call stack size exceeded`) that crashed the Gemini CLI terminal agent during active streaming responses.
- **Engineering Solution**: 
  - Investigated the Ink/React terminal reconciliation cycle and discovered a cyclic re-registration cascade between `ScrollProvider` and child `Scrollable` components triggered by unmemoized registration objects.
  - Re-architected the `ScrollProvider` subscriber registry from React `useState` to a mutable `useRef`, completely decoupling subscription state from the render lifecycle and eliminating cascading $O(N)$ tree re-renders.
  - Stabilized scroll state dependency callbacks using size references (`sizeRef`) to isolate dynamic terminal layout shifts from token streaming events.
- **Testing & Verification**: Authored automated regression test suites in `ScrollProvider.test.tsx` (*"Infinite Loop Prevention"*), ensuring deterministic terminal stability under rapid mounting/unmounting cycles. Engaged with core maintainers on root-cause defensive design.
- **Evidence & Code**:
  - **Root Cause Report**: [Issue #22409](https://github.com/google-gemini/gemini-cli/issues/22409) (*CLI Crash with "Maximum update depth exceeded"*)
  - **Upstream Pull Requests**: [PR #22334](https://github.com/google-gemini/gemini-cli/pull/22334) & [PR #22505](https://github.com/google-gemini/gemini-cli/pull/22505) (*Fix/scroll overflow v2*)
- **Core Tech**: `TypeScript`, `React / Ink CLI Architecture`, `React Reconciler`, `Concurrency`, `Async Token Streaming UX`.

---

### 2. [Archon](https://github.com/coleam00/Archon) — Autonomous AI Coding Agent Harness
*Production-grade autonomous coding agent harness (24,000+ GitHub Stars)*

- **Problem & Scope**: Expanding Archon beyond cloud-only API endpoints to support zero-cloud, privacy-preserving local LLM orchestration and providing real-time observability into the agent's internal reasoning trajectories.
- **Engineering Solutions**:
  - **Local Model Execution**: Integrated offline local inference pipelines using Ollama (LLaMA) and dynamic vector embeddings using `nomic-embed-text` with environment-variable-driven model switching (**Merged [PR #2](https://github.com/coleam00/Archon/pull/2)**).
  - **Model Context Protocol (MCP)**: Extended V3 Model Context Protocol routing to bridge external tools with locally running LLMs.
  - **Thought-Process Telemetry**: Architected a real-time background telemetry daemon and interactive UI widget that captures, polls, and streams the agent's intermediate reasoning steps, tool calls, and documentation lookups ([PR #98](https://github.com/coleam00/Archon/pull/98); commended by founder Cole Medin).
  - **Iteration Enhancements**: Added missing execution handlers to support multi-step iteration stability (**Merged [PR #46](https://github.com/coleam00/Archon/pull/46)**).
- **Evidence & Code**:
  - **Merged PR #2**: [Local Ollama/LLaMA & Vector Embeddings](https://github.com/coleam00/Archon/pull/2) *(Merged by Core Maintainer)*
  - **Merged PR #46**: [Iteration Enhancements](https://github.com/coleam00/Archon/pull/46) *(Merged by Core Maintainer)*
  - **Telemetry PR #98**: [Thought Process Observability Daemon](https://github.com/coleam00/Archon/pull/98) *(Commended by founder Cole Medin)*
- **Core Tech**: `Python`, `Ollama`, `LLaMA`, `Vector Embeddings (nomic-embed-text)`, `Model Context Protocol (MCP)`, `Agent Telemetry`, `AsyncIO`.

---

### 3. [Excalidraw Skill for Coding Agents](https://github.com/coleam00/excalidraw-diagram-skill)
*Deterministic diagramming skill for Claude Code and autonomous agent runtimes*

- **Problem**: AI coding agents frequently rendered overlapping, unreadable architectural schemas due to lack of spatial awareness and bounding calculations prior to SVG/canvas generation.
- **Engineering Solution**: 
  - Authored a proactive Python dimensioning tool bridge (`bounds_tool.py`) enabling LLMs to query exact geometry, text bounds, and container dimensions before generating canvas elements.
  - Implemented mathematical bounding box calculations (`bounds.py`) and hierarchical collision detection algorithms supporting nested parent-child groupings and directional connectors.
- **Evidence & Code**:
  - **Active Pull Request**: [PR #10](https://github.com/coleam00/excalidraw-diagram-skill/pull/10) (*Feat: Deterministic bounds and collision detection*)
- **Core Tech**: `Python`, `Agent Tool Calling`, `Computational Geometry`, `Claude Code Skills`, `Architecture Modeling`.

---

## Developer Frameworks & Architecture Standards

- **[AI-Rules](https://github.com/Aniket1995/AI-Rules)**: Production engineering framework establishing context-window preservation, modularity constraints (`<500 LOC`), and deterministic two-tier planning workflows (`@PLANNING`, `@TASK`) for autonomous AI coding agents.

---

## Technical Competencies Matrix

| Domain | Core Technologies & Architecture Patterns |
| :--- | :--- |
| **AI & Agent Orchestration** | Google Agent Development Kit (Google ADK), Vertex AI Agent Platform, Gemini Skills, Model Context Protocol (MCP), Chrome DevTools MCP, LangGraph State Machines, Local Inference (Ollama/LLaMA), Structured Outputs, RAG, Eval Frameworks |
| **AI-Accelerated Engineering** | Google Antigravity (Gemini 3.8 Flash), Spec-Driven Development (GSD Core), OpenCode + LiteLLM, Claude Opus 5.5 / Sonnet 5.5, Gemini 3, Herdr, Neovim, Hunk Diff |
| **Backend & Distributed Systems** | Java (17/16), Spring Boot, Apache Thrift, Python (AsyncIO, FastAPI, Pydantic), Microservices, Event-Driven Architecture, REST APIs |
| **Linux & Systems Engineering** | Arch Linux (Daily Driver), Omarchy (Agentic OS), Kernel Interfaces (`/sys`, `/dev`, `udev`), Quickshell / Qt Quick / QML, Bash, Concurrency |
| **Cloud, Data & DevOps** | Google Cloud Platform (GCP), AWS, Docker, MongoDB, Redis, PostgreSQL, MySQL, RabbitMQ, Jenkins CI/CD, ELK Stack |

---

## What Engineering Leaders Say

> *"I worked with Aniket and can speak directly to the quality of his work. He builds AI agents from scratch that do real, meaningful work, not demos or proofs of concept. His agent harnesses and the systems he designs around them actually guide agents to complete tasks reliably... Aniket has both strong engineering fundamentals and deep AI expertise. That pairing makes him far more effective at shipping products that work in the real world rather than just in a notebook."*  
> — **Carter Rees, PhD**, VP, AI Engineering at Reputation (May 2026)

---

## Education & Google Cloud Credentials

- **B.Tech. in Computer Science and Engineering** — Walchand College of Engineering, Sangli (2013 – 2017) | GPA: 7.8
- **Deploy Multi-Agent Architectures (Advanced Skill Badge)** — Google Cloud (Credential ID: 25379894)
- **Add Agents to Gemini Enterprise (Challenge Lab)** — Google Cloud (Credential ID: 24469549)
- **Gen AI Agents: Transform Your Organization & Work With Gen AI Apps** — Google Cloud

---

## Connect & Collaborate

- **LinkedIn**: [linkedin.com/in/aniket-bhanavase0208](https://linkedin.com/in/aniket-bhanavase0208)
- **Email**: [abhanavase@gmail.com](mailto:abhanavase@gmail.com)
- **Location**: Pune / Hyderabad, India (Open to Global Remote & Hybrid Senior/Staff Applied AI Roles)
