# Nucleotide BLAST (BLASTn)

This is the most straightforward form of BLAST. You use BLASTn when you have a raw DNA or RNA sequence and want to find where it exists or what it resembles in known nucleotide databases like GenBank.\
**For example:**\
 If you sequence a fragment of an unknown organism's genome, you paste that sequence into BLASTn and it will tell you which organisms have similar sequences. It works entirely at the nucleotide level without any translation.

> To access BLASTn [Click Here](https://blast.ncbi.nlm.nih.gov/Blast.cgi?PROGRAM=blastn&PAGE_TYPE=BlastSearch&BLAST_SPEC=&LINK_LOC=blasttab&LAST_PAGE=blastn)

> **ALL THIS IS INPUT PAGE**

![BLASTn Interface](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/blastn_interface.png?raw=true)

# The Nucleotide BLAST Search Page

The “nucleotide-blast” link loads the standard “Nucleotide BLAST” search page, with the breadcrumb at the top indicating the page position within the site hierarchy **(A)**. A set of tabs for quick navigation among the five flavors of BLAST search pages **(B)** are under the descriptive page title. Two buttons to the right **(C)** reset the search settings to default and bookmark the custom settings, respectively. The page contains three sections, whose functions are described below.  

![blastn](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/blastn.png?raw=true)

## Enter Query Sequence Explanation 1

This input box **(D)** takes nucleotide query sequences in accession (NM_000249) or FASTA format. For a single input, “Query subrange” boxes **(E)** define a segment of that input to use in the search. The “Choose File” button **(F)** upload a plain text file with one or more sequences in FASTA format. The “Align two or more sequences” checkbox **(G)** changes the database list in “Choose Search Set” to a “Enter Subject Sequence” input box to allow the entering of another set of sequences for custom comparison.

## Enter Query Sequence Explanation 2

This is where you **provide** the **nucleotide sequence** you want to search.

You have **three ways** to do this.

1. You can paste an accession number, which is a unique identifier for a sequence already in NCBI's database. 
2. You can paste a GI number, which is another type of sequence identifier. You can paste a FASTA sequence directly, which is a text format that starts with a ">" line containing the sequence name followed by the actual sequence on the next line. 
3. You can also upload a file instead of pasting.

The **"Query subrange"** fields (From and To) let you search only a specific portion of your sequence rather than the whole thing, which is useful if you only care about a particular region.

The **"Job Title"** field lets you label your search so you can identify it later in your results history.

The **"Align two or more sequences"** checkbox switches the tool into a pairwise alignment mode where you compare two specific sequences directly against each other rather than searching a database.

## Choose Search Set Explanation 1

![chose_search_set](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/chose_search_set.png?raw=true)

You can change the default database using the pull-down menu **(A)**. To focus a search, you can restrict the lookup to a subset of the database by typing the name of the organism in the “Organism” textbox and selecting from the suggested list, using the checkbox to exclude the selection, and clicking the “Add organism” button to add extra input boxes to broaden the selection **(B)**. Use checkboxes in Exclude line **(C)** to exclude sequences with low information content from the hits, or enter query terms in the “Entrez Query” textbox **(D)** to restricts a search to entries satisfying the specified criteria for non-wgs and non-sra databases under the “Standard databases” list. For example, “500:1000[slen]” restricts a search to database entries with length between 500 and 1000.

## Choose Search Set Explanation 2

This section determines which database your query will be searched against.

The **Database options** visible here are Standard databases (nr etc.), rRNA/ITS databases, Genomic and transcript databases, Betacoronavirus, and Experimental databases. The currently selected one is the Core nucleotide database (core_nt), which is a curated subset of GenBank containing well-supported sequences.

The **Organism field** is optional and very useful — it lets you restrict your search to a specific organism so you only get hits from, say, humans or Arabidopsis thaliana instead of all life.

The **Exclude options** let you filter out Model sequences (XM/XP), which are computationally predicted rather than experimentally verified, and Uncultured/environmental sample sequences, which come from environmental samples and may be less reliable.

The **Limit to field** with "Sequences from type material" restricts results to sequences from officially designated type specimens, useful for taxonomic work.

The **Entrez Query field** lets you write a custom filter using NCBI's Entrez query syntax to further narrow your search in very specific ways.

## Program Selection Explanation 1

![program_selection_1](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/program_selection_1.png?raw=true)

Three programs (**E** and Table 1 in p.2) with different search speed and sensitivity are available for nucleotide searches. The default megablast is better for tasks such as identifying input queries or searching with a large genomic entry; discontiguous megablast works better in finding related sequences from other species; while blastn works better for cross-species searches than megablast and for identifying short matches.

## Program Selection Explanation 2

![program_selection_2](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/program_selection_2.png?raw=true)

**Optimize for**

Highly similar sequences (megablast) is the default and currently selected option. Megablast is the fastest algorithm and is designed for finding sequences that are nearly identical to your query, typically above 95% identity. It is best used when comparing sequences within the same species or very closely related organisms. Because it uses a larger word size for its initial seed matches, it is very fast but will miss distantly related sequences.

More dissimilar sequences (discontiguous megablast) is a middle-ground option. It uses a non-contiguous word matching strategy, meaning the seed it looks for does not have to be a perfectly continuous stretch of matching bases. This makes it more sensitive than megablast and suitable for comparing sequences across different species where some mismatches are expected, such as cross-species gene comparisons.

Somewhat similar sequences (blastn) is the traditional BLASTn algorithm. It uses a smaller word size which makes it the slowest of the three but the most sensitive. It is best for finding distantly related sequences where similarity may be low, such as comparing sequences across very different organisms or looking for conserved regions in divergent genomes.

**The BLAST button**

At the bottom you can see the blue BLAST button along with a summary line that confirms exactly what will happen when you click it, in this case it will search the core_nt database using Megablast optimized for highly similar sequences. This confirmation line updates as you change your settings, which is a helpful way to verify your choices before running the search. There is also a "Show results in a new window" checkbox if you want the results to open separately.

## Algorithm parameters Explanation 1

![algoritm_pattren_1](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/algoritm_pattren_1.png?raw=true)

Open Algorithm Parameters (F) to access additional parameter settings.

Under General Parameters, the “Max target sequences” (G) sets the upper limit on database sequences with matches BLAST will save and report back. The checked “Short queries” (H) allows BLAST to optimize settings for queries 30 bases/ residues or shorter. The “Expect threshold” (I) filters out less significant matches, with Expect value above the setting. The “Word size” (J) controls the size of the initial seed match, with smaller settings more sensitive. The “Max matches in a query range” (K) limits the matches saved to a given region of the query (such as a repeat region) so matches to other regions of the query can be reported. The default setting of “0” means no limit.

Under Scoring Parameters, the “Match/ Mismatch Scores” (L) specifies the reward assigned to an exact match and penalty assigned to a mismatch. The “Gap Costs” (M) specifies how penalties for gaps introduced in the alignment. For megablast, the default is linear, i.e., no penalty for opening a gap and a linear penalty proportional to the length of the gap upon gap extension.

Parameters under Filter and Masking specify what query masking should be used. Default is to mask low complexity regions in the query and only at the seed match stage (N). For genomic sequence, make sure to activate “speciesspecific repeats for:” option (O) and select the correct species from the pulldown list.

## Algorithm parameters Explanation 2
![algorithm_pattren_2](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/algorithm_pattren_2.png?raw=true)

**General Parameters**

Max target sequences is set to 100, meaning BLAST will return at most 100 matching sequences in your results. You can increase this if you want a broader picture or decrease it to keep results focused.

Short queries has a checkbox that is ticked by default. When enabled, BLAST automatically adjusts its internal parameters if your input sequence is very short, since short sequences need different sensitivity settings to find meaningful matches.

Expect threshold is set to 0.05. This is the E-value cutoff. Only hits with an E-value equal to or below 0.05 will be shown in your results. The default is usually 10, so setting it to 0.05 here makes the search more stringent, meaning only statistically significant matches will appear.

Word size is set to 28. This is the length of the initial seed that BLAST uses to find candidate matches before extending them into full alignments. A larger word size like 28 (typical for megablast) means the search is faster but less sensitive. Smaller word sizes find more distant matches but take longer.

Max matches in a query range is set to 0, which means there is no limit on how many matches can be reported from any given region of your query sequence.

**Scoring Parameters**

Match/Mismatch Scores is set to 1,-2. This means each matching base adds 1 to the alignment score, while each mismatching base subtracts 2. This ratio influences how tolerant the alignment is toward mismatches, a higher penalty for mismatches makes the search more strict.

Gap Costs is set to Linear. This defines how insertions and deletions (gaps) in the alignment are penalized. A linear gap cost means the penalty grows proportionally with gap length, which is the simplest model. Other options would apply an additional penalty for opening a new gap.

**Filters and Masking**

Filter, Low complexity regions is checked. Low complexity regions are stretches of sequence with repetitive or biased composition, like runs of the same nucleotide (AAAAAAA) or simple repeats. These regions tend to produce many meaningless hits, so filtering them out keeps your results biologically meaningful.

Filter, Species-specific repeats is unchecked but set to Homo sapiens by default. If checked, it would mask known repetitive elements specific to humans (like Alu repeats) before searching, preventing those repeats from dominating your results.

Mask for lookup table only is checked. This means the masking is only applied during the initial seed-finding step but not during the final alignment extension, which balances sensitivity and specificity well.

Mask lower case letters is unchecked. If you manually put parts of your FASTA sequence in lowercase, checking this would tell BLAST to ignore those regions during the search.

**BLAST Button**

At the bottom the confirmation line again shows that the search will run on the core_nt database using Megablast, reflecting all the parameters you have set above.

> **ALL THIS IS OUTPUT PAGE**

![blastn_output](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/blastn_output.png?raw=true)

> I taken FASTA file of Pseudomonas putida strain QAU90 PqqC (pqqC) gene, complete cds from https://www.ncbi.nlm.nih.gov/ for test and one thing to remember that in result the first result is same which i put.

**Descriptions Tab**

![blastn_description](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/blastn_description.png?raw=true)

This is the main results list titled "Sequences producing significant alignments." Each row represents one hit — a sequence in the database that matched your query. The columns mean the following:

**Description** is the full name of the matching sequence. The top hit is "Pseudomonas putida strain QAU90 PqqC (pqqC) gene, complete cds" which is essentially the same sequence as the query, confirming the search worked correctly.

**Scientific Name** is the organism the hit belongs to. All hits here are various Pseudomonas species, which makes biological sense since the query was from Pseudomonas putida.

**Max Score** is the highest alignment score from any single alignment segment between your query and that hit. Higher is better.

**Total Score** is the sum of scores from all alignment segments if there are multiple. When there is only one alignment region, Max and Total Score are the same.

**Query Cover** shows what percentage of your query sequence is covered by the alignment. All top hits here show 100%, meaning the entire 771 bp query aligned to each subject.

**E value** is the statistical significance. All top hits show 0.0, which effectively means the probability of finding this match by chance is essentially zero — these are extremely significant hits.

**Per. Ident** (Percent Identity) shows how similar the aligned sequences are. The top hit shows 100% identity, confirming it is the exact same sequence. Other hits range from 92% to 96%, indicating closely related but not identical sequences.

**Acc. Len** is the total length of the matching sequence in the database. Notice these are complete genome sequences millions of base pairs long, yet your 771 bp query aligned to them perfectly.

**Accession** is the unique GenBank identifier for each hit, such as KM251428.1 for the top hit.

**Graphic Summary Tab**

![blastn_graphical_summary](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/blastn_graphical_summary.png?raw=true)

This visual shows the "Distribution of the top 10 BLAST hits on 10 subject sequences." The teal bar at the top represents your query sequence spanning from position 1 to 750 (771 bp). Each red bar below it represents one hit, showing where on your query that hit aligned.

The color of each bar corresponds to the alignment score legend shown at the top right. Red means a score of 200 or above, which indicates very high quality alignments. All 10 hits are red and span the full length of the query, which visually confirms that every hit covers 100% of the query with very high scores — consistent with what the Descriptions tab showed numerically.

**Alignments Tab**

![blastn_alingment](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/blastn_alingment.png?raw=true)

This tab shows the actual nucleotide-level alignment for each hit. The example shown is the top hit, Pseudomonas putida strain QAU90 PqqC.

At the top it shows the key statistics for this alignment: Score is 1424 bits for 771 bases, Expect (E value) is 0.0, Identities are 771 out of 771 which is 100%, Gaps are 0 out of 771 meaning no insertions or deletions, and Strand is Plus/Plus meaning both sequences run in the same direction.

Below that is the actual pairwise alignment displayed in blocks of 60 bases at a time. "Query" is your submitted sequence and "Sbjct" is the matching database sequence. The vertical lines between them indicate matching bases. Since this is a 100% identity match, every single position shows a vertical line with no mismatches. The numbers on the left and right of each row indicate the sequence positions being shown in that block, going from 1 to 771.

The Alignment view dropdown at the top lets you switch between Pairwise (shown here), Flat query-anchored, and other display formats depending on how you prefer to visualize the alignment.

**Taxonomy Tab**

![blastn_taxonomy](https://github.com/MuhammadMohsin404550/blast_guide/blob/main/asserts/blastn_taxonomy.png?raw=true)

This tab organizes the hits by their taxonomic classification rather than by score. It has three sub-tabs: Lineage, Organism, and Taxonomy — and the Lineage view is currently shown.

The top level shows the genus Pseudomonas with a Blast Name of g-proteobacteria (gamma-proteobacteria), which is the bacterial class this genus belongs to. It shows 10 total hits under this genus.

Below that, each species is listed with its individual score and number of hits. Pseudomonas putida has the highest score of 1424 with 1 hit, which is the exact match. Pseudomonas soli appears three times in the results (Number of Hits = 3), meaning three different strains of that species matched your query. The scores decrease as you go down the list, reflecting decreasing sequence similarity.

This tab is particularly useful for understanding the taxonomic distribution of your results and quickly seeing whether your sequence matches organisms from one genus or many different groups.
