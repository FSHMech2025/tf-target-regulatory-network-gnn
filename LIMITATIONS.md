# Limitations

Several limitations should be considered when interpreting the results.

1. **Incomplete regulatory knowledge**  
   The underlying regulatory network represents only a subset of biological regulatory interactions.

2. **External database coverage**  
   TRRUST provides curated regulatory evidence, but its coverage is incomplete. Therefore, interactions not supported by TRRUST cannot be considered false.

3. **Candidate-space dependence**  
   The generated candidate space depends on the construction of the original regulatory network and the candidate-generation strategy.

4. **Model configuration**  
   The GNN results correspond to the evaluated architecture, feature representation, training procedure, and experimental configuration. Other GNN architectures or feature sets may produce different results.

5. **Topology effects**  
   Network connectivity contains strong structural information. Degree-based ranking can therefore capture signals that may overlap with information learned by graph-based models.

6. **Annotation multiplicity**  
   External databases may contain multiple references or regulatory annotations for the same TF–target pair. Annotation counts should therefore be distinguished from unique interaction counts.

7. **Biological validation**  
   Computational validation against curated databases does not replace experimental biological validation.
