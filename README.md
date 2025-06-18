# BOO

This repository contains the code for my BOO project.

In this project, I designed a new way to score WGCNA module activity. Currently, eigengene scoring is the golden standard.
However, eigengene scoring has its limitations, as it does not account for network structure of genes in a module.

To overcome this problem, I designed a topology-based scoring method, Weighted Directed Random Walk (wDRW).
wDRW was adapted from Directed Random Walk strategies, that were designed to infer pathway acivity in predefined pathways.
The specific formulas for the wDRW module activity inference technique can be read in my BOO report or in the
[hPHH_DRW.html](DRW_hPHH/output/hPHH_DRW) and [hRPTEC_DRW.html](DRW_hRPTEC/output/hRPTEC_DRW) files.

The wDRW was compared with the eigengene scores on different evaluation metrics ([hPHH_EG.html](Eigengene_hPHH/output/hPHH_EG), [hPHH_DRW.html](DRW_hPHH/output/hPHH_DRW), [hRPTEC_EG.html](Eigengene_hRPTEC/output/hRPTEC_EG), [hRPTEC_DRW.html](DRW_hRPTEC/output/hRPTEC_DRW)). 
First, the (weighted) proportion of activated genes in a module were plotted and fitted against the scoring methods. 
wDRW provided a beter fit on these metrics in both PHH and RPTEC.

Then wDRW was compared with eigengene using heatmaps ([Heatmap.Rmd](Evaluation/Heatmap/Heatmap.Rmd)) of selected compounds from Hugo (RPTEC) and from the TXG-MAPr publication (PHH).
wDRW showed to filter out a lot of 'noisy' scores, while the top eigengene scores retained the top wDRW scores.

Then the top k scoring module and compound Reactome enrichments were compared with the Comparative Toxicogenomics Database (CTD) compound enrichment for their matching accuracy ([Target_Matching.html](Evaluation/CTD_Matching/output/Target_Matching.html)). wDRW showed a better
enrichment matching accuracy than eigengene in both PHH and RPTEC, indicating that it might give more toxicologically relevant results.

Finally, the most and least correlated modules between wDRW and Eigengene were evaluated in both PHH and RPTEC ([Target_Matching.html](Evaluation/Correlation_EG_vs_wDRW/output/Correlation_EG_vs_wDRW.html)).
