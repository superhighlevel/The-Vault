---
aliases: TF, Term Frequency, term frequency
---
#### TF-Formular
$$tf(t, d)=\dfrac{f_d(t)}{\underset{w\in d}{max}f_d(w)}$$
where:
- $t$ is a [[tokens|token]] or term
- $d$ is documents
- $f_d(t)$ is  the frequency of token $t$
- $\underset{w\in d}{max}f_d(w)$ is max numbers of word($w$) in $d$ 
#### Term Frequency
The Term Frequency (TF) representation of a phrase, sentence, or document   as *weighted* words *proportionally* to their *frequency*.$$tf(t, d)=\dfrac{f_d(t)}{\underset{w\in d}{max}f_d(w)}$$
where:
- $t$ is a [[tokens|token]] or term
- $d$ is documents
- $f_d(t)$ is  the frequency of token $t$
- $\underset{w\in d}{max}f_d(w)$ is max numbers of word($w$) in $d$ 
##### Examples
   ```
   Fruit flies like time flies a fruit
   --> [1, 2, 2, 1, 1, 0, 0, 0]
   ```
Notice that each entry is a count of the number of times the corresponding word appears in the sentence (corpus)
##### Weakness
In TF, common words such as “claim” do not add anything to our understanding of a specific patent. Conversely, if a rare word (such as “tetrafluoroethylene”) occurs less frequently but is quite likely to be indicative of the nature of the patent document.
   