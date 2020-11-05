# A Question Answering Tool: "Where is the answer?" ("Cevap Nerede?")

This is a junior project at Yildiz Technical University Computer Engineering Department and advised by Assoc. Prof. M. Fatih Amasyalı.
Basically, this tool finds the location of the sentence containing *the answer* of *given questions* and compares the performance results of some basic NLP methods. 
According to results we discuss the performance of various methods. Which one is the most effective to find where is the answer on a text.

Test-set consists of Turkish Child Tales and contains 500 questions and 71 tales in different size and complexity.

## Methods
### Method 0: Select Randomly
In this method, we randomly select sentences in the text and return these sentences in response. This method is our base-line, we tried to improve this results with the following methods.

### Method 1: Basic Word Equality
In this method, Common words between question-text and sentence texts are counted. The idea behind this method is "The more common words, the more likely the sentence is to be the answer to the given question.".

### Method 2: Similarity of the First Six Characters
Turkish is an agglutinating language which most of the word stems contain 6 character at most. Therefore we compare words with their first six characters. So, the performance has increased.

### Method 3: Constructing sentence vectors with FastText
In this method, we decided to use FastText to extract word embeddings. We used wiki.tr (compiled by FastText team from Turkish Wikipedia) file as train set. When we have word embeddings, we treat sentences as arithmetic mean of the defined words. First, we created word vectors and then summed all the word vectors. Finally, we calculated the arithmetic mean to obtain the average vector which represents the whole sentence.

To find similarity between sentences and question, we used cosine similarity. This method sees sentences as atomic units.  

### Method 4: Jaccard Similarity
In this method, Wwe added a jaccard similarity operation to locate the answer in text.

### Method 5: Constructing word vectors with FastText (using Cosine Similarity)
In this method, we use words as atomic units of a text. We calculate similarity of question and sentence texts using cosine similarity.

### Method 6: Constructing word vectors with FastText (using Euclidean Similarity)
In this method, a module is implemented to find word embeddings, similar to method 5, along with the euclidean similarity metric to compare sentences.

## Contributors
- *Berk Sudan*, [GitHub](https://github.com/berksudan), [LinkedIn](https://linkedin.com/in/berksudan/)
- *Burak Tahtacı*, [GitHub](http://buraktahtaci.com/contact),  [LinkedIn](https://linkedin.com/in/tahtaciburak)

