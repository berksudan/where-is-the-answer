# A Question Answering Tool: "Where is the answer?" ("Cevap Nerede?")

This is a junior project at Yildiz Technical University Computer Engineering Department and advised by Assoc. Prof. M. Fatih Amasyalı.
Basically, this tool finds the location of the sentence containing *the answer* of *given questions* and compares the performance results of some basic NLP methods. 
According to results we discuss the performance of various methods. Which one is the most effective to find where is the answer on a text.

Test-set consists of Turkish Child Tales and contains 500 questions and 71 tales in different size and complexity.

## Methods
### Method 0: Select Randomly
In this method, we randomly select sentences in the text and return these sentences in response. This method is our base-line, we tried to improve this results with the following methods.

### Method 1: Basic Word Sameness
In this method, Common words between question-text and sentence texts are counted. The idea behind this method is "The more common words, the more likely the sentence is to be the answer to the given question.".

### Method 2: Similarity of the First Six Characters
Turkish is a suffix-based language which most root words contain 6 letter. Therefore we compare words within six letters. And the performance is getting more.

### Method 3: Constructing sentence vectors with FastText
We decided to use fasttext to get word embeddings. We used wiki.tr (compiled by FastText team from Turkish Wikipedia) file as train set. When we got word embeddings,we constructed sentences as arithmetical average of words. First we created word vectors and then we sum all the words. Finally we calculated the arithmetic average to get average vector and this vector represents the whole sentence.

To find similarity between sentences and question we used cosine similarity. This method approaches sentences as atomic units.  

### Method 4: Jaccard Similarity
We implemented jaccard similarity into words to find where is the answer.

### Method 5: Constructing word vectors with FastText (using Cosine Similarity)
To increase performance we tried new method. In this method we approach words as atomic unis of a text. We calculate similarity of question and sentence texts using cosine similarity.

### Method 6: Constructing word vectors with FastText (using Euclidean Similarity)
Uses similar with method5 algorithm to find word embeddings but this method use euclidean similarity to compare sentences.

## Contributors
- *Berk Sudan*, [GitHub](https://github.com/berksudan), [LinkedIn](https://linkedin.com/in/berksudan/)
- *Burak Tahtacı*, [GitHub](http://buraktahtaci.com/contact),  [LinkedIn](https://linkedin.com/in/tahtaciburak)

