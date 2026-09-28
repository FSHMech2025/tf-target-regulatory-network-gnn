# Discussion

## Main Findings

This study evaluated graph neural network (GNN)-based ranking of candidate transcription factor (TF)–target regulatory interactions and compared the learned ranking with a simple topology-based degree baseline.

The candidate space contained 3,926,526 TF–target pairs. External validation using TRRUST identified 2,607 candidate pairs with supporting curated regulatory evidence.

Across the evaluated ranking strategies, the degree-based baseline achieved the highest external validation precision at Top-5,000, recovering 47 TRRUST-supported interactions. The raw GNN recovered 20 interactions, while the embedding-aware residual ranking recovered 3.

These findings indicate that, in the current network and experimental setting, network topology provided a strong signal for recovering known regulatory interactions. The evaluated GNN did not demonstrate an additional advantage over the degree baseline.

## Interpretation

The result does not indicate that GNNs are inherently unsuitable for regulatory interaction prediction. Rather, it suggests that the information available to the current model and architecture may overlap substantially with structural information already captured by simple network connectivity.

This observation highlights the importance of strong and interpretable baselines in biological network machine learning. A more complex model should demonstrate improvement beyond simple structural features before its additional complexity can be considered useful.

The comparison also demonstrates that model performance should be interpreted together with the characteristics of the underlying biological network. Highly connected nodes and network structure can strongly influence candidate rankings, and these effects may be captured by degree-based methods without requiring learned representations.

## External Validation

TRRUST provided an independent source of curated regulatory evidence for evaluating the candidate rankings.

Among the validated interactions, TRRUST annotations included activation, repression, and unknown regulatory effects. Because individual TF–target pairs can have multiple annotations or references, annotation counts should be distinguished from counts of unique validated interactions.

The presence of externally supported interactions in the candidate space provides evidence that the generated candidate space contains biologically meaningful relationships. However, absence from TRRUST should not be interpreted as evidence that a predicted interaction is biologically incorrect.

## Implications

The results support a practical principle for biological graph learning:

**Complexity should be justified by measurable improvement over strong structural baselines.**

For this dataset and experimental configuration, the degree baseline provided a strong and interpretable reference and outperformed the evaluated learned rankings under the TRRUST validation criterion.

Future improvements should therefore focus on introducing information that is complementary to network topology rather than simply increasing model complexity.
