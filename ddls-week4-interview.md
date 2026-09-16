# DDLS 2026 — Week 4 interview transcript

**Lab:** Interview a Structural-Biology Data Owner
**Data owner:** Dr. Lena Brandt — Neurodegeneration researcher (SOD1 in ALS)
**Student:** Doreen Schwochow <doreen.schwochow@scilifelab.se>
**Exported:** 2026-09-16T12:14:37+00:00

> This is the record of your interview with the data owner. Hand it to your analyst agent as the raw source for `AGENTS.md` and `spec.md`.

---

**You**:

hello! what is your research on SOD1 about and why does it matter for ALS?

**Dr. Lena Brandt**:

I’m Dr. Lena Brandt at SciLifeLab, working on how mutant human SOD1 misfolds and aggregates in motor neurons. SOD1 is the Cu/Zn enzyme that normally detoxifies superoxide; in ALS, mutations can give it damaging properties even when the enzyme still looks functional. I’m trying to identify surface residues to mutate and disrupt its activity or aggregation, and AlphaFold gave me a gorgeous model with about **98** confidence. I need to turn that into a defensible six-mutation shortlist quickly—would you rather start with the disease mechanism or the residue-selection plan?

**You**:

the disease mechanism. what damaging properties are we talking about and which part of the protein mediate that?

**Dr. Lena Brandt**:

The main issue is usually **toxic gain of function**, not simply loss of dismutase activity. Mutant SOD1 can become less stable, misfold, form soluble oligomers and larger aggregates, and bind abnormally to membranes, mitochondria, or proteins involved in axonal transport and stress responses.

There isn’t one single toxic patch. Changes can arise from the **metal-binding region**, the beta-barrel that supports the fold, or flexible surface loops; mutations such as A4V, G93A, and D90A illustrate that quite different positions can produce ALS. Metal loss or abnormal metal chemistry can also increase oxidative injury, while misfolded SOD1 appears especially harmful to motor neurons. For the mutagenesis, do you want to target aggregation-prone surface chemistry or preserve the native enzyme while perturbing abnormal interactions?

**You**:

what is causing ALS?

**Dr. Lena Brandt**:

ALS is not one disease with one cause. It involves progressive motor-neuron death, with inherited mutations accounting for roughly 5–10% of cases—SOD1 is one of the established genes—while most cases are sporadic and probably reflect a mixture of genetic susceptibility, aging, cellular stress, and environmental factors.

For SOD1-linked ALS, the mutations generally cause a toxic new property: instability, misfolding, aggregation, abnormal interactions, and disturbed mitochondrial or axonal function—not simply failure to remove superoxide. Are you asking about ALS overall or specifically how mutant SOD1 kills motor neurons?

**You**:

tell me about the model you got: how did you get it? did you use the entire protein sequence?

**Dr. Lena Brandt**:

I put the human **SOD1 sequence—154 amino acids, the entire protein—into AlphaFold** and accepted the resulting structure. It came back as a beautiful, compact fold with confidence around **98**, so I assumed the surface was reliable for planning mutations. I also received a separate confidence-matrix file, but I haven’t opened or interpreted it; do you want to focus on how the model was generated or on selecting residues from it?

**You**:

first tell me everything about the model and what you got.

**Dr. Lena Brandt**:

I used the full 154-residue human SOD1 sequence. AlphaFold returned a single, compact, beautifully folded structure with confidence around **98**; in the viewer I can see many residues on the outside that look suitable for mutation. I received the structure as `SOD1_alphafold_model.cif`, plus `SOD1_alphafold_pae.json`, which I understand is some additional confidence information but haven’t interpreted. I haven’t calculated residue exposure or checked candidate positions—would you like the next step to be identifying outside-facing residues or checking the confidence data?

**You**:

have you experimentally validated the structure?

**Dr. Lena Brandt**:

No—this particular structure has not been experimentally validated. I only inspected the AlphaFold model in the viewer and trusted its roughly **98** confidence; I haven’t compared it systematically with an experimental SOD1 structure or tested the proposed mutation sites in the lab. For the shortlist, should we treat the model as a guide rather than proof?

**You**:

what number would have to be true for your claim to hold?

**Dr. Lena Brandt**:

If you mean my claim that the model is reliable, there isn’t a single confidence number that would make it experimentally true. The **~98** only made me feel reassured; it isn’t validation. Do you mean reliability of the fold, confidence at a particular residue, or confidence that a residue is suitable for mutation?

**You**:

what exactly does confidence around 98 mean? what exact value is it? what is it called?

**Dr. Lena Brandt**:

I don’t know the exact value—I only noted that the viewer showed confidence at roughly **98**. I also don’t know the formal technical name for that score; I’ve been calling it the model’s confidence, and I haven’t inspected the structure file to verify whether 98 is a single summary or an average across residues.

**You**:

can you tell me more about the protein itself: what is known about how it folds? does it have different regions? are there regions that need to be in contact to work properly together  etc.?

**Dr. Lena Brandt**:

SOD1 is a small, largely **beta-sheet barrel** stabilized by several connecting loops rather than by separate domains. The metal-binding loops position histidines and other ligands around copper and zinc; those contacts are essential for catalysis and also help hold the fold together. A disulfide bond involving Cys57 and Cys146 further stabilizes the mature protein, while the long loop around residues 50–80 and the C-terminal region are important for shaping the active site and overall stability.

So yes—different parts have to contact one another precisely: the metal-binding loops must sit against the barrel, and the ends of the chain help close and stabilize the structure. Mutations far from the catalytic histidines can still disrupt folding or promote aggregation by weakening those internal contacts. Are you most interested in the metal-binding region, the flexible loops, or the parts linked to aggregation?

**You**:

which residues are you interested in and why?

**Dr. Lena Brandt**:

I haven’t chosen exact residues yet. I’m interested in outside-facing positions that are confidently modelled, away from the metal-binding histidines—His46, His48, His63, His71, His80, and His120—because I want to perturb abnormal interactions or aggregation without simply destroying catalysis. The sequence and structure files are there for you to identify the six; I wouldn’t trust myself to pick them by eye. Are you screening for aggregation-related surfaces or for residues that alter interactions with cellular partners?

**You**:

maybe both would be interesting for your questions?

**Dr. Lena Brandt**:

Yes, both—but they’re not the same experiment. I’d want a small set that perturbs aggregation-prone surface chemistry and another that tests cellular binding, while avoiding the catalytic histidines; with only six mutations, the distinction matters. Should the shortlist prioritize mechanistic separation or the strongest chance of seeing a phenotype before the grant deadline?

**You**:

six each or six in total?

**Dr. Lena Brandt**:

Six in total, unfortunately. That’s the entire mutagenesis budget, so we need a rule that gives us interpretable coverage rather than six attractive-looking surface residues. Should we prioritize aggregation or cellular interactions?

**You**:

cellular binding to what?

**Dr. Lena Brandt**:

To abnormal partners associated with mitochondria, membranes, axonal transport, and stress responses—rather than one single confirmed receptor. Misfolded mutant SOD1 can acquire promiscuous interactions with several cellular systems, which is part of why motor neurons are vulnerable. Do you want the six mutations aimed at one candidate interaction or spread across different kinds of binding surfaces?

**You**:

is this a single domain or complex protein?

**Dr. Lena Brandt**:

It is one compact folded protein rather than a multi-domain protein, but the working enzyme is made from **two identical SOD1 copies clamped together**. The model I received shows only one copy, not the complete working pair—I hadn’t appreciated that distinction when I first looked at the “surface.” Do you want the six candidates to exclude positions that may lie against the other copy?

**You**:

would the model actually allow for two SOD1 copies to bind together?

**Dr. Lena Brandt**:

Not by itself. The file contains one SOD1 copy, so it doesn’t show whether a second copy can bind or which outside-facing residues would be involved; it is compatible with the pair, but it does not demonstrate it. Since the functional enzyme is two copies clamped together, we must check the known SOD1 pairing arrangement before calling any residue safe to mutate—should I treat possible contact residues as exclusions?

**You**:

is it known were the two copies form a dimer?

**Dr. Lena Brandt**:

Yes. Experimental SOD1 structures show the two copies meeting mainly along complementary faces of their beta-barrels, involving the N-terminal and C-terminal edge regions and segments around the 50–60 and 90–100 areas. The exact contacts depend somewhat on the metal-loaded state, and this pairing surface is distinct from—but close enough to influence—the metal-binding loops; mutations such as **A4V** can destabilize the pair and promote misfolding. 

So I would not call every outside-facing residue in my single-copy model safe. Do you want the six-position rule to exclude known or likely pairing-contact residues as well as the histidines?

**You**:

what are the known pairing contacts? why would I want to exclude them?

**Dr. Lena Brandt**:

The best-established contact regions are the **N-terminal edge**, the **C-terminal edge**, and parts of the barrel around roughly residues **50–60** and **90–100**. I would treat those as *possible pairing-contact regions*, not as an exact residue-by-residue map from my single-copy file; the precise contacts depend on the experimental structure and metal state.

I’d exclude them if the experiment is meant to test aggregation or cellular binding, because a mutation there could simply weaken or rearrange the normal two-copy enzyme. That would make any phenotype hard to interpret—especially with mutations like **A4V**, where altered pairing and instability are already part of the disease story. Do you want to preserve normal pairing, or deliberately perturb it as one of the six experiments?

**You**:

hello

**Dr. Lena Brandt**:

Hello—still here. Do you want to continue with the SOD1 pairing contacts, or return to choosing the six mutations?

**You**:

yes, do you have any criteria or ideas or thoughts on how to chose those six mutations?

**Dr. Lena Brandt**:

Yes. I’d use a hard rule: include only residues that are outside-facing in the model, have local confidence above 90, are away from the six metal-binding histidines and the Cys57–Cys146 stabilizing disulfide, and are not in the known regions where the two SOD1 copies contact each other. Then rank those by biological plausibility—three affecting aggregation-related chemistry and three probing abnormal cellular binding—while keeping the amino-acid changes conservative enough not to destroy the fold outright.

I can’t identify the six from the files by eye; that’s exactly the computational part I need you to do. Do you want the experiment designed to preserve normal SOD1 activity, or are you willing to include one deliberately disruptive control?

**You**:

yes, one deliberately disruptive control

**Dr. Lena Brandt**:

Then I’d reserve one slot for a **known destabilizing control**, rather than applying the “safe surface” rule to all six. A4V is a plausible choice because it is an ALS-linked SOD1 mutation associated with instability and abnormal aggregation, but its effect could also disturb the normal two-copy pairing—so it tells us the assay can detect disruption, not whether a surface candidate specifically affects binding or aggregation. That leaves five exploratory mutations; should the control be A4V, or do you want a less disease-specific folding control?

**You**:

can you name some for me? then I can decide during analysis if I would need a different control.

**Dr. Lena Brandt**:

For a deliberately disruptive disease-linked control, the obvious candidates are **A4V, G93A, D90A, and I113T**. **A4V** is the strongest general instability/aggregation control, whereas **G93A** is widely used in cellular and mouse ALS models; D90A and I113T can also alter stability and misfolding but may be more assay-dependent.

I would not use any of those as one of the five “safe surface” mutations—they are controls for abnormal behavior, not clean tests of a particular surface. For the exploratory five, I need the residue-level analysis from the model and sequence rather than inventing names from memory; which assay will define “disruptive”—loss of activity, aggregation, or cell toxicity?

**You**:

how would you define those categories?

**Dr. Lena Brandt**:

I’d define them by the **primary readout**:

- **Loss of activity:** reduced superoxide dismutation, measured with a standard SOD1 enzymatic assay. This says the mutation compromises catalysis or metal handling.
- **Aggregation:** increased insoluble or high-molecular-weight SOD1, ideally confirmed by sedimentation or microscopy rather than relying on one staining assay.
- **Cell toxicity:** reduced motor-neuron viability or neurite health, with evidence that the effect tracks with mutant SOD1 rather than general expression stress.

For the five exploratory mutations, I’d want activity preserved but altered aggregation or cellular behavior; otherwise we cannot tell a specific toxic mechanism from a generally damaged protein. Which readout can your lab measure most reliably?

**You**:

Ok, so you want 5-6 mutations, which affect activity, aggregation and cell toxicity of SOD1 in ALS. we use one verification mutation and then 5 exploratory, which keep the proteins function and only affect aggregation or cell toxicity. you got high confidence score but only for a monomer while SOD1 is actually active as a dimer, so the confidence numbers might not take that into account. what did I miss?

**Dr. Lena Brandt**:

That is mostly right, but three important points are missing.

1. **The confidence value is not verified.** I only remember “about 98”; I do not know its exact value, what it is averaged over, or whether it applies locally to each residue. The extra `SOD1_alphafold_pae.json` file may matter, and I have not examined it.
2. **The five exploratory mutations cannot be assumed to affect aggregation or toxicity while preserving function.** That has to be tested: activity and metal handling first, then aggregation and cellular effects. A cellular phenotype could simply reflect poor expression, loss of folding, or disrupted pairing.
3. **The single-copy model is insufficient for choosing “safe” outside residues.** We need to compare candidates with experimentally established contacts between the two SOD1 copies and exclude metal-coordination regions, the Cys57–Cys146 disulfide context, and important structural loops.

Also, A4V is a useful disease-linked destabilizing control, but it does not by itself verify that our assay specifically detects aggregation or toxicity. We still need an appropriate wild-type control and expression/solubility controls. The immediate missing deliverable is therefore not just six names, but six names plus evidence that each exploratory change leaves normal SOD1 activity intact.
