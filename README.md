# exon_usage_analysis

## Various analysis versions

### Simple tx ratio vs Gene ratio

This analysis can be found in tx_ratio_vs_gene_ratio branch.

For each transcript $t_i$ of a given gene $g$, we compute a score that contrasts the transcript-level fold-change between conditions with the gene-level fold-change. Let $t_{i,a}$ and $t_{i,
b}$ denote the average expression of transcript $t_i$ in conditions $a$ and $b$, and let $g_a$ and $g_b$ denote the average expression of the parent gene in conditions $a$ and $b$, respectiv ely. The score is defined as:

$$S_i = \log2{\left(\frac{\left(\frac{t_{i,b} + 1}{t_{i,a} + 1}\right)}{\left(\frac{g_b + 1}{g_a + 1}\right)}\right)}$$ or equivalently:

$$S_i = \log_2\!\left(\frac{t_{i,b} + 1}{t_{i,a} + 1} \cdot \frac{g_a + 1}{g_b + 1}\right)$$

A pseudocount of 1 is added to all terms to handle zero counts. $S_i > 0$ indicates that transcript $t_i$ is proportionally more induced in condition $b$ than the overall gene, while $S_i <
0$ indicates it is proportionally more repressed. Transcripts with the highest $|S_i|$ are nominated as candidates for a transcript usage switch.

### Isoform usage with IsoformSwitchAnalyzeR

This analysis can be found in isoform_switch_analyzeR branch.
