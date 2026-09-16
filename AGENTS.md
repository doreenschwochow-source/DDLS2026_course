# AGENTS.md

## Environment and workflow

- Use `uv`: create the environment with `uv venv` and run all Python with `uv run`. This works the same on every OS.
- The interview transcript is `ddls-week4-interview.md`.
- Input data lives in `data/`:
  - `data/SOD1.fasta` is the human SOD1 sequence.
  - `data/SOD1_alphafold_model.cif` is the AlphaFold mmCIF model.
  - `data/SOD1_alphafold_pae.json` is the confidence-matrix JSON.
- Write generated outputs to `results/`.
- To load a structure, use an mmCIF/PDB reader. In the mmCIF, pLDDT is in the B-factor column. PAE is in the JSON; use the `predicted_aligned_error` matrix and its `max_predicted_aligned_error` metadata.

## Folding sequences not in the AlphaFold DB

Use the course fold service. To fold a protein sequence that is not in the AlphaFold DB, read `https://ddls-structure-api-8a7d6803.svc.hypha.aicell.io/skill.md` and follow it. Take the fold key from the `DDLS_FOLD_KEY` variable in `.env`; load it with `set -a; source .env; set +a`, then send it as the Bearer token. Never write the key itself into `AGENTS.md` or any other committed file.

## Version control

This folder is a git repository. Commit the current state before any big change, and commit again whenever something starts working, using short, clear messages. Never commit secrets; `.gitignore` excludes `.env`, `.venv/`, `__pycache__/`, and `*.pyc`.

## Evidence rule

Never report an answer about a structure without first reporting the confidence that matches the claim and confirming that the model is actually this protein. Use per-residue pLDDT for a fold or region claim; use PAE/interface evidence for claims about how parts sit together. The supplied model is one SOD1 copy, whereas the transcript says the active enzyme is a two-copy assembly; do not treat monomer evidence as proof of the dimer.
