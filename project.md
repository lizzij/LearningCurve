# project
ah finally...

## proposal
### What is a compound heterozygosity gene?
- Recessive restricted search: one allele from each parent &rarr; child inherit two copies of the mutated allele
- For example, SCRIB in RGP_402 Family (Rare Genomes Project_Genomes) is a compound het
- Assumptions about compound hets:
  - there are only pairs (i.e. in 2s)
  - tags and notes should be the same for each pair of compound het

### What's not good enough about the current db and ui?
- Not clear that the pair of compound hets should be together, while other variants should be considered alone
- Tags and notes have to be marked twice on both variants
- In discovery sheet (staff page), report is generated for both compound hets, while there should only be one report

### What should be done about compound hets?
- In search, when recessive restricted search is selected, there should be a popup section for choosing if compound hets should be displayed together or apart
- Create mockup ui for displaying compound hets together
- Changes the database
  - add a linking table
  - or add some marker
- Create ui and/or db script to fix previous compound hets
  - need ui cos sometimes subjective (confident ARI hit)

### Workflow
- iterative front end design (ask for feedback from analysts)
- break up into smaller tickets, document the tickets
- meetups and reports regularly

### Compound hets prediction project
- predict the likelihood of being compound hets
  - good trios (both mom and dad unaffected, child affected)
  - some has missing information

### Coding & non-coding search option
- change search implementation to display changes
- box popup for choosing the different display
- show variant as either recessive or compound hets
- one coding + one none-coding option

## es search
- understand `es-utils.py`
- do `elastic 6` tutorials
