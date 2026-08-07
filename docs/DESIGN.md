# Design

Audience of this file: a session resuming the design. Floor: knows `writing-checkable-code`; has no transcript of the sessions that derived this.

## Problem

An agent rewriting a standing doc writes from inside its session. Four leaks, one class — the writer's context mistaken for the reader's fact:

1. **Session residue** — the working session's frame carried into the doc.
2. **Anticipatory self-defense** — rationale defending choices instead of stating behavior; over-justification clusters where the writer stops describing and starts arguing.
3. **Implementation dump** — internals, script names, and comment-lore harvested from source files.
4. **Test-fixture specifics** — fixture names, sample inputs, harness structure. Tests are the richest legible statement of behavior, so agents mine them first; but tests are written for maintainers against synthetic data. Test: would the fact survive deletion of the test suite?

Symmetric and larger defect: **omission**. A doc-only reading certifies its own omissions; every reviewer given only the doc missed "cannot get a new machine to a first correct result."

## Structure (mirrors the sibling)

`writing-checkable-code` works because every check runs against an artifact that can contradict it. Docs lacked such artifacts; the skill's job is to declare them:

- **A0 · Audience** — the type declaration. One doc, one audience, stated as *situation + knowledge floor* (a moment, not a demographic). Unwritable → everything below is unverified. Only writable as two → two docs are welded; split before judging sentences.
- **J0 · Jobs** — the interface. What the reader hires the doc for, derived from *audience × system surfaces* (each entry point → an invoke-job, each reachable failure → a diagnose-job, each lifecycle moment → install / first-run / upgrade / removal jobs). Never derived from the doc.
- **Funnel** — the ordering, for the declared audience's path: what is → what for / for whom (incl. the disqualifier) → get → first correct result → daily jobs → change it (pointer) → breaks → limits → leave. First screen strictly ordered; below the fold, findability replaces order (readers arrive mid-task by search). A doc funnel optimizes correct decisions, not conversion: a reader correctly leaving at sentence 2 is a success.
- **Handoffs** — the module boundaries. A funnel stage hired by another reader class (change-it → maintainer) is exactly one sentence + a pointer to that class's doc. Absence = omission (the fork is unfindable); expansion = contamination (the other class's funnel inlined).

## Draft rows

| Row | Contract | Check |
|---|---|---|
| A0 Audience | One doc, one audience: situation + knowledge floor | Write the audience sentence; none → all unverified; two → split first |
| J0 Jobs | Job list derives from audience × surfaces | Fresh agent, given system not doc, lists jobs |
| S1 Selection | Every sentence is hired by a job | Name the job; none → cut (kills all four leaks and truisms by one test) |
| S2 Completeness | Every job answerable from the doc | Per job, find the answering fact; none → omission |
| S3 One home | A fact code/config states is pointed to, not restated | Change it at source; a doc still asserting the old value had a second home |
| S4 Floor | Every fact is above the declared knowledge floor | Substitute a sibling tool into the sentence: still true → below floor, cut |
| O1 Ordering | Funnel order on the first screen; findability below | Stage k answerable without reading past stage k; hand agent stages 1–2, ask "needed for job X?" — wrong answer = broken decide-stage |
| O2 Handoff | Cross-class stages are pointers | Name each stage's hiring class; other class → must be exactly a handoff |
| M1 Modality | Claim strength matches an artifact: *required* means something refuses; *measured* means someone measured; closure ("all X") only where code closes the set | Per must/always/all, name the enforcing artifact; none → downgrade or cut |
| X1 Evidence | Examples executed, commands run, links resolve | Run them, at HEAD |
| X2 Decay | Statement's subject is the current system | Same — executed against HEAD, not remembered |

## Execution model (the part the code sibling doesn't need)

Checks split by executor:

- **Mechanical / near-mechanical:** S3, M1, X1, X2, parts of O1.
- **Judge-agent:** A0, J0, S1, S2, S4. A judge gets the *system*, never the doc under review, and reports findings, not citations — a context-free reader given only the document certifies the document's omissions, and a polluted judge inherits the writer's vantage. The judge's context budget is part of the check's definition.

## Calibration seeds (each failure became a clause)

- **Quarter-cut failure:** a reducer given a word budget and no job list kept the worst parts — pruning without J0 optimizes words, not jobs.
- **2.7× expansion failure:** a rewriter given a preservation checklist and no vantage gate expanded 682 → 1845 words, importing implementation and fixture facts. "Manual stuffed into a README" is the failure mode of preservation without S1.
- **Modality inventions:** an expansion pass upgraded measured facts to required ones — four falsehoods from register alone. Hence M1.
- **Register camouflage (2026-08-06):** three rewrite loops spared four vacuous sentences because they wore the doc's own apodictic voice — the judge matched register, not hire. Hence the S1 register clause and the rework rule: the incumbent's style carries no authority.

## Decisions (2026-08-06)

- **A0/J0 never enter the doc.** A loop wrote them into a README as an HTML comment; the declaration is audit apparatus, and in the doc it is sentences no job hires. It lives in the audit report; in a doc only where the owner explicitly asked.
- **Rework over patch.** Derive the point from the system before reading how the incumbent wrote it; the incumbent is evidence for facts only. The owner is asked one question, only when several irreconcilable points arise.
- **`--audit: complete | deep | light | none`, default `light`.** Scopes claim verification; full execution (X1, clean-machine S2) is `complete` only — full execution cost ~10 min per agent on a one-page README, too rigorous as the unconditional default.
- **L7 — no hard wrap.** Prose is one line per paragraph or list item; wrapping is the renderer's. Every produced doc had imitated word wrap until the owner refused it.

## Prior art (what to compose, not rebuild)

The literature covers the document; nothing covers the writer having the wrong context loaded. Diátaxis owns genre separation (= job classes). Baker (*Every Page Is Page One*) owns non-linear arrival. Williams owns the sentence. Carey et al. (*Developing Quality Technical Information*) is the only published inspection method, but assumes the task list is given. JTBD (Christensen; Ulwick) supplies the selection declaration; applying it as the doc's checkable interface is this skill's contribution, with Pinker's curse of knowledge as the named mechanism behind all four leaks. Sentence-level style: distilled in-repo (`references/style.md`, W1–W8 from Williams; the external delegation dangled on hosts without obra's skill). Drift tools verify only what a doc already mentions — they cannot find absence; S2 exists because of that blindness.

## Open

- Row wording is draft; contracts need the sibling's precision pass.
- Evals: candidate corpus is the kanon README experiment (682-word original, 187-word cut, 1845-word expansion) — three graded failures, one source.
- `references/calibration.md` to be seeded from the failures above.
- Name of the "first correct result" activation check's clean-machine requirement: container vs fresh clone — undecided.
