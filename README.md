# NOAA 'Omics Metabarcoding Assays

Metabarcoding assays used for DNA metabarcoding by NOAA 'Omics researchers, using terms from the [FAIRe](https://fair-edna.github.io) standard. An assay is defined by the unique combination of forward and reverse PCR primers, which have fixed data associated with them (taxonomic target, gene, subfragment, amplicon size, primer sequences, primer names, and primer references). The assay metadata contains additional terms that can vary from lab to lab, but a given combination of PCR primers will still have the same core assay data (`assays.tsv`).

## Assays

### [assays.tsv](https://github.com/lukenoaa/noaa-omics-primers/blob/main/assays.tsv)

Core assay information. This file is created by `merge_assays_primers.ipynb`, which merges `primers_without_assay_info.tsv` and `assays_without_primer_info.tsv`. The fields are described under the two files listed below.

### [assays_without_primer_info.tsv](https://github.com/lukenoaa/noaa-omics-primers/blob/main/assays_without_primer_info.tsv)

- `assay_name`: A brief, concise identifier for the assay with no spaces or special characters, ensuring machine readability. Must be unique. Suggest including the targeted taxonomic group, gene, subfragment (if applicable), and author or commonly used name of assay.
- `targetTaxonomicAssay`: Taxa or species name targeted by the primers.
- `targetTaxonomicScope`: The taxonomic group(s) targeted in the study. This can differ from the targetTaxonomicAssay. For example, the targetTaxonomicAssay may be "Chordata" while the targetTaxonomicScope is "Chondrichthyes" (bony fish, sharks and rays).
- `target_gene`: Targeted gene or locus name for marker gene studies.
- `target_subfragment`: Name of subfragment of a gene or locus. Used to identify specific regions on marker genes like V6 of 16S rRNA.
- `ampliconSize`: The length of the amplicon in basepairs EXCLUDING the primers, adapters, and MIDs. A range can be entered separated by a bar "|" (e.g., "140 | 160"). Units in basepairs.
- `pcr_primer_forward`: Forward PCR primer (5'-3') used to amplify the sequence of the targeted gene.
- `pcr_primer_reverse`: Reverse PCR primer (5'-3') used to amplify the sequence of the targeted gene.

### [primers_without_assay_info.tsv](https://github.com/lukenoaa/noaa-omics-primers/blob/main/primers_without_assay_info.tsv)

- `pcr_primer`: Primer sequence (5'-3'). The primer sequence should NOT contain MIDs and adapter sequences and should be reported in uppercase letters. In primers containing an "N" (any base), the published sequence may contain an "I" (inosine, pairs with any base).
- `pcr_primer_name`: Standardized primer names, using original name but adding the name of the target gene, target subfragment (if applicable), and in some cases author information.
- `pcr_primer_name_published`: Original primer name as published in the reference.
- `pcr_primer_reference`: Link to original publication (DOI if available) of primer.
- `direction`: "forward" or "reverse".

Note: Forward and reverse primers are combined in this table, with "forward" or "reverse" provided in the `direction` column. When `assays.tsv` is created, "_forward" or "_reverse" are appended to the term names.

## Assay metadata

An assay contains all the fixed assay information plus variable lab-specific details. These variable fields may differ from lab to lab for the same assay, and thus are not included in the above tables.

- `nucl_acid_amp`: Link to assay protocol DOI on Zenodo. Example: `https://doi.org/10.5281/zenodo.15636182`
- `thermocycler`
- `commercial_mm`
- `custom_mm`
- `nucl_acid_amp`
- `pcr_cond`
- `barcoding_pcr_appr`
- `pcr2_commercial_mm`
- `pcr2_cond`
- `sequencing_location`
- `platform`
- `instrument`
- `seq_kit`
- `adapter_forward`
- `adapter_reverse`
- `lib_screen`
- `checksum_method`
- `seq_method_additional`
