# BOO

This repository contains the code for my BOO project.

In this project, I designed a new way to score WGCNA module activity. Currently, eigengene scoring is the golden standard.
However, eigengene scoring has its limitations, as it does not account for network structure of genes in a module.

To overcome this problem, I designed a topology-based scoring method, Weighted Directed Random Walk (wDRW).
wDRW was adapted from Directed Random Walk strategies, that were designed to infer pathway acivity in predefined pathways.
The specific formulas for the wDRW module activity inference technique can be read in my BOO report or in the
hPHH_DRW.Rmd and hRPTEC_DRW.Rmd files.

The wDRW was compared with the eigengene scores on different evaluation metrics (hPHH_EG.Rmd, hPHH_DRW.Rmd, hRPTEC_EG.Rmd, hRPTEC_DRW.Rmd). 
First, the (weighted) proportion of activated genes in a module were plotted and fitted against the scoring methods. 
wDRW provided a beter fit on these metrics in both PHH and RPTEC.

Then wDRW was compared with eigengene using heatmaps (Heatmap.Rmd) of selected compounds from Hugo (RPTEC) and from the TXG-MAPr publication (PHH).
wDRW showed to filter out a lot of 'noisy' scores, while the top eigengene scores retained the top wDRW scores.

Then the top k scoring module and compound Reactome enrichments were compared with the Comparative Toxicogenomics Database (CTD) compound enrichment for their matching accuracy (Target_Matching.Rmd). wDRW showed a better
enrichment matching accuracy than eigengene in both PHH and RPTEC, indicating that it might give more toxicologically relevant results.

Finally, the most and least correlated modules between wDRW and Eigengene were evaluated in both PHH and RPTEC (Correlation_EG_vs_wDRW.Rmd).