# Lesson 12 — The frontier: what is being developed

> **Concept map**
> **Builds on** — Lesson 11 (the canon), which ends where this begins; Lesson 9 (evaluation), which is the only tool that survives contact with this material.
> **Connects to** — Lesson 7 (language into data), whose methods this lesson has largely replaced; Lesson 10 (deployment and governance), which is where most of it will actually fail.
> **Leads to** — your own reading, on a schedule. The last section is a routine, not a summary.

## Why this matters

Everything in Lesson 11 is settled enough to teach. Nothing in this lesson is. That is the point of separating them: **a canon and a frontier have to be read with different levels of trust**, and the most common mistake a busy senior person makes is to grant frontier work the credence they have learned to give settled work.

You need this material anyway, for three reasons. It is what every funder, journal editor and ministry counterpart now wants to talk about. It is moving fast enough that a two-year-old mental model is actively misleading. And a surprising amount of it is **evaluated badly in exactly the ways Lesson 9 taught you to spot** — which means your existing skills transfer directly, and are in short supply.

::: How to read the citations in this lesson

Roughly half the important work here is on **arXiv** and has never been peer reviewed. In machine learning this is normal and not in itself a mark against a paper — the field's major results appear at conferences with a preprint months earlier. But it does mean the usual filters are absent. Where a preprint is cited below with no DOI, treat it as a **named lead** whose claims are widely accepted within the field but not independently adjudicated.
:::

## Learning objectives
By the end of this lesson you will be able to:

- **Explain** the transformer-to-LLM chain in five steps, without equations.
- **Distinguish** a capability claim from a benchmark result, and say why the difference matters more here than anywhere else in this course.
- **Appraise** a foundation-model-in-medicine claim using the same questions you already apply to a prediction model.
- **Maintain** a sustainable reading routine that keeps you current in under an hour a month.

## Prerequisites
Lessons 9 and 11.

---

## Section 1 · From transformer to chatbot, in five steps

The whole chain, each step a single idea.

**1 · Attention (2017).** **Vaswani** et al., "Attention is all you need", NeurIPS, 2017. arXiv:1706.03762. A way of letting every position in a sequence attend to every other position, dropping recurrence entirely. Crucially it **parallelises**, which is what made training on enormous corpora economically possible.

**2 · Scale (2020).** **Brown** et al., "Language models are few-shot learners", NeurIPS, 2020. arXiv:2005.14165 — GPT-3. The finding was not a new architecture. It was that the same architecture, made much larger and fed much more text, began doing tasks it had not been trained for, from instructions in the prompt.

**3 · Scaling laws (2020–2022).** **Kaplan** et al., "Scaling laws for neural language models", 2020. arXiv:2001.08361 — performance improves as a smooth power law in compute, data and parameters. Then **Hoffmann** et al., "Training compute-optimal large language models", 2022. arXiv:2203.15556 — the *Chinchilla* result, which corrected the recipe: the big models of that era were substantially under-trained on data for their size. This pair is why the field spent five years buying compute rather than inventing architectures.

**4 · Alignment to instructions (2022).** **Ouyang** et al., "Training language models to follow instructions with human feedback", NeurIPS, 2022. arXiv:2203.02155 — reinforcement learning from human feedback. This is the step that converts a text-completion engine into something that answers your question, and it is the difference between GPT-3, which almost nobody outside the field used, and what arrived in late 2022.

**5 · Foundation models as a category (2021).** **Bommasani** et al., "On the opportunities and risks of foundation models", Stanford CRFM, 2021. arXiv:2108.07258 — the report that named the paradigm: one large model, pre-trained broadly, adapted to many downstream tasks. SKIM the executive summary; it is 200 pages.

✱ Note what this chain implies for your appraisal. A foundation model is **one artefact serving many purposes**, which breaks the assumption underneath every evaluation framework in Lesson 9. TRIPOD+AI asks about *the* intended use, *the* target population, *the* outcome. A model with a hundred intended uses has no such thing, and the field does not yet have an agreed answer to this.

---

## Section 2 · Foundation models arrive in medicine

- **Moor** et al., "Foundation models for generalist medical artificial intelligence", *Nature* 616:259–265, 2023. doi:10.1038/s41586-023-05881-4 — READ. The agenda-setting paper for "generalist medical AI": models that handle multiple modalities and tasks without task-specific training. Read it as a statement of intent rather than of results.
- **Singhal** et al., "Large language models encode clinical knowledge", *Nature* 620:172–180, 2023. doi:10.1038/s41586-023-06291-2 — SKIM. Med-PaLM. Notable as much for its evaluation design — human raters judging answers along multiple axes — as for its scores.
- **Tu** et al., "Towards conversational diagnostic artificial intelligence", *Nature*, 2025. doi:10.1038/s41586-025-08866-7 — already the subject of this course's Lesson 22 deep dive. Read that lesson's appraisal beside the paper.

**What is actually being deployed in health systems right now**, as distinct from what is being published:

| Application | Status | The honest read |
|---|---|---|
| Ambient clinical documentation | Widely deployed, commercially | The clearest near-term win. It automates a task with a human reviewer already in the loop and a low cost of error. |
| Coding and billing support | Deployed | Same shape: reversible, supervised, economically motivated. |
| Retrieval over guidelines and records | Piloting broadly | Depends entirely on retrieval quality, not model quality. |
| Diagnostic reasoning / triage | Research and limited pilots | The claims are strongest and the evaluation weakest. Where your scepticism belongs. |
| Autonomous agents taking clinical actions | Not deployed, much discussed | Treat any claim here as a claim about the future. |

The pattern is worth naming: **adoption is tracking reversibility, not accuracy.** The tasks that have gone furthest are the ones where a human corrects the output as part of the normal workflow.

---

## Section 3 · A frontier epistemics lesson: "emergence"

This is the single best worked example of why your appraisal skills matter here, and it is worth doing carefully.

**The claim.** **Wei** et al., "Emergent abilities of large language models", TMLR, 2022. arXiv:2206.07682 — certain capabilities are absent in smaller models and appear abruptly beyond a scale threshold. Unpredictable, discontinuous, and — the implication most people took — potentially dangerous, since you cannot know what the next model will suddenly be able to do.

**The rebuttal.** **Schaeffer**, Miranda and Koyejo, "Are emergent abilities of large language models a mirage?", NeurIPS, 2023. arXiv:2304.15004 — the discontinuity is substantially an artefact of the **metric**. Use a harsh all-or-nothing metric like exact string match and improvement looks like a sudden jump; use a continuous metric on the same models and the same data and the curve is smooth and predictable.

::: Why this belongs in an epidemiology course

Because it is a measurement-scale artefact, and you have met it before. Dichotomising a continuous variable at a threshold manufactures apparent discontinuities in the outcome; the underlying relationship was smooth all along. Same error, different field.

The general rule this gives you: **when a capability claim depends on a threshold, ask what the metric is before you ask whether the claim is true.** That question would have saved the field two years of argument, and it comes free with your training.
:::

---

## Section 4 · Where the science case is strongest

The sceptical literature is heavy in this lesson, so it is worth being explicit that the strongest counterexamples are very strong.

- **Jumper** et al., "Highly accurate protein structure prediction with AlphaFold", *Nature* 596:583–589, 2021. doi:10.1038/s41586-021-03819-2
- **Abramson** et al., "Accurate structure prediction of biomolecular interactions with AlphaFold 3", *Nature* 630:493–500, 2024. doi:10.1038/s41586-024-07487-w

These are not benchmark wins dressed as science. They solved a fifty-year-old problem, the result is used daily by structural biologists who can check it independently, and the 2024 extension moved from single proteins to interactions. When you are asked whether any of this is real, this is the answer.

Note what these have that clinical AI usually lacks: **a ground truth that exists independently of the model, and a community able to falsify the output.**

---

## Section 5 · The evaluation crisis at the frontier

Everything Lesson 9 taught, made worse.

- **Benchmark contamination.** If a model was trained on most of the public internet, and the benchmark is on the public internet, a high score may mean memorisation. This is not hypothetical and it is difficult to rule out, because the training data is usually undisclosed.
- **Benchmarks measure the wrong thing.** Passing a medical licensing exam is not evidence of clinical competence; the exam was designed to discriminate among humans who had already completed medical training. A model can have the exam-shaped knowledge and none of the substrate.
- **The evaluation is often done by the developer**, on data they chose, with no protocol registered in advance. You would not accept this for a diagnostic test.
- **Holistic evaluation attempts exist.** **Liang** et al., "Holistic evaluation of language models" (HELM), TMLR, 2023. arXiv:2211.09110 — KNOW it exists; it is the most serious attempt to evaluate across many scenarios and metrics rather than reporting a single headline number.

**Your four questions, unchanged from Lesson 9, work perfectly here:**

1. What is the comparator, and is it a real clinician or an absent one?
2. What is the prevalence in the deployment setting, and what does PPV do there?
3. Was the evaluation prospective, and on data from a different source than development?
4. Who is harmed when it is wrong, and how quickly is that detected?

Very few frontier medical AI claims survive all four. That is not cynicism; it is the current state of the evidence base, and saying so is a contribution.

---

## Section 6 · The honest sceptics — and what they get right

Not doom, and not dismissal. These are the arguments that hold up.

- **Narayanan and Kapoor**, *AI Snake Oil*, Princeton University Press, 2024 — READ. The most useful sceptical book, because it makes a distinction most commentary refuses to: **generative AI is genuinely capable and improving; predictive AI applied to social outcomes — recidivism, job performance, which patients will deteriorate — mostly does not work and largely cannot.** For your field, the second half is the relevant one, and their argument is that the limits are about the predictability of the phenomenon, not the quality of the model.
- **Rudin** 2019, doi:10.1038/s42256-019-0048-x — carried forward from Lesson 11, because it applies with more force to a model nobody can inspect at all.
- **Mitchell**, *Artificial Intelligence: A Guide for Thinking Humans*, Farrar Straus and Giroux, 2019 — SKIM. The clearest book-length explanation of what these systems do and do not understand, written before the current hype cycle and holding up well.
- **Christian**, *The Alignment Problem*, W. W. Norton, 2020 — KNOW. The best narrative account of why specifying objectives is the hard part. It is, underneath, the same argument as Obermeyer's cost-versus-illness label.

✱ The connective thread worth carrying: **the frontier's central failure mode is still the label.** Obermeyer's algorithm optimised cost and was sold as health. A language model optimises next-token prediction over human text and is sold as reasoning. In both cases the system does its actual job extremely well. The gap is between the objective and the claim.

---

## Section 7 · A reading routine you will actually keep

Under an hour a month, and it beats any amount of feed-scrolling.

**Monthly — 30 minutes.**
- Skim the tables of contents of *Nature Medicine*, *NEJM AI* and *The Lancet Digital Health*. Titles only; open at most two.
- Read one thing from the SKIM tier of Lesson 11 that you have not read.

**Quarterly — 20 minutes.**
- Read one systematic review or reporting-standards update in your own area rather than a primary AI paper. Reviews are where the frontier becomes appraisable.
- Check whether any WHO or regulatory guidance on AI in health has moved.

**When something is announced loudly — 10 minutes, and this is the highest-value habit.**
1. Find the actual paper or technical report. If there is none, stop; you have learned what you need.
2. Read the evaluation section first. Not the abstract, not the results.
3. Ask the four questions from Section 5.
4. Ask which of the six shapes it is, and whether it was evaluated as that shape or as a different one.

That last question is this course's own contribution and it is remarkably effective. **A claim evaluated as one shape and sold as another** remains the most common failure mode in the field — it is the spine of this whole course, and it applies to a foundation model exactly as it applied to Google Flu Trends.

---

## Section 8 · What would change the picture

Signposts worth watching, stated so you can notice if they happen.

- **Prospective, externally validated, multi-site trials of LLM-based clinical tools with registered protocols.** Currently rare. If these start appearing and reporting positive results, the evidence base changes character.
- **Regulatory frameworks that handle a model with many intended uses.** Nobody has solved this. Whoever does will shape the next decade of deployment.
- **Disclosed training data.** Would make contamination assessable. There is no commercial incentive for it, so watch whether regulation forces it.
- **Predictive AI on social outcomes either improving markedly or being formally abandoned.** Narayanan and Kapoor say it cannot work; that is a falsifiable claim and it will be tested.
- **A high-profile clinical harm traced to a deployed generative system.** It has not happened publicly yet. When it does, the governance conversation in Lesson 10 will move faster than any argument.

## Sources

DOIs on this page are machine-checked against Crossref — see `sources/source-ledger.md`. Preprint and conference citations (Vaswani, Brown, Kaplan, Hoffmann, Ouyang, Bommasani, Wei, Schaeffer, Liang) carry arXiv identifiers instead and are graded **SEARCH**: widely accepted within the field, not independently adjudicated here. Books are cited by publisher and year.

Re-check the DOIs at any time:

```bash
python3 ../../../tools/check_course_dois.py ai-in-public-health
```
