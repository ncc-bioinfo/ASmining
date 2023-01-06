# ASmining
### AS knowledge-based signature file (.tsv) description
<table>
<tr>
  <td width="200"></td>
  <td align="center"><b>Description</b></td>
</tr>
<tr>
  <td align="center"><b>Pathway</b></td>
  <td>Pathway names</td>
</tr>
<tr>
  <td align="center"><b>Gene</b></td>
  <td>Official gene symbol</td>
</tr>
<tr>
  <td align="center"><b>Frequency</b></td>
  <td>The number of literatures to contain sentences existing both pathway and gene</td>
</tr>
<tr>
  <td align="center"><b>Log_likelihood</b></td>
  <td>Log likelihood of the co-occurrence of pathway and gene pairs</td>
</tr>
<tr>
  <td align="center"><b>Correlation</b></td>
  <td>Correlation coefficient of the co-occurrence of pathway and gene pairs</td>
</tr>
<tr>
  <td align="center"><b>Bayesian</b></td>
  <td>Bayesian probability of the co-occurrence of pathway and gene pairs</td>
</tr>
<tr>
  <td align="center"><b>Rank</b></td>
  <td>Co-occurrence rank merged from log-likelihood, correlation, and Bayesian probability</td>
</tr>
<tr>
  <td align="center"><b>Pubmed_ID</b></td>
  <td>Literature IDs to acquire corresponding information</td>
</tr>
</table>
1) mining.tsv<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Data collection for pathway, and splicing genes to include additional occurrence measurements, and profile.<br/>
&nbsp;&nbsp;&nbsp;&nbsp;User can select refined gene sets cutting off by rank measurements.<br/>
<br/>
2) mining.gmt<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Splicing gene set collection for each pathway is provided by a gmt format file.<br/>

### AS transcriptome-based signature file (.tsv) description
<table>
<tr>
  <td width="200"></td>
  <td align="center"><b>Description</b></td>
</tr>
<tr>
  <td align="center"><b>Pathway</b></td>
  <td>Out of 42 pathways under analysis</td>
</tr>
<tr>
  <td align="center"><b>Cancer</b></td>
  <td>Out of 16 TCGA cancer types</td>
</tr>
<tr>
  <td align="center"><b>Gene</b></td>
  <td>Symbol | ID</td>
</tr>
<tr>
  <td align="center"><b>Strand</b></td>
  <td>+ / -</td>
</tr>
<tr>
  <td align="center"><b>AS_event_type</b></td>
  <td>RI (Retained intron); A3 (Alternative 3' splice site); A5 (Alternative 5' splice site); MX (Mutual exclusive exons); SE (Skipped exon)</td>
</tr>
<tr>
  <td align="center"><b>AS_event_ID</b></td>
  <td>ID following SUPPA2 format</td>
</tr>
<tr>
  <td align="center"><b>Text_mining_gene</b></td>
  <td>"Observed", when the AS gene is also identified by text-mining analysis; "", otherwise</td>
</tr>
<tr>
  <td align="center"><b>AS_event_importance</b></td>
  <td>Measured as the learned Random Forest (RF) model's feature importance (higher, the more important)</td>
</tr>
<tr>
  <td align="center"><b>AS_event_correlation</b></td>
  <td>Measured as the spearman's correlation between GSVA scores (degree of pathway enrichment) and PSI values</td>
</tr>
<tr>
  <td align="center"><b>Cancer_recurrence</b></td>
  <td>Cancer type recurrence (% out of 16 cancer types) of which the AS event shows positive feature importance (RF model)</td>
</tr>
</table>
1) CANCER_PATHWAY_all.tsv<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Final AS signature set.<br/>
&nbsp;&nbsp;&nbsp;&nbsp;Top 100 AS events of highest positive feature importance were extracted from the learned Random Forest model (transcriptome-based analysis). Next, the AS signatures of compact size were augmented with our knowledge-based splicing gene signatures revealing high recurrence (>50%) of positive feature importance.<br/>
<br/>
2) CANCER_PATHWAY_txm.tsv<br/>
&nbsp;&nbsp;&nbsp;&nbsp;AS signature set of which genes were also identified by our text-mining analysis (knowledge-based)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;"Text_mining_gene" column == "Observed"<br/>
<br/>
3) CANCER_PATHWAY_txmRec(N).tsv<br/>
&nbsp;&nbsp;&nbsp;&nbsp;AS signature set satisfying both conditions: 1) AS genes were identified by the knowledge-based analysis and 2) cancer type recurrence (AS event shows positive feature importance) bigger than N% (out of 16 cancer types)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;"Text_mining_gene" column == "Observed" and "Cancer_recurrence" column > N%
