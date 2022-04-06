# Natural Language Processing with Python   
## Steven Bird, Ewan Klein, Edward Loper - O'Reilly Media
![[f4726515463e1699de63911141b0f35e.jpg]]

 Lê Anh
 NCF Global

#### Organization
Chapter 1 - 3: Conceptual difficulty, starting with a practical introduction to [[NLP]]. 
Chapter 4: [[structured programming]]
Chapter 5 - 7: fundamental topics in [[NLP]]: [[tagging]], [[classification]], and i[[nformation extraction]]
Chapter 8 - 10: [[parse sentence]], [[recognize syntactic structure]], and [[construct representations of meaning]]
Chapter 11: Conclutions

### CHAPTER 1.  Language Processing and Python
#### 1.1 Computing with Language: Texts and Words
We’ll address the following questions:
1. What can we achieve by combining simple programming techniques with large quantities of [[text]]?
2. How can we automatically extract key words and phrases that sum up the style and content of a [[text]]?
3. What tools and techniques does the Python programming language provide for such work?
4. What are some of the interesting challenges of natural language processing?

[[dispersion plot]] 

We use the term len to get the length of something, which we’ll apply here to the book of Genesis:
``` python
len(text3)
```
\>>44764

So Genesis has 44,764 words and punctuation symbols, or [[tokens]]. 
When we count the number of tokens in a [[text]], say, the phrase *to be* or *not to be,* we are counting occurrences of these sequences.
Get the [[vocabulary]] of the [[text]]:
```python
sorted(set(text3))
```
\>> ['!', "'", '(', ')', ',', ',)', '.', '.)', ':', ';', ';)', '?', '?)', 'A', 'Abel', 'Abelmizraim', 'Abidah', 'Abide', 'Abimael', 'Abimelech', 'Abr', 'Abrah', 'Abraham', 'Abram', 'Accad', 'Achbor', 'Adah', 'Adam', 'Adbeel', 'Admah', 'Adullamite', 'After', 'Aholibamah', 'Ahuzzath',...]
```python
len(set(text3))
```
\>> 2789
Although it has 44,764 [[tokens]], this book has only 2,789 distinct words, or [[word types]]. Our count of 2,789 items will include punctuation symbols, so we will generally call these unique items [[types]] instead of [[word types]].
When you repeatedly doing a single task with the same line of code, considering using python [[Python function]]. 


#### 1.2 A Closer Look at Python: Texts as Lists of Words
##### 1.2.1 Lists
What is a [[text]]? --> [[text]] 
A text can be present in [[python list]]. 
