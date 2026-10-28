# Revision notes

Working state of the revision loop for [paper title] ([source file]). Claude reads this file and `PAPER.md` at the start of every session and updates this file after each confirmed revision. Codex reads only the parts its review needs. Line numbers are approximate; search for the quoted text.

## Paper entry

The rules are in "Revision loop" in `CLAUDE.md`. Written in the paper assessment.

- **Claim:** [approved wording from `PAPER.md`, or a proposal marked as such]
- **Problem and contribution:** [what the closest work establishes, what remains unresolved, and what this paper adds]
- **Section chain:** [one line per section: its contribution, its relation to the preceding section, the question it hands on, the later sections that depend on it]
- **Assessment status:** [not assessed, assessed with open issues, or no outstanding blocking findings; link to `review/paper/assessment/`]
- **My approval:** [date and approved version]
- **Open dependencies:** [evidence needed, affected sections, next action]

## Paper-level plan

None adopted yet. Written in the paper assessment: literature map, section order, word budget, and the sequence of work (see "Order of work" in `CLAUDE.md`).

### Gates

A gate records a question that dependent work cannot assume answered, the argument or evidence required to answer it, the affected passages, and its status. It is marked passed only when the recorded evidence meets the stated requirement.

None defined yet.

### Say-it-once map

Each repeated item has one home where it is stated in full; elsewhere it is recalled in a clause. Revise the home first; elsewhere, cut to the recall.

None decided yet.

### Length

Limit: [from `PAPER.md`]. Counts by the validated command in "Session setup".

| Component | Current words | Working budget | Included in journal total? |
|---|---:|---:|---|
| Abstract | | [200 or lower journal limit] | |
| Keywords | | [journal requirement] | |
| Introduction | | | |
| [Body sections] | | | |
| Conclusion, if separate | | | |
| Notes | | | |
| References | | | |
| Other counted material | | | |
| Journal-counted total | | [limit] | Yes |

Available headroom:
Proposed cuts, with locations:
Applied cuts, with versions:

## Progress

None started. Next: the paper assessment.

## Pending items

Give each item an identifier, the affected passages, the next action, and its status. Resolve it when the relevant work is done and keep a link to the resolution. Reopen a confirmed section when a changed premise, definition, source, or conclusion affects it.

None yet.

## Session setup

- **Word count:** [validated command, what it includes and excludes, and the validation date; for LaTeX, for example `pandoc paper.tex -t plain --wrap=none | wc -w`, checking that the abstract is counted]
- **Environment and installation:** the environment's setup script installs the Codex CLI (`npm install -g @openai/codex@0.164.0`); record the tested version and any network access needed.
- **Reviewer model:** `gpt-6-astra`; record the model actually used for every run.
- **Review invocation:** `codex exec -m gpt-6-astra -c 'model_reasoning_effort="high"' --sandbox read-only --output-last-message <file> "<prompt>" < /dev/null`, run from the repository root so that Codex reads `AGENTS.md`.
- **Authentication:** check `codex login status`; if not logged in, run `codex login --device-auth` and give me the link and code.
- **Input:** when the prompt is passed as an argument and stdin is unused, close stdin (`< /dev/null`), or a background run waits and is killed at the time limit. When the prompt comes from a file, supply that file through stdin deliberately.
- **Interrupted runs:** keep completed work and record the next action. A ChatGPT usage limit stops a run with "You've hit your usage limit" and the reset time; schedule the resume rather than retrying, and claim a scheduled resume only when one has actually been set.
