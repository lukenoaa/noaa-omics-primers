# NOAA 'Omics Metabarcoding Primers & Assays

Primer and assay lists used for DNA metabarcoding by NOAA 'Omics researchers, compatible with [FAIRe guidelines](https://fair-edna.github.io).

## Primers

**[metabarcoding_primers.tsv](https://github.com/NOAA-Omics/noaa-omics-primers/blob/main/metabarcoding_primers.tsv)**

Forward and reverse primers are combined in this table, with "forward" or "reverse" provided in the `direction` column. When using the FAIRe format, add "_forward" or "_reverse", respectively, to the term names. For example, `pcr_primer_forward`, `pcr_primer_name_forward`, and `pcr_primer_reference_forward` for forward primers.

- `pcr_primer`: Primer sequence (5'-3'). The primer sequence should NOT contain MIDs and adapter sequences and should be reported in uppercase letters. In primers containing an "N" (any base), the published sequence may contain an "I" (inosine, pairs with any base).
- `pcr_primer_name`: Standardized primer names, using original name but adding the name of the target gene, target subfragment (if applicable), and in some cases author information.
- `pcr_primer_name_published`: Original primer name as published in the reference.
- `pcr_primer_reference`: Link to original publication (DOI if available) of primer.
- `direction`: "forward" or "reverse".

## Assays

**[metabarcoding_assays.tsv](https://github.com/NOAA-Omics/noaa-omics-primers/blob/main/metabarcoding_assays.tsv)**

An assay here is the metabarcoding (amplicon) PCR of a target gene from a mixture of DNA. Forward and reverse primer sequences are provided; any other information from the primers list is not duplicated and must be retrieved from the primers list.

- `assay_name`: A brief, concise identifier for the assay with no spaces or special characters, ensuring machine readability. Must be unique. Suggest including the target taxonomic group, target gene, subfragment (if applicable), and author or commonly used name of assay.
- `targetTaxonomicAssay`: Taxa or species name targeted by the primers.
- `targetTaxonomicScope`: The taxonomic group(s) targeted in the study. This can differ from the targetTaxonomicAssay. For example, the targetTaxonomicAssay may be "Chordata" while the targetTaxonomicScope is "Chondrichthyes" (bony fish, sharks and rays).
- `target_gene`: Targeted gene or locus name for marker gene studies.
- `target_subfragment`: Name of subfragment of a gene or locus. Used to identify specific regions on marker genes like V6 of 16S rRNA.
- `ampliconSize`: The length of the amplicon in basepairs EXCLUDING the primers, adapters, and MIDs. A range can be entered separated by a bar "|" (e.g., "140 | 160"). Units in basepairs.
- `pcr_primer_forward`: Forward PCR primer (5'-3') used to amplify the sequence of the targeted gene.
- `pcr_primer_reverse`: Reverse PCR primer (5'-3') used to amplify the sequence of the targeted gene.
- `assay_reference`: Link to protocol or publication (DOI if available) of assay.
