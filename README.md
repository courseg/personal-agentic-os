# Personal Agentic OS

A six-session guided build of your own file-based agentic OS. You answer questions; the agent creates and maintains the files.

Most people who try to build an AI "second brain" start by designing a folder structure — and end up with forty empty folders they never touch. This does the opposite. It interviews you over six sessions and lets the structure emerge from real material, so what you finish with is something you actually use and can maintain without help.

## What it builds

A small, readable set of markdown files on your own disk:

- `AGENTS.md` — a routing index (under 400 words) telling any agent what to read, and when
- `context/` — how you work, who you deal with, how you write
- `playbooks/` — your first three workflows, each proven by hand before it was written down
- `decisions/`, `journal/`, `learnings.md` — the memory that compounds
- `inbox/` — where raw material lands

Everything is plain markdown. No database, no lock-in — you can read and edit all of it.

## The six sessions

| # | Session | What you leave with | Gate |
|---|---------|--------------------|------|
| 1 | **Scope** | One role named, a boundary and an off-limits list | One role, not three |
| 2 | **Operating** | Your cadence, recurring decisions, key people, artifacts, failure modes | The agent restates your week and you confirm it |
| 3 | **Voice** | How you write — hard rules, a refusal list, sample sentences | 15+ refusals captured, not just preferences |
| 4 | **Harvest** | A folder structure derived from your real files | The tree reflects your material, not a template |
| 5 | **Workflows** | Three playbooks you have already done by hand three times | Each backed by pasted evidence, one run live |
| 6 | **Review loop** | A weekly review ritual, run once | The ritual exists and has been run |

Sessions 2 and 3 spread across sittings. The build writes `BUILD-STATE.md` after every session, so you can stop and resume days later — just say **"continue building my agentic OS."**

## Where it runs

Requires an agent with local file read/write. This repo is a portable Agent Plugins package (`plugin.json` + `skills/`) — install it with your agent's plugin or skill mechanism.

| Surface | What you need |
|---------|--------------|
| **ChatGPT desktop** | Switch the composer to **Work**, then select **Work locally** |
| **Codex** | Open your session from inside the folder you are building in |
| **Claude Code / Cowork** | Add the folder to the workspace |
| **OpenWork** | Create a workspace pointed at your Documents folder |

ChatGPT Work is still rolling out, so it may not be in your account yet — Codex or Claude Code work today.

## Getting started

1. Install this plugin in your agent.
2. Let it create the working folder (`Documents/my-agentic-os`) — or point the agent at a folder you choose.
3. Say: **"Build my personal agentic OS. Interview me."**

Then answer, one question at a time.

## Repo layout

```
plugin.json          # Agent Plugins manifest (com.openai extension)
skills/
  setup/             # onboarding entry point
  personal-agentic-os-setup/
    SKILL.md         # the six-session facilitator
    references/      # one file per session + interview mechanics
    assets/          # AGENTS.md / BUILD-STATE.md templates
assets/              # icon + logo
```

## Design notes

- **The structure is an output, not an input.** Session 4 derives it from your files; a template-shaped result is treated as a failure.
- **Refusals over preferences.** Most of a usable writing identity is what you would never publish.
- **One question at a time.** The agent is instructed not to batch.
- **Nothing is invented.** If you say "you decide," it stops and asks for one real example.

## License

MIT.

---

Built by [George Pratsos](https://github.com/courseg).
