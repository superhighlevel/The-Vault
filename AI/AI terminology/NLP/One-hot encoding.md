---
aliases: One-hot encoding, One hot encoding, one-hot encoding, one hot representation, one-hot pepresentation
---

#### One-hot encoding
One-hot encoding technique is a common and basic way of turning a word into a [[One-hot vector]].  Starts with a zero vector, and sets as 1 the corresponding *entry* in the vector if the word is present in the sentence or document.

##### Examples
```
Time flies like an arrow.  
Fruit flies like a banana.
```
   [[tokens|Tokenizing]] the sentences, ignoring punctuation, and treating everything as lowercase, will yield a [[vocabulary]] of size 8: 
   ```
   {time, fruit, flies, like, a, an, arrow, banana}
   ```
   So we have One-hot embedding of the samples:
   ```
   Time flies like an arrow. --> [1, 0, 1, 1, 0, 1, 1, 0]
   Fruit flies like a banana. --> [0, 1, 1, 1, 1, 0, 0, 1]
   ```
   