# Paper revision template

A repository set up for revising a journal paper section by section, with Claude revising and Codex (Astra) critiquing, under the rules in `CLAUDE.md`. `AGENTS.md` is a link to `CLAUDE.md`, so both read the same rules. Everything particular to a paper goes in `PAPER.md`; the loop's working state goes in `REVISION-NOTES.md`; the review records go in `review/`.

## Starting a new paper

1. On GitHub, click **Use this template**, then **Create a new repository**. Make it private and name it after the paper.
2. Upload the paper's source file (and its `.bib` file, if any) to `main`.
3. Check that the Claude GitHub app can access the new repository: https://github.com/settings/installations, then Configure next to Claude.
4. At claude.ai/code, start a new session with the new repository and the environment whose setup script installs Codex.
5. First message:
   > Read CLAUDE.md. Fill in PAPER.md from the paper and ask me for anything you cannot infer (journal, limits, reader, settled positions). Then set up the word count, write the paper entry in REVISION-NOTES.md, and run the paper-organization check. Do not change the paper. Show me PAPER.md and the paper entry before committing.
6. When asked, approve the Codex login: open the link the session gives and enter its code. This is needed once in every new session.
7. Run the loop: "Go" for the next section; "Confirmed" to write a revision into the paper and push it.

## Environment

The cloud environment's setup script needs one line: `npm install -g @openai/codex@0.164.0`. If Codex cannot connect, allow OpenAI's domains (chatgpt.com, auth.openai.com, api.openai.com) under Network access in the environment's settings.

## Habits

Open a new session every few sections and after each paper is done, right after a confirmed revision has been pushed. Never work on the same repository in two sessions at once.
