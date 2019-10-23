# Project 1: Compound Hets
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

### Rules for selecting compound heterozygous variants?
We implemented a compound heterozygous filter in Ruby inside the GeneTalk framework. We assume that the phenotype is fully penetrant and that all sequenced individuals are either affected or not affected. The first two rules work on a single variant level:

1. A variant has to be in a **heterozygous** state in all **affected** individuals.
2. A variant must **not** occur in a **homozygous** state in any of the **unaffected** individuals.

If a variant were homozygous in an unaffected individual it could not be disease causing, otherwise the individual would have to be affected, as both copies of the gene harbor the same mutation.

If the genotypes of both parents of an affected child are available and they are both unaffected there is a third rule that is very powerful in reducing the variants:

3. A variant that is heterozygous in an affected child must be **heterozygous** in **exactly one** of the parents.

This rule is a compact version of:

&nbsp;&nbsp;&nbsp;&nbsp;3a. The variant must **not** be **heterozygous** in **both** parents.  
&nbsp;&nbsp;&nbsp;&nbsp;3b. The variant must be **present in at least one** of the parents.  

*Kamphans T, Sabri P, Zhu N, et al. Filtering for compound heterozygous sequence variants in non-consanguineous pedigrees. PLoS One. 2013;8(8):e70151. Published 2013 Aug 5. doi:10.1371/journal.pone.0070151*

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

---

# Project 2: Coding & None-coding Search
In variant search, when the Inheritance mode is "Compound Hets" (or "Recessive", but implement CH first): A **secondary Annotation** hit criteria should appear under annoation to filter for compound hets pairs that each satisfy one of the annoation criteria.
