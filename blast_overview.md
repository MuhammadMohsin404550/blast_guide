# BLast

## What is **BLAST**?

Basic Local Alignment Search Tool (**BLAST**) finds regions of similarity between biological sequences.  The program compares nucleotide or protein sequences to sequence databases and calculates the statistical significance of matches. BLAST can be used to infer functional and evolutionary relationships between sequences as well as help identify members of gene families.

> To access **BLAST** [Click Here](https://blast.ncbi.nlm.nih.gov/Blast.cgi)

**BLAST Web Interface.**

![BLAST Interface](blast_interface.png)

It has **Four** main tool.

**1. Nucleotide BLAST (BLASTn)**
  
This is the most straightforward form of BLAST. You use BLASTn when you have a raw DNA or RNA sequence and want to find where it exists or what it resembles in known nucleotide databases like GenBank.\
**For example:**\
 If you sequence a fragment of an unknown organism's genome, you paste that sequence into BLASTn and it will tell you which organisms have similar sequences. It works entirely at the nucleotide level without any translation.

**2. blastx**

Here your query is a nucleotide sequence, but instead of comparing it directly as nucleotides, BLAST first translates it into protein sequences. Because a nucleotide sequence can be read in six possible reading frames (three on the forward strand and three on the reverse complement strand), blastx translates all six and searches each against a protein database.\
This is extremely useful when you have a newly sequenced DNA region and want to know what protein it potentially codes for, even if you do not yet know which reading frame is correct. It essentially lets a nucleotide sequence speak the language of proteins.

**3. tblastn**

This is the reverse of blastx. Your query is a known protein sequence, and the database contains nucleotide sequences. BLAST translates the nucleotide database in all six reading frames on the fly and compares your protein query against those translations. \
This is particularly powerful when you are hunting for a gene in a genome that has not yet been annotated. **For instance**, if you know a protein exists in humans and want to find its equivalent gene buried in a newly sequenced but unannotated plant genome, tblastn will find the nucleotide region that likely encodes a similar protein.

**4. Protein BLAST (BLASTp)**

Both the query and the database are protein sequences, meaning amino acid sequences. BLASTp is used when you already have a protein sequence and want to find similar proteins in databases like UniProt or the non-redundant protein database at NCBI. Since proteins are more conserved across evolution than nucleotide sequences (because multiple codons can encode the same amino acid), BLASTp is often more sensitive than BLASTn for detecting distant evolutionary relationships. It is the tool for identifying protein function, finding homologs across species, and studying protein families.

