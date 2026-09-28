# Conclusion

This study investigated graph neural network (GNN)-based ranking of candidate transcription factor (TF)–target regulatory interactions and compared the learned ranking with a topology-based degree baseline.

A large candidate space of 3,926,526 TF–target pairs was generated from the regulatory network and evaluated using externally curated interactions from TRRUST. Among the candidate pairs, 2,607 were supported by TRRUST evidence.

In the evaluated experimental setting, the degree-based baseline achieved higher external validation precision than the raw GNN and embedding-aware residual rankings at Top-5,000, recovering 47 validated interactions compared with 20 for the raw GNN and 3 for the embedding-aware residual approach.

These results demonstrate that simple network topology can provide a strong and interpretable signal for regulatory interaction ranking. The findings also emphasize that the value of graph-based machine learning should be assessed relative to strong structural baselines rather than model complexity alone.

The study provides a reproducible framework for comparing learned graph representations with topology-based approaches in biological regulatory networks and establishes a foundation for future work incorporating richer biological features and complementary sources of regulatory evidence.
