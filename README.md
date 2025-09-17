# NOAA 'Omics Metabarcoding Targets

PCR targets (primers and associated information) used for DNA metabarcoding by NOAA 'Omics researchers, compatible with [FAIRe guidelines](https://fair-edna.github.io).

## Targets (formerly assays)

### [targets.tsv](https://github.com/lukenoaa/noaa-omics-primers/blob/main/targets.tsv)

Use this file to access all target information using FAIRe terms. To avoid repeating primer information in this main file, the two files `primers_without_target_info.tsv` and `targets_without_primer_info.tsv` are maintained separately and then merged to generate `targets.tsv`.

### [primers_without_target_info.tsv](https://github.com/lukenoaa/noaa-omics-primers/blob/main/primers_without_target_info.tsv)

Forward and reverse primers are combined in this table, with "forward" or "reverse" provided in the `direction` column. In the file `targets_and_primers.tsv`, "_forward" or "_reverse" are added to the term names.

- `pcr_primer`: Primer sequence (5'-3'). The primer sequence should NOT contain MIDs and adapter sequences and should be reported in uppercase letters. In primers containing an "N" (any base), the published sequence may contain an "I" (inosine, pairs with any base).
- `pcr_primer_name`: Standardized primer names, using original name but adding the name of the target gene, target subfragment (if applicable), and in some cases author information.
- `pcr_primer_name_published`: Original primer name as published in the reference.
- `pcr_primer_reference`: Link to original publication (DOI if available) of primer.
- `direction`: "forward" or "reverse".

### [targets_without_primer_info.tsv](https://github.com/lukenoaa/noaa-omics-primers/blob/main/targets_without_primer_info.tsv)

An target here is the assay information for PCR target. Forward and reverse primer sequences are provided; any other information from the primers list is not duplicated and must be retrieved from the primers list.

- `target_name`: A brief, concise identifier for the target with no spaces or special characters, ensuring machine readability. Must be unique. Suggest including the target taxonomic group, target gene, subfragment (if applicable), and author or commonly used name of assay.
- `targetTaxonomicAssay`: Taxa or species name targeted by the primers.
- `targetTaxonomicScope`: The taxonomic group(s) targeted in the study. This can differ from the targetTaxonomicAssay. For example, the targetTaxonomicAssay may be "Chordata" while the targetTaxonomicScope is "Chondrichthyes" (bony fish, sharks and rays).
- `target_gene`: Targeted gene or locus name for marker gene studies.
- `target_subfragment`: Name of subfragment of a gene or locus. Used to identify specific regions on marker genes like V6 of 16S rRNA.
- `ampliconSize`: The length of the amplicon in basepairs EXCLUDING the primers, adapters, and MIDs. A range can be entered separated by a bar "|" (e.g., "140 | 160"). Units in basepairs.
- `pcr_primer_forward`: Forward PCR primer (5'-3') used to amplify the sequence of the targeted gene.
- `pcr_primer_reverse`: Reverse PCR primer (5'-3') used to amplify the sequence of the targeted gene.

## Assays

An assay contains all the information about the target plus lab-specific details. These additional fields may differ from lab to lab for the same target, and thus are not included in the above tables.

- `assay_name`: Name for the assay that uses the above target but also has lab-specific details.
- `nucl_acid_amp`: Link to protocol or publication (DOI if available) of assay.
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
