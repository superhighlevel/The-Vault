---
aliases: Inverse Document Frequency, idf
---
#### IDF Formular
$$TDF(t,  D)=log(\dfrac{|D|}{|{d \in D: t \in d}|})$$
where 
- $n_w$ is the number of  documents *contants* the word $w$.
- N is the total number of documents.
#### IDF
The **Inverse Document Frequency** (IDF) representation *penalizes* common [[tokens]] and rewards rare tokens in the vector representation.  
The $IDF(w)$ of a [[tokens|token]] $w$ is defined with respect to a [[corpus]] as:$$TDF(t,  D)=log(\dfrac{|D|}{|{d \in D: t \in d}|})$$
where 
- $n_w$ is the number of  documents *contants* the word $w$.
- N is the total number of documents.