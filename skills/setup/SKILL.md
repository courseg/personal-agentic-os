---
name: personal-agentic-os-setup-onboarding
description: Set up the personal agentic OS build after install. Use when someone has just installed the Personal Agentic OS Setup plugin and wants to begin, or asks how to start building their agentic OS.
---

# Onboarding — personal agentic OS

You are starting a six-session build. Do not summarise the whole method;
run the preflight and get to session 1.

## 1. Create the folder before you ask about it

Do not ask the participant for a path until you know you can write to one.

1. Create `~/Documents/my-agentic-os` (macOS/Linux) or
   `%USERPROFILE%\Documents\my-agentic-os` (Windows). Use
   `mkdir -p` / `New-Item -ItemType Directory -Force`. Creating a folder
   that already exists is not an error.
2. Write `.os-writetest.md` inside it containing `ok — <timestamp>`.
3. Read it back to confirm the write landed.

**If the folder was created and the test file written, continue silently.**
Do not tell them a folder was made. They should never see this step.

## 2. If it fails, decide which failure it is

Two failures look identical to the participant and need different fixes.
Test them in this order.

### 2a. No write access at all

The `mkdir` itself failed, or the write failed with a permissions error.
Say one sentence, matched to the surface:

- **ChatGPT desktop:** "I can't write to your Documents folder yet. Switch
  the composer to **Work locally** — cloud mode can't touch your files —
  then tell me when it's done."
- **ChatGPT on the web or mobile:** "This build needs the desktop app. Open
  ChatGPT on your computer, switch to **Work**, and select **Work locally**."
- **Claude Code / Cowork:** "Add your Documents folder to the workspace and
  tell me when it's done."
- **OpenWork:** "Create a workspace pointed at your Documents folder and
  tell me when it's done."

Then wait. Do not offer a copy-paste workaround. There isn't one.

### 2b. Write access, but the folder isn't the active workspace

The `mkdir` succeeded — the folder exists — but the write landed somewhere
else, or you cannot see files inside it. This is a scoping problem, not a
permission problem, and it is the common one.

Say: "I made the folder, but I'm not working inside it. Point me at it and
we'll continue."

Then give only the matching steps:

- **ChatGPT desktop (Work):** "In the composer, open the folder selector and
  choose `Documents/my-agentic-os`. If it isn't listed, choose **Add
  folder** and pick it."
- **Codex:** "Reopen Codex from inside `Documents/my-agentic-os`, or add it
  as the workspace folder."
- **Claude Code:** "Open a session in `Documents/my-agentic-os`."

### 2c. Never ask them to build the structure

Creating the empty working folder is the only thing they may ever be asked
to do. If they are being asked to make subfolders, rename things, or move
files, that is a bug — do it yourself.

## 3. Confirm, then hand over

Once the write test passes, delete `.os-writetest.md` and ask them to
confirm they saw it. Then open the `personal-agentic-os-setup` skill and
follow it exactly, starting with its preflight.

Sessions span sittings: always check for `BUILD-STATE.md` before starting
anything.

## 4. What not to do

- Do not create the full folder structure up front. Session 4 derives it
  from their real material.
- Do not write their context files for them. If they say "you decide",
  refuse and ask for one real example.
- Do not refer to "Codex" when the participant is in ChatGPT Work, or vice
  versa. Use the wording for the surface you are actually running on.
