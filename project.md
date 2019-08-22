# project
ah finally...

## proposal
### What is a compound heterozygosity gene?
- Definition: A compound heterozygous polymorphism refers to a child that has inherited two different heterozygous polymorphisms within the same gene, one from each parent. This could result in both copies of the gene being potentially affected.
  - The human genome contains two copies of each gene, a paternal and a maternal allele. A mutation affecting only one allele is called heterozygous. A homozygous mutation is the presence of the identical mutation on both alleles of a specific gene. However, when both alleles of a gene harbor mutations, but the mutations are different, these mutations are called compound heterozygous.
- Recessive restricted search: one allele from each parent &rarr; child inherit two copies of the mutated allele
- For example, SCRIB in RGP_402 Family (Rare Genomes Project) is a compound het
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
- do `elastic 6.2` tutorials

## Plan
- compound het db and ui
- move onto search options
- prediction for likelihood of compound het

## Random
- check if JSON object is a JSON Array or JSON Object
```
import json

# assume that, each line is valid json data
obj = json.loads(line)

# if returns true, then JSON Array
isinstance(obj, list)

# if returns true, then JSON Object.
isinstance(obj, dict)
```
- for viewing es output use `localhost:3000/api/search/<index>`

- current redis key is `search_results__VSR0009866_f1a64a99936eb356dbb__xpos`
