# Natural Language Processing

- [tracking progress](http://nlpprogress.com/)

## Tasks

### Simple tasks

- tokenization
	- break down text
	-  `word_tokenize(text)`, `sentence_tokenize(text)`
- stopword removal
	- nltk.corpus 
	- `stopwords.words('english')`
- N-Grams
	- `nltk.collocations`
	- `BigramCollocationFinder.from_words(words)`
- Word Sense Disambiguation
	- identify meaning based on context
	- wordnet
		- Synset: one single representation of a word
	- `from nltk.wsd import lesk`
- POS tagging
	- `nltk.pos_tag`
- stemming
	- same words with different ending
	- `nltk.stem`
	- e.g. LancasterStemmer

### More complex tasks

- auto summarization
	- rule-based:
		- finding the most important word (word frequemcy) -> significance score for the word
		- sentence significance -> significance score for the sentence
		- pick the most important sentences
- spam detection
	- static rules
	- dynamic approach = machine learning
- sentiment analysis
- chatbots
	- Rasa: framework
		- open source
		- development
			- yaml files for description
			- python code for actions

## Data Representation

- Term Frequency
- TF-IDF

## Models

- mathematical equation or a set of rules, depening on the task
- classification
	- Naive Bayes
	- SVM
- clustering
	- K-Means
	- Hierarchical Clustering

## Preprocessing

- urllib2: to download html page
- BeautifulSoup: to parse webpages
- nltk.probability: FreqDist