- it is an exact retrieval model
- each document is treated as a bag of words/terms
- collection of documents D, $V = {t_1, t_2,... t_{|V|}}$
  V --> vocab
- a weight is associated with each term $t_i$ of a document $d_i$ belonging to D. if not in $d_j$, weight is 0  
- query terms are combined using boolean operators

# Retrieval
- given a boolean query, the system retrieves every document that makes the query logically true.
- called exact match
- results are usually quite poor because term frequency is not considered.

