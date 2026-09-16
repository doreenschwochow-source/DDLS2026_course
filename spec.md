# Specification

## Decision needed

The owner needs a defensible six-mutation SOD1 shortlist: one deliberately disruptive/verification control and five exploratory mutations. The exploratory changes should be intended to preserve normal SOD1 activity while testing aggregation-related or abnormal cellular-binding/cell-toxicity effects. The owner has a six-mutation mutagenesis budget.

## Protein and assembly

- Protein: human SOD1 (Cu/Zn superoxide dismutase), UniProt P00441.
- Sequence: 154 amino acids, and the supplied FASTA is described as the entire protein sequence.
- The supplied structure is predicted by AlphaFold, not experimentally validated.
- The supplied mmCIF shows one compact SOD1 copy (a monomer model), not the complete working assembly.
- The transcript says the functional enzyme is made from two identical SOD1 copies clamped together (a dimer).
- SOD1 is described as one compact folded protein rather than a multi-domain protein, with a beta-sheet barrel and connecting loops.

## Files

- `ddls-week4-interview.md`: raw interview transcript and owner requirements.
- `data/SOD1.fasta`: human SOD1 sequence, 154 aa.
- `data/SOD1_alphafold_model.cif`: predicted single-copy AlphaFold structure. Its B-factor column carries pLDDT values.
- `data/SOD1_alphafold_pae.json`: predicted aligned error matrix and maximum predicted aligned error metadata.

## Exact owner claim and relevant residues/parts

The owner is making the working claim that five exploratory mutations can perturb aggregation or abnormal cellular interactions/cell toxicity while preserving normal SOD1 activity, plus one known destabilizing control can demonstrate assay sensitivity. The owner wants outside-facing, confidently modelled residues, away from the six metal-binding histidines—His46, His48, His63, His71, His80, and His120—away from the Cys57–Cys146 disulfide context, important structural loops, and likely dimer-contact regions. The transcript proposes three aggregation-related and three abnormal-cellular-binding probes, but the final six include one control and five exploratory positions.

The control candidates named in the transcript are A4V, G93A, D90A, and I113T; A4V is described as the obvious general instability/aggregation control, but it may also disturb dimer pairing. These are owner-provided candidates, not a final selection.

Relevant assembly regions to check are the N-terminal and C-terminal beta-barrel edges and approximate regions 50–60 and 90–100. The transcript explicitly says these are possible pairing-contact regions, not an exact residue-level map from the supplied monomer file.

## Confidence required for each claim

- For a fold or local-region claim, report the relevant per-residue pLDDT from the mmCIF B-factor column; do not substitute the owner’s remembered “about 98” for verified values.
- For a claim about how separate regions or two SOD1 copies sit together, report PAE/interface evidence from the JSON and distinguish monomer-model evidence from dimer evidence.
- High pLDDT alone does not validate the model experimentally, establish mutation safety, or establish the dimer interface.

## Checks that could break the decision

1. Confirm that the FASTA sequence is exactly the sequence represented by the structure, including length, residue identities, numbering, and chain identity.
2. Confirm that the mmCIF is actually human SOD1 rather than relying only on its filename or metadata.
3. Confirm the number of chains and residues represented by the model; the transcript says one chain/copy and 154 residues.
4. Check whether candidate positions are outside-facing in the monomer model, but do not call them safe until the experimentally established SOD1 dimer arrangement is checked.
5. Exclude or flag the six metal-binding histidines, the Cys57–Cys146 disulfide context, important structural loops, and likely dimer-contact regions.
6. Use the PAE file to assess confidence in relative placement of parts; do not infer a dimer interface from a monomer PAE matrix.
7. Remember that exploratory effects must be tested: activity and metal handling first, then aggregation and cellular effects. A cellular phenotype could instead result from poor expression, misfolding, loss of activity, or disrupted pairing.
8. Include wild-type, expression/solubility, and suitable assay controls; A4V alone does not verify assay specificity.

## Definition of done

Done means a documented six-position shortlist (one control plus five exploratory mutations) with the original residue and proposed substitution, sequence/structure identity and assembly checks, exposure and exclusion rationale, verified local pLDDT for fold/region claims, and appropriate PAE/interface evidence for any claim about parts sitting together. It must clearly label what comes from the supplied files, what comes from the transcript, what remains unknown, and what must be experimentally tested. No shortlist is defensible until the single-copy model versus the active dimer distinction is addressed.
