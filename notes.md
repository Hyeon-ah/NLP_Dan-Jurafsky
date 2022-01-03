# 4.1 Naive Bayes Classifiers 
+ = 베이지안 확률 
+ = probabilistic classifier 
+ = A bag-of-words <br>
+ an unordered set of words with position ignored, **only freqs** <br>

```
y가 x에 나타날 확률: P(x|y) = P(y|x)P(x) / P(y) <br>
d가 c에 나타날 확률:P(c|d) = P(d|c)P(c) / P(d) <br>
```

# 6.3 Words and Vectors
+ co-occurrence matrix에 기반을 둔 Vector/distributional models.
+ co-occurrence matrix = a term-document matrix
+ 각 row는 단어(number of times the word occurs), 각 colums은 doc(in the document.
+ vector = a list of array of numbers = |V| =the length of the vector (vocab size)
+ vector space = a collection of vectors(grouped by its dimension)
+ vector space의 숫자 순서는 meaningful.

## 6.3.2 Words as vectors
+ similar words have similar vectors because they tend to occur in similar documents ? <br>

### Term-document matrix
+ each row represents a word in the vocabulary
+ each column represents a document from some collection of documents.
+ 즉, 행의 단어가 열의 문서에 나오는 횟수 <br>

### Word-word co-occurrence matirx<br>
+ 관계 기반
```
This matrix is thus of dimensionality |V|x|V|,
and each cell records the number of times the row (target) word 
and the column (context) word co-occur in some context in some training corpus.
```
+ ex) `+-4`word window: 양 옆으로 4개의 단어 추출

# 6.7 PMI(Pointwise Mutual Information (PMI)
+ 확률을 모두 구해서 log식에 계산
+ ex) A, B 단어가 있을 때,

```
1. 전체 단어에서 A가 나올 확률
2. 전체 단어에서 B가 나올 확률
3. 전체 단어에서 A와 B가 동시에 나올 확률
```
1, 2, 3을 모두 구해서 log 계산식에 넣어 계산. 
+ Positive PMI (called PPMI)가 높을 수록 두 단어가 4 window(본 예시는 4개의 window를 봤음.) 안에 있을 빈도수(확률?)가 높음.
+ For instance,
```
P(w=information,c=data) = 3982 / 11716 = 0.3399
P(w=information) = 7703 / 11716 = 0.6575
P(c=data) = 5673 / 11716 = 0.4842
ppmi(information,data) = log2(0.3399/(0.6575*0.4842)) = 0.0944
```
