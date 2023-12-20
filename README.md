## Summary
This project explores speech patterns in presidential primary debates to determine if general election winners exhibit unique policy positions or semantic/rhetorical patterns. Key findings include:
- Winners often belong to outlier clusters, suggesting that voters reward uniqueness.
- Within the same party, candidates show high similarity in specific policy topics.

## Research Objective
The goal of this study is to analyze if U.S. presidential primary candidates present distinct policy alternatives compared to their intra-party competitors. This involves:
- Assessing candidate grouping from 2000-2023.
- Identifying if nominees and winners showcase distinct policy stances and semantic patterns.
- Examining the role of uniqueness in specific policy topics in clustering patterns.

The methodology includes exploratory and inferential analysis through text processing, topic modeling, and clustering of debate discourse.

## Background
- **Partisanship Increase**: McCarty (2019) notes a significant rise in legislative partisanship since the mid-1970s.
- **Party Unity Votes**: From 1970 to 2022, party unity votes increased from 32% to 70% (Shi Li, 2021).
- **Voting Predictions**: By the 2000s, the primary dimension of congressional votes was the conservative vs. liberal coalition (McCarty, 2019).

These trends suggest a standardization of party policies, potentially reducing 'true choice' for voters.

## Data
### Source
- Obtained from The American Presidency Project (APP) (Peters & Woolley, 2016).
- Transcriptions of presidential primary debates were manually collated from the APP’s website.

### Generation Process
- The corpus includes final 8 Republican/Democratic presidential primary debates from each election cycle (2000-2023).
- Each document represents a candidate’s speech in a specific debate round.
- The final dataset consists of 9259 rows of candidate responses.

- ## Techniques and Findings

### Techniques
1. **Topic Modelling with BERT**
   - **Approach**: Employed BERT-based topic modeling to handle semantic context and noise in debate speeches.
   - **BERT's Role**: Utilizes transformers for generating contextually informed word embeddings. Document-level embeddings are clustered to identify prominent topics.
   - **Evaluation**: Manual assessment of topics through representative documents and bag of words representations.

2. **Word and Document Embeddings**
   - **Method**: Used Doc2Vec for generating document-level embeddings, extending the Word2Vec model.
   - **Word2Vec**: Analyzes word occurrence probability within a surrounding word set, capturing linguistic context.
   - **Doc2Vec**: Generates embeddings for larger text blocks, considering a unique identifier for each document.

3. **Agglomerative Hierarchical Clustering**
   - **Process**: Concatenated documents for each candidate into a single document for unique word embedding representation.
   - **Methodology**: Employed agglomerative hierarchical clustering with Ward's linkage to minimize within-cluster variance.
   - **Evaluation**: Utilized the cophenetic correlation coefficient to measure cluster quality.

4. **Cosine Similarity**
   - **Purpose**: Explored cosine similarities between speakers’ word embeddings to determine similarity in topics.
   - **Method**: Cosine similarity measures the angle between two vectors, indicating the degree of similarity.

### Findings
1. **Topic Modelling**
   - Identified 51 policy-relevant topics out of 119, ensuring their occurrence is not by chance.
   - Limitation: Secondary topics may be inconsistent due to the stochastic nature of the algorithm.

2. **Hierarchical Clustering**
   - Found 17 distinct clusters among 63 presidential candidates.
   - Notable Observation: All elected presidents from 2000 to 2020 were in outlier clusters, indicating a preference for uniqueness in policy positions or speech patterns.

3. **Topic Wise Similarities**
   - High degree of similarity among presidential candidates within a party on various topics.
   - Winners tend to be the most or second most dissimilar within their parties, though differences are marginal.
   - Limitation: Methodology may not clearly distinguish nuanced policy position differences.

## Conclusion
This analysis highlights the importance of unique policy positions and speech patterns in presidential primaries. While candidates within a party show high similarity, those with distinct stances or rhetoric tend to stand out and are often favored by voters. The study underscores the need for nuanced analysis in understanding voter preferences and candidate differentiation.
