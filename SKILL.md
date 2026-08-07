---
name: writing-checkable-docs
description: Use when writing, rewriting or reviewing a README, spec, runbook, CONTRIBUTING, or any standing doc; when asked to "rework this doc", "distill this doc", "update the README", "document this", "is this doc good"; when a doc has bloated, gone stale, drifted from the code, or restates what code states; and at end of session when docs are updated to record what changed — before writing the update, not after.
---

# Doc Contracts

A doc has no compiler, so each audit derives the artifacts a check can contradict: an audience sentence (A0) and a job list (J0). Both live only in the audit report; they enter a doc only where the owner asked. The mechanical rows run without them; any other row missing its upstream artifact returns unverified, not passed — the finding is the missing artifact's, filed once, not per row. The unit is the standing doc alone; prose that dies with its session — a reply, a commit message, a plan — is not this skill's work.

Checks split by executor. Mechanical, run by the invoking agent against the doc and the tree at HEAD: S3, M1, X1, S2's clean-machine run, X2's existence half, O1's order half. A judge agent decides A0, J0, S1, the rest of S2, S4, the rest of O1, O2, X2's behavior half. Its context is part of each check: J0's derivation is its own agent, doc withheld — A0's judge has read the doc and cannot run it — because a reader given only the doc certifies the doc's omissions; every other judge row reads the doc against those artifacts and the system, carrying nothing of the writing session, because a judge given the writer's vantage judges from that vantage. The judge reports findings, not citations. The cold-read agent runs R1 under the isolation R1's check states, because a reader holding the writer's context cannot stumble where the writer's reader will. A verdict from a breached context — an executor that saw what its row withholds — is void: respawn it fresh, never patch its answer.

Sentence-level style is `references/style.md` — doc-side rows that run at every audit level; the rows here judge what a sentence is for, not how it reads.

## Rework

Asked to write, rewrite or distill, take the rework, not the patch, as the unit of work: derive what the doc is for before reading how the incumbent wrote it. In order: read the system's surfaces; derive A0 and J0 under the executor split above; state the point — the one claim the reader must retain. Where the system supports several irreconcilable points — different docs, not different phrasings — the owner chooses; that is the only question to ask. Then write fresh: the incumbent is evidence for facts and nothing else — a sentence is never spared for wearing the house register, because the register asserts nothing (calibration, S1). Order comes from the funnel (O1); the sentence is written under `references/style.md`; R1's cold read runs after the fresh write, before the report.

An end-of-session doc update is this rework in miniature: derive what the session changed against A0 and J0 before writing the record, not after.

## Audit

`--audit: complete | deep | light | none` scopes how far the doc's claims are verified; at every level, A0, J0 and the point derive from the system's surfaces, and the judge rows and W rows run — the bullets list only claim verification. The default is `light`. R1 follows mode and level: an audit leaves it unverified below `complete` and runs one cold read at `complete`; a rework runs one round below `complete` and the full loop at it. The report names the level that ran, carries A0, J0 and the point, and ranks the findings, each naming its row; a check the level excludes is unverified, not passed.

- `complete` — every check as written: X1 executes and fetches, S2's first-correct-result runs on a clean machine, M1 and X2 hunt every artifact at HEAD.
- `deep` — `light` plus the tree, nothing else executed: S3's source search, M1's artifact naming, X2 entire with behavior decided by reading; X1 and the clean-machine run are unverified.
- `light` — scans only: X2's existence half, L4's links, the doc-side L rows (L3, L7); behavior and artifacts unverified.
- `none` — no claim verification: every fact rides on its source's word — the incumbent's or the session's — and the report says so.

### A0 · Declaration

**Contract.** One doc, one audience, declared as situation plus knowledge floor — a moment, not a demographic (Pinker, curse of knowledge).

**Check.** The owner supplies the sentence — "a reader who ⟨situation⟩, who already knows ⟨floor⟩" — and the judge checks it against the doc and the system; with none supplied, the judge infers one from both, and its inferability is the check. Two situations demanding different first screens, or a floor no single reader holds, is two docs welded — split before judging any sentence, because every judge row decides against exactly one audience.

### J0 · Interface

**Contract.** The job list is what the reader hires the doc for (Christensen; Ulwick); it derives from audience × system surfaces, never from the doc; one doc serves one job class (Diátaxis).

**Check.** The judge lists the jobs from the system and the A0 sentence: each entry point an invoke-job, each reachable failure a diagnose-job, each lifecycle moment an install, first-run, upgrade or removal job. A list read off the doc's headings is void. A derived list spanning two job classes fires, routed to A0's split; a one-class list clears and is the artifact the rows below take.

### S1 · Sentence

**Contract.** Every sentence is hired by a job.

**Check.** The judge holds the J0 list, the doc and the system, and names the job each sentence answers: a sentence with none is cut; a fact that would not survive deletion of the test suite is fixture, not behavior. Each sentence O2 requires is exempt.

### S2 · Sentence

**Contract.** Every job is answerable from the doc (Carey et al.).

**Check.** Per J0 job, the judge finds the answering fact in the doc; none is an omission — drift tools verify only what a doc mentions; only walking the job list finds absence. The first-correct-result job is decided by execution, not reading: the doc's path runs on a clean machine, one without the writer's state; no such machine, and that job is unverified.

### S3 · Sentence

**Contract.** A fact code or config states has its one home there; the doc points, never restates.

**Check.** Change the fact at its source: a doc still asserting the old value was a second home. Per literal value, flag, path or default, name the source owner — restated fires, pointed-to clears. A fact only the doc can state — a decision, the reason for a constraint — has its one home in the doc and is exempt.

### S4 · Sentence

**Contract.** Every fact sits above the declared knowledge floor.

**Check.** Substitute, for the system's name in the sentence, a sibling tool the A0 floor says the reader already knows: still true means the sentence teaches the floor, not the system, and is cut.

### O1 · Order

**Contract.** The first screen follows the funnel, strictly ordered on the declared audience's path: what is → what for and for whom, disqualifier included → get → first correct result → daily jobs → change it (pointer) → breaks → limits → leave. Below the fold, findability replaces order — readers arrive mid-task by search (Baker, every page is page one).

**Check.** Mechanically, stage k is answerable without reading past stage k — a fact a stage needs, found in a later stage, fires, and a first screen where nothing maps to stages 1–2 fires as a missing decide-stage. The judge then takes stages 1–2 alone and answers, per J0 job, "is this doc needed for it?": a wrong answer is a broken decide-stage — and a reader correctly leaving at sentence two is a pass; the funnel optimizes correct decisions, not conversion. Below the fold, findability: per J0 job, search the doc by the job's own terms — an answering fact unreachable that way fires.

### O2 · Order

**Contract.** A funnel stage hired by another reader class — change-it, hired by the maintainer — is exactly one sentence plus a pointer to that class's doc.

**Check.** The judge names each stage's hiring class against A0. A missing stage another class hires is an omission — the fork to that class's doc is unfindable from here. A stage that exceeds a sentence and a pointer has inlined the other class's funnel — contamination. The row clears only at the handoff shape; a stage with no nameable class is S1's cut, not this row's.

### M1 · Claim

**Contract.** Claim strength matches an artifact: *required* means something refuses, *measured* means someone measured, closure — "all X", "always", "never" — only where code closes the set.

**Check.** Per must, always, all, never, guaranteed — and per measurement stated as fact: a duration, a count, a size — name the artifact at HEAD: the refusing check, the recorded measurement, the closed set. No artifact means a downgrade or a cut; a register-only upgrade mints falsehoods without touching a fact. A modal inside quoted output or example text asserts nothing of the doc's own and is exempt. A claim whose artifact was not sought is unverified.

### X1 · Evidence

**Contract.** Examples execute, commands run, links resolve — at HEAD.

**Check.** Run every example and command as written, supplying only inputs earlier funnel stages say the reader has; fetch every link. Fire where observed output diverges from what the doc shows — a breaks-stage example clears when the error it documents as output reproduces. One the environment cannot run is unverified and reported so; one presented as executed but never run is L1, unconditional.

### X2 · Evidence

**Contract.** Every statement's subject is the current system.

**Check.** Existence is mechanical: per named unit, path, flag or command, find the referent at HEAD — gone or renamed fires, and a former-version subject is L6, unconditional. A behavior claim is decided by X1's run where an example exercises it, and by the judge against the system where none does; decided by neither, it is unverified.

### R1 · Reader

**Contract.** First-pass comprehension is measured by a reader, never asserted by the writer — after a fresh write the writer cannot see their own curse of knowledge (Pinker).

**Check.** The cold-read agent reads only the doc — fresh, no session context, the tree forbidden, the tool genre known but not the system — and reports findings, no rewrites, no praise: every stumble, quoted, with one line naming the difficulty — ambiguous referent, two-way parse, metonymy, opaque term; a playback of the doc in the agent's own words, gaps marked where it would be guessing; the three worst sentences, ranked, each with what first-pass comprehension needs. Triage is the writer's, against A0: a stumble the declared audience would share is a defect; a pause on the system's own term at or below the floor is not, and the term stays (W7); a playback misreading outranks any stumble; a playback gap at a deliberate pointer is a pass. In a rework, fix, then repeat with a fresh cold-read agent, within the rounds mode and level grant (Audit); an audit files the stumbles as findings and stops. Three rounds bound the loop: convergence — a round whose three worst land on already-triaged residue — exits earlier; residue standing at the cap enters the report, not another round.

## Mechanical

Fail the doc on:

- **L1** an example presented as executed that was never executed
- **L2** a closure claim over a set no code closes
- **L3** a test-fixture name, sample input, or harness detail in a user doc
- **L4** a dead link
- **L5** a fact restating a default its source owns
- **L6** a statement whose subject is a former version of the system
- **L7** a newline inside a paragraph or list item — the writer wrapping what the renderer wraps; prose is one line per paragraph, at any length

## When a verdict is unclear

`references/calibration.md` records the shapes rows have been mis-drawn to — firing or sparing wrongly — each with the clause that decides it. Read the row's entry where one exists; a row without one is decided by running its check as written. A resemblance to a recorded shape never stands in for running the check.

## Changing the skill

Row wording, level scope and the failure history are the maintainer's; the design and its decisions live in `docs/DESIGN.md`.

## Refuse

NEVER, not even once, not even "temporarily": marketing register ("blazingly", "simply", "just") · anticipatory self-defense · manufactured contrast · restating a source-owned default · fixture names in user docs · closure claims over open sets · narrating the session or the history · "please note" and throat-clearing · expected behavior stated as a feature · examples never executed · a word budget as the pruning criterion · a preservation checklist as a hire · audience or job metadata written into the doc unasked · the incumbent's structure as a template · a sentence spared for its register · a newline inside a paragraph — hard wrap imitating the renderer
