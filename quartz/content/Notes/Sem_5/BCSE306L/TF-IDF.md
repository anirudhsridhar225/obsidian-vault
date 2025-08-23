IDF- Inverse document frequency
- it is the measure of importance of a word
- takes into account the entire collection
- log of ratio of total number of documents to number of documents containing the term
- goal is to penalize words that are common across all documents

![[{8A6B338E-F689-4D11-B2E5-695ECD3E7A7F}.png]]

# TF-IDF
- product of tf and idf
- gives more weightage to the word that is rare in the corpus

$TF-IDF(t,d,D) = TF(t,d)xIDF(t,D)$

![[{DEBE2AE7-BF67-413D-9643-A875BEA925C4}.png]]
