---
name: writing-checkable-docs
description: Use when writing, rewriting or reviewing a README, spec, runbook, CONTRIBUTING, or any standing doc; when asked to "distill this doc", "update the README", "document this", "is this doc good"; when a doc has bloated, gone stale, drifted from the code, or restates what code states; and at end of session when docs are updated to record what changed — before writing the update, not after.
---

# Doc Contracts

A doc has no compiler, so the skill declares the artifacts a check can contradict: an audience sentence (A0) and a job list (J0). A missing declaration is one repository-level finding, reported once after the doc's findings and not among them — never restated per sentence. The mechanical rows run without it; each judge row without its upstream declaration returns unverified, not passed.

Checks split by executor. Mechanical, against the doc and the tree at HEAD: S3, M1, X1, X2's existence half, O1's order half. A judge agent decides the rest — A0, J0, S1, S2, S4, O1's decide half, O2, X2's behavior half — and its context is part of each check: J0 is derived from the system and the A0 sentence with the doc withheld, because a reader given only the doc certifies the doc's omissions; every other judge row then reads the doc against those declarations and the system, carrying nothing of the writing session, because a judge given the writer's vantage inherits it. The judge reports findings, not citations.

Sentence-level style is delegated to obra's `writing-clearly-and-concisely`; these rows judge what a sentence is for, not how it reads.

### A0 · Declaration

**Contract.** One doc, one audience, declared as situation plus knowledge floor — a moment, not a demographic (Pinker, curse of knowledge).

**Check.** A declared sentence — "a reader who ⟨situation⟩, who already knows ⟨floor⟩" — is checked against the doc's content and the system; with none declared, the judge infers one from both, and its inferability is the check. Unwritable is an observation, not taste: two situations demanding different first screens, or no floor one reader holds, is two docs welded — split before judging any sentence, because every judge row decides against exactly one audience. With no sentence writable, every judge row below is unverified, not passed — the repository-level finding, once; the mechanical rows run regardless.

### J0 · Interface

**Contract.** The job list — what the reader hires the doc for (Christensen; Ulwick, jobs to be done) — derives from audience × system surfaces, never from the doc; one doc serves one job class (Diátaxis).

**Check.** The judge, given the system and the A0 sentence with the doc withheld, lists the jobs: each entry point an invoke-job, each reachable failure a diagnose-job, each lifecycle moment an install, first-run, upgrade or removal job. A list read off the doc's headings is void. A derived list spanning two job classes fires, routed to A0's split; a one-class list clears and is the artifact the rows below take. Without A0 the list is underivable and the row is unverified — A0's finding, not a new one.

### S1 · Sentence

**Contract.** Every sentence is hired by a job.

**Check.** The judge, holding the J0 list, the doc and the system, names the job each sentence answers: none names a cut. This one test kills all four leaks — session residue, self-defending rationale, implementation dump, fixture specifics — and truisms with them; a fact that would not survive deletion of the test suite is fixture, not behavior. The one sentence O2 requires is exempt. Without a J0 list the row is unverified — J0's finding, once, not one per sentence.

### S2 · Sentence

**Contract.** Every job is answerable from the doc (Carey et al., *Developing Quality Technical Information*).

**Check.** Per J0 job, the judge finds the answering fact in the doc; none is an omission — drift tools verify only what a doc already mentions, and walking the job list is the only check that finds absence. The first-correct-result job is decided by executing the doc's path on a machine without the writer's state, not by reading; where no such machine is obtainable, that job is unverified, not passed. Without a J0 list the row is unverified — J0's finding.

### S3 · Sentence

**Contract.** A fact code or config states has its one home there; the doc points, never restates.

**Check.** Change the fact at its source: a doc still asserting the old value was a second home. Mechanically, for each literal value, flag, path or default in the doc, name the source owner — restated fires, pointed-to clears. A fact only the doc can state — a decision, the reason for a constraint — has its one home in the doc and is exempt. Without the source search over the tree, the fact is unverified, not single-homed.

### S4 · Sentence

**Contract.** Every fact sits above the declared knowledge floor.

**Check.** Substitute into the sentence a sibling tool the A0 floor says the reader already knows: still true means the sentence is below the floor — it teaches the floor, not the system — and is cut. The judge runs this holding the floor, the doc and the system. Without a declared floor, above and below are undecidable and the row is unverified — A0's finding.

### O1 · Order

**Contract.** The first screen follows the funnel, strictly ordered on the declared audience's path: what is → what for and for whom, disqualifier included → get → first correct result → daily jobs → change it (pointer) → breaks → limits → leave. Below the fold, findability replaces order — readers arrive mid-task by search (Baker, every page is page one).

**Check.** Mechanically, stage k is answerable without reading past stage k — a fact a stage needs sitting in a later one fires, and a first screen mapping to no stage fires as a missing decide-stage. The judge then takes stages 1–2 alone and answers, per J0 job, "is this doc needed for it?": a wrong answer is a broken decide-stage — and a reader correctly leaving at sentence two is a pass, not a miss; the funnel optimizes correct decisions, not conversion. Below the fold, findability: per J0 job, search the doc by the job's own terms — an answering fact unreachable that way fires. Without J0, the decide half and the findability half are unverified — J0's finding; the order half runs regardless.

### O2 · Order

**Contract.** A funnel stage hired by another reader class — change-it, hired by the maintainer — is exactly one sentence plus a pointer to that class's doc.

**Check.** The judge names each stage's hiring class against A0. A stage another class hires that is absent is an omission — the fork is unfindable from here. One that runs past a sentence and a pointer has inlined the other class's funnel — contamination. The row clears only at exactly the handoff shape; a stage with no nameable class is S1's cut, not this row's. Without an A0 sentence the row is unverified — A0's finding.

### M1 · Claim

**Contract.** Claim strength matches an artifact: *required* means something refuses, *measured* means someone measured, closure — "all X", "always", "never" — only where code closes the set.

**Check.** Per must, always, all, never, guaranteed — and per measurement stated as fact: a duration, a count, a size — name the artifact at HEAD: the refusing check, the recorded measurement, the closed set. None names a downgrade or a cut; a register-only upgrade mints falsehoods without touching a fact. A modal inside quoted output or example text asserts nothing of the doc's own and is exempt. The scan is exhaustive over the doc; a claim whose artifact was not sought is unverified, not passed.

### X1 · Evidence

**Contract.** Examples execute, commands run, links resolve — at HEAD.

**Check.** Run every example and command as written, supplying only inputs the doc's own earlier funnel stages say the reader has; fetch every link. Fire where observed output diverges from what the doc shows — a breaks-stage example whose documented output is the error clears when that error reproduces. One the checking environment cannot run is unverified, not passed, and reported so; presented as executed but never run is L1, unconditional.

### X2 · Evidence

**Contract.** Every statement's subject is the current system.

**Check.** Existence is mechanical: for each named unit, path, flag or command, find the referent at HEAD — gone or renamed fires, and a subject that is a former version is L6, unconditional. A behavior claim is decided by X1's run where an example exercises it, and by the judge against the system where none does; decided by neither, it is unverified, not passed.

## Mechanical

Fail the doc on:

- **L1** an example presented as executed that was never executed
- **L2** a closure claim over a set no code closes
- **L3** a test-fixture name, sample input, or harness detail in a user doc
- **L4** a dead link
- **L5** a fact restating a default its source owns
- **L6** a statement whose subject is a former version of the system

## When a verdict is unclear

`references/calibration.md` records, per row, the shape it is drawn to and must not fire on, with the clause that spares it. Read the entry for the row in doubt; each one was a graded failure before it was a clause. A resemblance to a recorded shape never stands in for running the check.

## Keywords

Reach for: Diátaxis genre separation · every page is page one · curse of knowledge · jobs-to-be-done — the reader hires the doc · task orientation · knowledge floor · funnel of correct decisions · disqualifier up front · first correct result · handoff at the class seam · one home for a fact · point, don't restate · modality matches artifact · findability over order below the fold · fixture-deletion test · judge without the doc

Live by: the reader arrives mid-task · a fact you cannot find in time is a fact you do not have · a doc-only reading certifies its own omissions · a reader who correctly leaves is a success · boring reference is healthy reference · tests are written for maintainers, not readers · pruning without jobs optimizes words · the writer's context is not the reader's fact · unverified is not passed

Refuse — NEVER, not even once, not even "temporarily": marketing register ("blazingly", "simply", "just") · anticipatory self-defense · manufactured contrast · restating a source-owned default · fixture names in user docs · closure claims over open sets · narrating the session or the history · "please note" and throat-clearing · expected behavior stated as a feature · examples never executed · a word budget as the pruning criterion · a preservation checklist as a hire
