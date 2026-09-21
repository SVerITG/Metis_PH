# Lesson 11 — The canon: what was essential

> **Concept map**
> **Builds on** — Lesson 1 (the six shapes), which is the frame this reading list hangs on; Lesson 9 (evaluation), which is why half the canon is about failure rather than method.
> **Connects to** — Lesson 12 (the frontier), which is the same list continued into work that is not settled yet.
> **Leads to** — nothing in this course. It leads out of it, deliberately.

## Why this matters

You now have a working frame for AI in public health. What you do not have is the literature underneath it — the papers and books that the field's own practitioners treat as load-bearing, and that get referred to in one clause without explanation because everyone is assumed to have read them.

That gap costs you three specific things. You cannot tell a genuinely new idea from a rebranded old one, which is the single most useful skill when reading a press release. You cannot argue with a modeller on their own ground, because you do not know which of their assumptions the field itself has already litigated. And you miss that **several of the most important arguments in machine learning were made by statisticians, about problems you already understand**, in language you already speak.

✱ This is the good news and it is worth stating plainly. The centre of gravity of this lesson is not deep learning. It is the statistical-learning literature of 1996–2009, most of it published in statistics journals, most of it about the trade-off between prediction and explanation. That is your argument. You have been having it your whole career under different names.

## Learning objectives
By the end of this lesson you will be able to:

- **Locate** any AI claim you meet in the field's own intellectual history, and name what it descends from.
- **Distinguish** the works that must be *read* from the far larger set that need only be *known about*.
- **Explain** Breiman's two cultures, and place your own methodological training inside that split.
- **Recognise** the four canonical failure papers by their arguments, not just their titles.

## Prerequisites
Lessons 1 and 9. No mathematics beyond what you already have.

---

## Section 1 · How to use a canon

A reading list that pretends everything on it should be read cover to cover is a reading list nobody uses. So this one is graded into three tiers, and the tiers matter more than the entries.

| Tier | What it means | How many |
|---|---|---|
| **READ** | Sit down and read it properly. It will change how you appraise papers. | 9 |
| **SKIM** | Read the abstract, the figures and the discussion. Know the argument, not the method. | ~15 |
| **KNOW** | Know it exists, what it claimed, and why people cite it. Never open it. | the rest |

The failure mode here is treating the deep learning papers as READ and the statistics papers as KNOW. For your work it is precisely the other way round.

::: One more framing rule

A canon is not a ranking of importance. It is a **map of arguments that are still being had.** Every entry below earns its place because someone will invoke it at you, in a meeting, as though it settles something — and you should know whether it does.
:::

---

## Section 2 · The founding questions — KNOW, mostly

These are the origin points. You will meet them as rhetorical furniture rather than as method.

- **Turing**, "Computing Machinery and Intelligence", *Mind* 59(236):433–460, 1950. doi:10.1093/mind/LIX.236.433 — The imitation game. Cited constantly, read rarely; worth twenty minutes because Turing anticipates most of the objections still being raised.
- **Shannon**, "A Mathematical Theory of Communication", *Bell System Technical Journal*, 1948. doi:10.1002/j.1538-7305.1948.tb01338.x — Information as a measurable quantity. Everything downstream that talks about entropy, cross-entropy loss or mutual information is standing on this.
- **Rosenblatt**, "The perceptron: a probabilistic model for information storage and organization in the brain", *Psychological Review*, 1958. doi:10.1037/h0042519 — The first learning machine that generated real hype and a real backlash.
- **Samuel**, "Some studies in machine learning using the game of checkers", *IBM Journal of Research and Development*, 1959. doi:10.1147/rd.33.0210 — Where the phrase "machine learning" comes from.
- **Minsky and Papert**, *Perceptrons*, MIT Press, 1969 — KNOW. The book usually blamed for the first AI winter. The blame is somewhat unfair, but the episode matters: **a demonstrated limitation of one architecture defunded a whole research direction for fifteen years.** Field-level overcorrection is a recurring pattern, not a historical curiosity.

---

## Section 3 · The statistical learning core — this is your section

If you read nothing else in this lesson, read this section's first entry.

- **Breiman**, "Statistical Modeling: The Two Cultures", *Statistical Science* 16(3):199–231, 2001. doi:10.1214/ss/1009213726 — READ. The single most useful paper on this list for a senior epidemiologist. Breiman argues that statistics split into a *data modelling* culture, which assumes a stochastic model generated the data and interprets its parameters, and an *algorithmic modelling* culture, which treats the mechanism as unknown and judges only predictive accuracy. He estimates 98% of statisticians in the first camp and thinks that has been a disaster.

  You are, by training, in the first culture. Most of the AI claims you now have to appraise come from the second. The paper is also published *with commentary and a rejoinder* — Cox and Efron both push back — and the exchange is more valuable than the paper alone, because it is the field arguing about exactly the tension you feel when someone shows you an AUC and no coefficients.

- **Breiman**, "Random Forests", *Machine Learning* 45:5–32, 2001. doi:10.1023/A:1010933404324 — SKIM. Still the default strong baseline for tabular data twenty-five years later, which is itself an important fact about the field.
- **Tibshirani**, "Regression shrinkage and selection via the lasso", *JRSS-B*, 1996. doi:10.1111/j.2517-6161.1996.tb02080.x — SKIM. Regularisation as a principled answer to overfitting, in a language you already read.
- **Cortes and Vapnik**, "Support-vector networks", *Machine Learning* 20:273–297, 1995. doi:10.1007/BF00994018 — KNOW.

**The books.** Three, in ascending order of how much time they will cost you:

- **James, Witten, Hastie and Tibshirani**, *An Introduction to Statistical Learning* — READ, and read this one rather than the others. There is a version with R labs. It is the most efficient path from where you are to competent appraisal, and it is free online.
- **Hastie, Tibshirani and Friedman**, *The Elements of Statistical Learning*, 2nd ed., Springer, 2009 — REFERENCE. The mathematical parent of the above. Consult, do not read.
- **Efron and Hastie**, *Computer Age Statistical Inference*, Cambridge University Press, 2016 — READ if the Breiman paper lands. It narrates the whole arc from classical inference to modern prediction, written by two people who lived it, for a reader with exactly your training.

---

## Section 4 · The deep learning breakthrough — SKIM

Know what each one made possible. Do not attempt the mathematics unless you want to.

- **Rumelhart**, Hinton and Williams, "Learning representations by back-propagating errors", *Nature* 323:533–536, 1986. doi:10.1038/323533a0 — How a multi-layer network can be trained at all. The enabling idea.
- **Krizhevsky**, Sutskever and Hinton, "ImageNet classification with deep convolutional neural networks", *Communications of the ACM*, 2017. doi:10.1145/3065386 — the journal republication of the 2012 NeurIPS paper known as **AlexNet**. The result that ended the argument about whether deep networks worked. If you want one date for the modern era, 2012 is it.
- **LeCun**, Bengio and Hinton, "Deep learning", *Nature* 521:436–444, 2015. doi:10.1038/nature14539 — SKIM this as your single technical overview. Written by the three people who won the Turing Award for it, aimed at a general scientific readership.
- **He**, Zhang, Ren and Sun, "Deep residual learning for image recognition", CVPR, 2016. doi:10.1109/CVPR.2016.90 — ResNet. Why networks could suddenly get much deeper.
- **Vaswani** et al., "Attention is all you need", NeurIPS, 2017. arXiv:1706.03762 — The transformer. Everything in Lesson 12 descends from this eight-page paper. KNOW what it did; the architecture details are not your problem.
- **Silver** et al., "Mastering the game of Go with deep neural networks and tree search", *Nature* 529:484–489, 2016. doi:10.1038/nature16961 — KNOW.
- **Jumper** et al., "Highly accurate protein structure prediction with AlphaFold", *Nature* 596:583–589, 2021. doi:10.1038/s41586-021-03819-2 — READ the discussion, at least. The strongest existing case that these methods can produce genuine scientific advance rather than benchmark performance. Keep it in mind as the counterweight whenever the sceptical literature below starts to feel total.

**Goodfellow, Bengio and Courville**, *Deep Learning*, MIT Press, 2016 — REFERENCE, free online. The standard textbook. You will not read it and you do not need to.

---

## Section 5 · The reckoning — READ two of these

The most useful literature in machine learning is about how it fails. Four arguments, each of which you will need.

- **Sculley** et al., "Hidden technical debt in machine learning systems", NeurIPS, 2015 — READ. Short, and the most quietly devastating paper on the list. The model is a tiny box in the middle of a large diagram; everything else is configuration, data collection, serving infrastructure and monitoring. Written by Google engineers about Google systems. It explains, better than anything else, why a model that works in a paper does not work in a health system.
- **Rudin**, "Stop explaining black box machine learning models for high stakes decisions and use interpretable models instead", *Nature Machine Intelligence* 1:206–215, 2019. doi:10.1038/s42256-019-0048-x — READ. Argues that the accuracy-versus-interpretability trade-off is largely a myth in high-stakes settings, and that post-hoc explanation methods are a poor substitute for a model that is interpretable by construction. Directly relevant every time someone offers you SHAP values instead of a model you can read.
- **Kapoor and Narayanan**, "Leakage and the reproducibility crisis in machine-learning-based science", *Patterns* 4(9):100804, 2023. doi:10.1016/j.patter.2023.100804 — SKIM. A taxonomy of eight kinds of leakage, found across 17 fields and 329 papers. This is the paper to reach for when a model's performance looks too good.
- **Lazer**, Kennedy, King and Vespignani, "The parable of Google Flu: traps in big data analysis", *Science* 343:1203–1205, 2014. doi:10.1126/science.1248506 — Already covered in this course's deep dive, but it belongs on any canon list.

And three on bias and documentation, which you should KNOW and be able to name:

- **Obermeyer** et al., "Dissecting racial bias in an algorithm used to manage the health of populations", *Science* 366:447–453, 2019. doi:10.1126/science.aax2342 — The label was cost, not illness. Covered in Lesson 4.
- **Mitchell** et al., "Model cards for model reporting", FAT*, 2019. doi:10.1145/3287560.3287596
- **Gebru** et al., "Datasheets for datasets", *Communications of the ACM*, 2021. doi:10.1145/3458723

  The two documentation standards. Ask for them by name.
- **Bender**, Gebru, McMillan-Major and Shmitchell, "On the dangers of stochastic parrots: can language models be too big?", FAccT, 2021. doi:10.1145/3442188.3445922 — KNOW. The paper that framed the environmental, data-provenance and meaning-versus-form objections to large language models before most people had used one.

---

## Section 6 · The health canon

- **Rajkomar**, Dean and Kohane, "Machine learning in medicine", *New England Journal of Medicine* 380:1347–1358, 2019. doi:10.1056/NEJMra1814259 — READ. The best single orientation for a clinically trained reader.
- **Topol**, "High-performance medicine: the convergence of human and artificial intelligence", *Nature Medicine* 25:44–56, 2019. doi:10.1038/s41591-018-0300-7 — SKIM. Broad, enthusiastic, and a good index of what was promised in 2019 — which makes it a useful yardstick now.
- **Gulshan** et al., "Development and validation of a deep learning algorithm for detection of diabetic retinopathy in retinal fundus photographs", *JAMA* 316:2402–2410, 2016. doi:10.1001/jama.2016.17216 — The landmark result. Read it beside **Beede** et al., "A human-centered evaluation of a deep learning system deployed in clinics for the detection of diabetic retinopathy", CHI, 2020. doi:10.1145/3313831.3376718 — the field study of the same technology in Thai clinics. The pair is the entire lesson of this course in two papers.
- **Esteva** et al., "Dermatologist-level classification of skin cancer with deep neural networks", *Nature* 542:115–118, 2017. doi:10.1038/nature21056 — KNOW.
- **Wynants** et al., "Prediction models for diagnosis and prognosis of covid-19: systematic review and critical appraisal", *BMJ* 369:m1328, 2020. doi:10.1136/bmj.m1328 — SKIM. Hundreds of models, almost all at high risk of bias.

**The reporting standards — know these by name and demand them:**

- **Collins** et al., "TRIPOD+AI statement: updated guidance for reporting clinical prediction models that use regression or machine learning methods", *BMJ* 385:e078378, 2024. doi:10.1136/bmj-2023-078378
- **Liu** et al., "Reporting guidelines for clinical trial reports for interventions involving artificial intelligence: the CONSORT-AI extension", *Nature Medicine* 26:1364–1374, 2020. doi:10.1038/s41591-020-1034-x

---

## Section 7 · If you read only five things

In this order.

1. **Breiman 2001, "The Two Cultures"** — because it names the argument you are already in.
2. **Sculley et al. 2015, "Hidden technical debt"** — because it explains why deployment fails.
3. **Rajkomar, Dean and Kohane 2019, NEJM** — because it is the orientation written for you.
4. **Rudin 2019** — because it gives you grounds to refuse a black box rather than merely dislike it.
5. **Gulshan 2016 and Beede 2020, together** — because the gap between them is this whole course.

Then, if the Breiman paper landed: **Efron and Hastie, *Computer Age Statistical Inference*.**

---

## Where this leaves you

The canon above stops around 2023 and is, in the field's own terms, settled — argued over, but stable. Nothing on this list is going to be overturned next year.

That is exactly what makes it useful, and exactly what makes it insufficient. Lesson 12 takes the same list forward into work that is not settled at all.

## Sources

Every DOI on this page is machine-checked against Crossref for existence and correct attribution — see `sources/source-ledger.md` and run:

```bash
python3 ../../../tools/check_course_dois.py ai-in-public-health
```

Entries without a DOI (Vaswani 2017; Sculley 2015; the four books) are conference or book publications where no Crossref record was expected. They are graded SEARCH in the ledger and should be confirmed before citing in a manuscript.
