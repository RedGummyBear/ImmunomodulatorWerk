*IMMUNOMODULATORWERK*

A computational drug discovery pipeline detailing concept-to-candidate design of novel small molecules targeting oncology developed at Immunomodulator.xyz 


WHAT THIS IS:

This repo documents a self-built, end-to-end in-silico drug discovery workflow covering target identification, pocket analysis, pharmacophore modeling, molecular docking, lead optimization, ADMET/toxicity profiling, and off-target screening. Primary targets: c-MYC (oncology) and BRAF V600E (melanoma/colorectal). Secondary work includes nuclear import pathway modulation.
All work was conducted on Google Colab using open-source cheminformatics tools (RDKit, AutoDock Vina, OpenMM, SwissADME).


WORKFLOW SEQUENCE:

In_silicoValidation1 — initial target validation and binding site identification
BRAFInhibitorDocking_Pipeline — full 0-to-1 pipeline: ligand generation → 3D conversion → AutoDock Vina docking → MD prep → ADMET gating (BRAF V600E, PDB: 4MNE)
NuclearImportWorkflow — mechanistic modeling of nuclear import pathway; evaluates ΔΔG (DNA-competition binding) and MAX dimer selectivity for c-MYC inhibitor candidates 6G and 6H
SMILESAssemblyValidator — validates SMILES string integrity before docking runs
Tier1FilterCascade — rule-based in-silico screening across V5–V20 candidates: pocket score, pharmacophore, Vina ΔG, hERG/CYP safety flags
LeadOpt_AnalogSprintToV5 — iterative lead optimization from initial hit to V5; gates on IC50, hERG, and mitochondrial toxicity
ADMEToxValidator_V5vsV9 — ADME profiling of V5 vs V9 using RDKit + SwissADME API; V9 returns GO status across all cut-offs
OffTargetScreeningV5vsV9 — off-target liability comparison between V5 and V9
BenchmarkMatrixV5toV20 — benchmarks V5–V20 against standard drug discovery thresholds (Rule-of-5, CNS/intracellular, first-in-class oncology, PAINS)
EvolutionaryMoleculeDesignDANMYC2to45 — evolutionary analog design for DAN-MYC series from v2 to v4.5
ExtendedMYCEvolutionDAN2to4_5 — extended evolution run for the DAN-MYC series
LargeScaleMYCLibraryScreening — large-scale virtual screening of MYC inhibitor library
cMycInhibitorDossier45xV5 — full pharmacological dossier comparing DAN-MYC-4.5 vs DAN-MYC-6H-V5; evaluates c-MYC inhibition, ADMET proxies, normal-MYC selectivity, and immune-escape probability. Lead candidate: DAN-MYC-6H-V5 (predicted IC50: 0.2 nM, GRANT GREEN verdict)

KEY OUTPUTS:

Lead candidate: DAN-MYC-6H-V5 — predicted IC50 0.2 nM, no in-silico liabilities flagged, cleared for in-vivo proof of concept
BRAF pipeline: architecture validated across all 5 gates; production docking runs require GPU cluster (exhaustiveness=32)
V9 analog: passes all ADME cut-offs via SwissADME; V5–V20 benchmark shows further IC50 optimization needed to clear Rule-of-5 and intracellular thresholds


TOOLS USED:

RDKit · AutoDock Vina · OpenMM · SwissADME API · BioTite · Google Colab


STATUS:

In-silico campaign complete. Next steps: wet lab validation and GPU-cluster production docking runs.
