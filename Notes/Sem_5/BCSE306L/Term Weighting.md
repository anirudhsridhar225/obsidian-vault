Term weights consist of 2 components:
1. Local: how imp is the term in this doc
2. Global: how imp is the term in the collection

- terms that appear often in a document should get high weights
- terms that appear in many documents should get low weights
- we capture this by using:
	- term frequency (local) [[TF]]
	- inverse document frequency (global) [[TF-IDF]]