---
header-includes: \usepackage{graphicx}
---

# H7N9 pathway analysis #
Douglas Wu

### Pathway enrichment ###

I took each table from the excel file and performed [**enrichr**](http://amp.pharm.mssm.edu/Enrichr/#about) (Fig \ref{fig:kegg_sets}).

\begin{figure}[ht]
\includegraphics[width=1\textwidth]{../figures/kegg_enrichment.png}
\caption{Top 20 KEGG pathways for each of the gene set. Negative log-transformed adjusted p-values for each of the top 20 KEGG pathways are plotted for each of the gene set. Red line indicate an adjusted p-value cutoff of 0.05. Bars are arranged in a descending order of negative log-trasnformted adjusted p-values. A higher negative log-trasnformted adjusted p-value indicate greater change in the corresponding pathway. }
\label{fig:kegg_sets}
\centering
\end{figure}


### Potential improvements ###

I figured out the two gene sets maybe originated from a single analysis but separated to up-regulated getens (set 1) and down-regulated genes (set 2). For pathway analysis, we usually use all of the genes for such an analysis, so that the analysis can be more comprehensive. Here, I combined both gene sets and performed a gene set enrichment analysis (GSEA; Fig \ref{fig:kegg_combined}) with respect to per oxygen index sensitivity.

\begin{figure}[ht]
\includegraphics[width=1\textwidth]{../figures/combined_kegg_enrichment.png}
\caption{KEGG pathways with significant changes. All genes from both tables were used in GSEA, only pathways with adjusted p-value $< 0.05$ are shown. Pathways with postivie normalized enrichment scores are enriched, and pathways with negative normalized enrichment scores are depleted.}
\label{fig:kegg_combined}
\centering
\end{figure}

From this result, we can also check if any of your interested pathway is really enriched or depleted. Using T-cell signaling pathways as an example (Fig \ref{fig:tcell}), most of the genes involved in this pathway have positive sensitivities to OI (clustered to the left of the plot).  


\begin{figure}[ht]
\includegraphics[width=1\textwidth]{../figures/hsa04660.png}
\caption{Enrichment plot of T-cell signaling pathways. Genes are ordered descendingly by their sensitivity to oxygen index as shown in the bottom panel and the heat map. In the middle panel, vertical lines indicate gene involved in the T-cell signaling pathways. Top plot shows the enrichment score of the pathway when genes were scanned in the order of sensitivity to oxygen index.  }
\label{fig:tcell}
\centering
\end{figure}

This analysis is more comprehensive/reliable if you can send me the results of the complete list of genes that you probed.