# Experiment 16: NLP Techniques on Text Data in Python

**Author:** Ronit Mehta  
**PRN:** 25070123094  

---

## AIM
To study and implement fundamental Natural Language Processing (NLP) techniques on textual data using the Natural Language Toolkit (`nltk`) library in Python.

---

## Theory & Command Reference

Natural Language Processing (NLP) allows machines to interpret, process, and analyze human language. The `nltk` library provides built-in modules to break down and standardize text for analysis.

### 1. NLTK Initialization
Before processing text, the required linguistic datasets and models must be downloaded into the environment.
* `import nltk`: Imports the Natural Language Toolkit.
* `nltk.download('punkt')` / `nltk.download('punkt_tab')`: Downloads the required sentence tokenizer models.
* `nltk.download('stopwords')`: Downloads the corpus of common linguistic stopwords.
* `nltk.download('wordnet')`: Downloads the lexical database for English (required for Lemmatization).
* `nltk.download('averaged_perceptron_tagger')`: Downloads the model required for POS tagging.

### 2. Tokenization (Word & Sentence)
Tokenization is the process of breaking down a large paragraph of text into smaller, manageable units (tokens).
* `word_tokenize(text)`: Splits a given string into a list of individual words and punctuation marks.
* `sent_tokenize(text)`: Splits a given paragraph into a list of individual sentences based on punctuation and context.

### 3. Stopwords Removal
Stopwords are common words (e.g., "is", "the", "a", "in") that provide structural meaning but hold little analytical value.
* `stopwords.words('english')`: Retrieves a list of standard English stopwords.
* **List Comprehension Filter:** `[w for w in words if w.lower() not in stop_words]` iterates through the tokenized words and removes any word that exists in the stopwords set, resulting in a clean list of meaningful words.

### 4. Stemming & Lemmatization
Both techniques reduce words to their base or root forms, standardizing variations (e.g., "running", "runs", "ran").
* **Stemming:** A crude, rule-based approach that chops off word endings. It is fast but can result in non-dictionary words (e.g., "studies" becomes "studi").
  * `from nltk.stem import PorterStemmer`
  * `stemmer = PorterStemmer()`
  * `stemmer.stem(word)`: Applies the stemming algorithm to a word.
* **Lemmatization:** A more advanced, dictionary-based approach that analyzes morphological context to return proper base words (e.g., "studies" becomes "study").
  * `from nltk.stem import WordNetLemmatizer`
  * `lemmatizer = WordNetLemmatizer()`
  * `lemmatizer.lemmatize(word)`: Returns the linguistically correct lemma of the word.

### 5. Part-of-Speech (POS) Tagging
POS Tagging assigns grammatical labels (nouns, verbs, adjectives, etc.) to each token in a sentence.
* `pos_tag(words)`: Takes a list of tokenized words and returns a list of tuples, where each tuple contains the word and its corresponding POS tag (e.g., `NNP` for Proper Noun, `VBZ` for Verb).

### 6. Frequency Distribution
Frequency analysis helps identify the most prominent concepts or keywords within a text.
* `from nltk.probability import FreqDist`
* `fd = FreqDist(words)`: Calculates the frequency of each unique token in the provided list.
* `fd.most_common()`: Returns a sorted list of tuples displaying the words and their respective occurrence counts in descending order.

---


## Conclusion
In this experiment, the core foundations of Natural Language Processing were successfully explored and implemented using Python's `nltk` library. We demonstrated how raw text can be broken down into structural components via Word and Sentence Tokenization. Data noise was reduced by successfully filtering out English Stopwords. Furthermore, we contrasted Stemming and Lemmatization, highlighting the difference between rule-based truncation and dictionary-based morphological analysis. Finally, we applied Part-of-Speech (POS) tagging to understand grammatical context and utilized Frequency Distributions to quantify word occurrences. These sequential operations form the standard text-preprocessing pipeline required for advanced machine learning models, sentiment analysis, and search algorithms.
