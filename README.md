# PfATP4 protein structure predicted with AlphaFold2

This project is one of our contributions to Open Source Malaria (OSM). Previous OSM docking results with homology models did not yield satisfactory outcomes. Hopefully, AlphaFold2 structures will provide better accuracy.

## TL;DR

* 3 PDB files are available at `model/PFATP4_3temp_116_end_relaxed_model_*.pdb`. According to the IDDT diagram, model 1 is the best.
* IntePro [IPR023298 family](https://www.ebi.ac.uk/interpro/entry/InterPro/IPR023298/alphafold/#table) annotations now contain AlphaFold2 predictions for many closely related proteins.
* Feel free to test the [Colab Notebook](AlphaFoldPredictPfAtp4Structure.ipynb)

## Pipeline

1. We downloaded PfATP4 sequence from UniProt [Q9U445](https://www.uniprot.org/uniprot/Q9U445)
2. Then, we trimmed the first 115 residues based on a [domains/family](https://www.ebi.ac.uk/interpro/protein/Q9U445) study of the protein.
3. We performed a multiple-sequence alignment with [HHblits](https://toolkit.tuebingen.mpg.de/tools/hhblits) (default parameters, 3 iterations).
4. We ran AlphaFold2 based on the excellent [ColabFold](https://github.com/sokrypton/ColabFold) notebook by Sergey Orchinnikoy (@sokrypton) and the API hosted at the Södinglab (@SoedingL).

## Limitations

1. AlphaFold2 [GitHub page](https://github.com/deepmind/alphafold) provides the bioinformatics (MSA etc.) pipeline that was used in the original publication. We used the online version of HHblits instead.
2. The notebook provided may not run with the free Google Colab plan due to GPU memory limitations. The Pro plan provided sufficient resources.
