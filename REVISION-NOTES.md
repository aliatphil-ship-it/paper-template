# Revision notes

Working state of the revision loop for [paper title] ([source file]). Every session reads this file and `PAPER.md` before starting and updates this file after each confirmed revision. Line numbers are approximate; search for the quoted text.

## Paper-level plan

None adopted yet. The argument is stated in `PAPER.md`; this section holds the work plan once one is adopted.

### Gates

A gate is passed only by a written argument that answers its question; doing the exercise is not passing it. Unresolved gates stay "unestablished".

None defined yet.

### Say-it-once map

Each repeated item has one home where it is stated in full; elsewhere it is recalled in a clause. Revise the home first; elsewhere, cut to the recall.

None decided yet.

### Length

Limit: [from `PAPER.md`]. Counts by the command in "Session setup".

| Section | [date] | Target |
|---|---:|---:|
| Abstract and keywords | | 200 at most |
| 1 Introduction | | |
| [further sections] | | |
| References | | |
| Total | | [limit] |

## Progress

### Paper entry

The template is in "Revision loop" in `CLAUDE.md`. Write it before the first section enters the loop.

- *Claim:* [the paper's one claim in a sentence, and what the debate leaves open without the paper]
- *Chain:* [one line per section: what it contributes to the claim, its relation to the preceding section, the question it hands on, the later sections that depend on it]
- *Status:* [provisional or verified; open dependencies and when they will be checked]

### Sections

None has entered the loop. Next: [section].

## Pending items

Fix each when its section comes up in the loop, then delete it here.

None yet.

## Session setup

- Word count: [command, for example `pandoc paper.tex -t plain --wrap=none | wc -w`, and what it covers; check that it includes the abstract].
- Codex CLI is installed by the environment's setup script. If `codex --version` fails, install it with `npm install -g @openai/codex@0.164.0`.
- Codex must be logged in each new session: run `codex login --device-auth` and give the author the link and code.
- Codex runs from the repository root, so it reads `AGENTS.md`, which is a link to `CLAUDE.md`. `CLAUDE.md` tells it to read `PAPER.md`.
- Run `codex exec` with `< /dev/null` when it runs in the background; otherwise it waits on stdin and is killed at the time limit. A ChatGPT usage limit stops a run with "You've hit your usage limit" and the reset time; schedule the resume rather than retrying.
