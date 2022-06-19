# Exercises {#exercises}

Here you can find assignments on different topics. 

TIPS:

   - Add comments that explain what each line or lines of code do. This helps you and others to understand your code and find bugs. Furthermore, it is easier for you to reuse the code, and it promotes transparency.
   - Interpret results by comparing them to literature. List main findings, so that results can easily be understood by others without advanced data analytics knowledge.
   - Avoid hard-coding. Use variables which get values in the beginning of the pipeline. That way it is easier for you to modify parameters and reuse the code.
   
## Reproducible reporting {.unlisted .unnumbered}

1. Create an R Markdown file.
2. Add a code chunk and give a name for it.
3. Import e.g., iris dataset, and create a dotplot with a title.
4. Create another code chunk and plot. 
5. Adjust the size of the figure, and choose from the options that the code chunk will not be shown in the report.
6. Add some text.
7. Add an R command within the text.
8. Create an HTML file from the Rmd file.

## Introduction to TreeSummarizedExperiment (TreeSE) {.unlisted .unnumbered}

Import data from CSV files to TreeSE.

1. Import data.
2. Construct a TreeSE.
3. Check that importing is done correctly. E.g., you can choose random samples and features,
and check that their values equal between raw files and TreeSE.

Functions that might be useful: DataFrame, TreeSummarizedExperiment, matrix, rownames, colnames, SimpleList

## Data exploration {.unlisted .unnumbered}

1. Please install the latest development version of mia from GitHub.
2. Load experimental dataset from mia.
3. What are the dimensions? (How many samples there are, and how many taxa in each taxonomic rank)?
4. Calculate library size.
5. Summarize sample metadata variables. (How many age groups, how they are distributed? 0%, 25%, 50%, 75%, and 100% quantiles of library size?)
6. Create two histograms. Another shows the distribution of absolute counts, another shows how CLR transformed values are distributed.
7. Visualize how relative abundances are distributed between taxa in samples.
8. Calculate Shannon diversity index. Is it significantly different between vegan and mixed diet?

Functions that might be useful: nrow, ncol, dim, summary, table, quantile, unique, transformSamples, ggplot, wilcox.test, addPerCellQC, agglomerateByRank, estimateDiversity, plotAbundance

## Differential abundance analysis {.unlisted .unnumbered}

1. Please install the latest development version of mia from GitHub.
2. Load experimental dataset from mia.
3. Compare abundances of each taxa between groups. First, use Wilcoxon or Kruskall-Wallis test. Then use some other method dedicated to microbiome data. 
4. Summarize findings by plotting a taxa vs samples heatmap. Add column annotation that tells the group of each sample, and row annotation that tells whether the difference of certain taxa was statistically significant.
5. Choose statistically significant taxa and visualize their abundances with boxplot & jitterplot.

Functions that might be useful: wilcox.test, kruskal.test, ggplot, pheatmap, ComplexHeatMap::Heatmap, ancombc, aldex2, maaslin2, agglomerateByRank, transformSamples, transformFeatures, subsetByPrevalentTaxa

## Basics of community composition {.unlisted .unnumbered}

1. Please install the latest development version of mia from GitHub.
2. Load experimental dataset from mia.
3. Create a PCoA with Aitchison dissimilarities. How much coordinate 1 explains the differences? How about coordinate 2?
4. Create dbRDA with Bray-Curtis dissimilarities on relative abundances. Use PERMANOVA. Can differences between samples be explained with variables of sample meta data? 
5. Analyze diets' association on beta diversity. Calculate dbRDA and then PERMANOVA. Visualize coefficients. Which taxa's abundances differ the most between samples? 
6. Interpret your results. Is there association between community composition and location? What are those taxa that differ the most; find information from literature.

Functions that might be useful: runMDS, runRDA, anova.cca, transformSamples, agglomerateByRank, ggplot, plotReducedDim

## Introduction to MultiAssayExperient (MAE) {.unlisted .unnumbered}

1. Create TreeSE data containers from individual CSV files.
2. Combine TreeSE into MAE.
3. Check that each individual experiment of MAE equals corresponding TreeSE.
4. Take a subset of MAE (e.g., 10 first samples), and observe the subsetted MAE.

Functions that might be useful: DataFrame, TreeSummarizedExperiment, matrix, rownames, colnames, MultiAssayExperiment, ExperimentList, SimpleList

## Introduction to multiomics {.unlisted .unnumbered}

1. Load experimental dataset from microbiomeDataSets (e.g., HintikkaXOData).
2. Analyze correlations between experiments. (Taxa vs lipids, Taxa vs biomarkers, Lipids vs biomarkers)
3. Agglomerate taxa data.
4. Apply CLR to taxa data, apply log10 to lipids and biomarkers.
5. Perform cross-correlation analyses and visualize results with heatmaps. (Use Spearman coefficients)
6. Is there significant correlations? Interpret your results.

Functions that might be useful: pheatmap, ComplexHeatMap::Heatmap, ggplot, transformSamples, testExperimentCrossAssociation
