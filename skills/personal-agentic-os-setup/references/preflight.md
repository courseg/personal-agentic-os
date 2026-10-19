# Preflight

Run once, before session 1. Conversational — this should feel like the
opening of an interview, not a form. Three questions maximum to the user.

## A. File access (silent)

Your first real action is writing BUILD-STATE.md. Do not announce a test.
If the write fails, say ONE sentence matched to the app:

  ChatGPT desktop  "I can't write to your folder yet — switch the composer
                    to 'Work locally' and tell me when you've done it."
  Claude Cowork    "I can't write to your folder yet — add this folder to
                    the workspace and tell me when you've done it."
  Codex            "I'm in the wrong directory. Run me from the folder you
                    want to build in."
  OpenWork         "No workspace yet — create one pointed at this folder."

Then wait. Do not offer a copy-paste workaround; there isn't one that works.

## B. Model tier (infer, don't ask)

Use metadata.default_tier unless you can tell better. Sets three knobs:

  frontier  voice 100 Q · checkpoint every 10 · 15-20 files
  mid       voice 40 Q  · checkpoint every 5  · 12 files · one topic per
            message, never combine
  local     voice 25 Q  · checkpoint every 3  · 10 files · re-read the
            current reference file before each block, assume drift

When unsure, assume lower. Long context on a weak model produces confident
generic answers — worse than short ones, because the user can't tell.

## C. Ask these three, as conversation

1. "What language do you want to work in?"
2. "Would you rather talk or type?"
3. (then go straight into session 1's first question)

Language → conduct everything in it. context/voice.md, all transcripts, and
anything about tone, register or refusals stay in that language. AGENTS.md
routing, folder names and skill frontmatter stay English.

Modality → if typing, load the written-mode pressure tests.

## D. Scheduling (note, don't ask)

Record whether scheduled tasks exist. Session 6 needs a ritual that has run
once; a calendar reminder satisfies it as well as a cron job.
