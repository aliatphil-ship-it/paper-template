# Paper revision template

A repository set up for revising a journal paper section by section, with Claude revising and Codex (Astra) critiquing, under the rules in `CLAUDE.md`. `AGENTS.md` is a link to `CLAUDE.md`, so both read the same rules. Everything particular to a paper goes in `PAPER.md`; the loop's working state goes in `REVISION-NOTES.md`; the review records go in `review/`.

## Starting a new paper

1. On GitHub, click **Use this template**, then **Create a new repository**. Make it private and name it after the paper.
2. Upload the paper's source file (and its `.bib` file, if any) to `main`.
3. Check that the Claude GitHub app can access the new repository: https://github.com/settings/installations, then Configure next to Claude.
4. At claude.ai/code, start a new session with the new repository and the environment whose setup script installs Codex.
5. First message:
   > Read CLAUDE.md. List the manuscript files and identify the source and commit. Draft PAPER.md from explicit evidence in the paper; mark unknowns and ask me for decisions you cannot infer; do not infer settled positions. Validate the word count. Then do the paper assessment: paper entry, literature map, the main argument and the strongest objection, section order, and word budget, with Codex's independent check. Do not change the manuscript. Show me PAPER.md, the assessment, and the decisions I need to make before committing.
6. Codex: the session checks `codex login status`. If a login is needed, open the link it gives you and enter its code. This is needed at most once per new session.
7. After the plan is agreed, "Go" starts the next task in the recorded order: provisional introduction, body sections, conclusion, final introduction, abstract, then the paper-level passes. "Confirmed" approves the exact revision shown for insertion into the paper, recording, commit, and push to the branch in PAPER.md.

## Environment

Use a cloud environment whose setup script installs the Codex CLI (`npm install -g @openai/codex@0.164.0`). If Codex cannot connect, allow OpenAI's domains (chatgpt.com, auth.openai.com, api.openai.com) under Network access in the environment's settings. Record the tested CLI version and invocation in "Session setup" in `REVISION-NOTES.md`, and test a short read-only review before starting the loop.

## Habits

Open a new session every few sections and after each paper is done, right after a confirmed revision has been pushed. Never work on the same repository in two sessions at once.
