# ASmining
### AS knowledge-based signature file (.tsv) description
<table bgcolor="white">
<tr>
  <td width="200"></td>
  <td align="center"><b>Description</b></td>
</tr>
<tr>
  <td align="center" bgcolor="white"><b>Pathway</b></td>
  <td bgcolor="white">Pathway names</td>
</tr>
<tr>
  <td align="center" bgcolor="white"><b>Gene</b></td>
  <td>Official gene symbol</td>
</tr>
<tr>
  <td align="center" bgcolor="white"><b>Frequency</b></td>
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
<br/>
1) mining.tsv<br/>
&nbsp;&nbsp;&nbsp;Data collection for pathway, and splicing genes to include additional occurrence measurements, and profile.<br/>
&nbsp;&nbsp;&nbsp;User can select refined gene sets cutting off by rank measurements.<br/>
<br/>
2) mining.gmt<br/>
&nbsp;&nbsp;&nbsp;Splicing gene set collection for each pathway is provided by a gmt format file.<br/>
<br/>
