Data is being generated as e speak, as we tweet, as we send messages, and in various ither activities. Majority of this data exists in textual form, which is highly unestructured in nature.

# 1. Introduction to NLP
NLP is a branch of Data Science that consists of systematic processes for analyzing, understanding, and deriving information from the text data in a smart and efficient manner. Utilizing NLP and its components, one can organize the massive chunks of text data, perform numerous automated tasks and solve a wide range of problems such as:
    + automatic summarization
    + machine transklation
    + named entity recognition
    + relasionship extraction
    + sentiment analysis
    + speech recognition
    + topic segmentation
    
Some terms used:
    + tokenization: process of coverting a text into tokens
    + tokens: words or entities presents in the texts
    + text object: a sentence/a phrase/a word/an article
    
# 2. Text Preprocessing
Various types of noise are present in the text, so the data is not readly analyzable without any preprocessing. The entire process of cleaning and standarization of text, making it noise-free and ready for analysis is also known as text preprocessing. It is predominantly comprised of three steps:
    + noise removal
    + lexicon normalization
    + object standarization
        
The architecture of text processing pipeline:
    ··· raw text -> text cleaning pipeline -> cleaned text
    
    + text cleaning pipeline:
        + noisy removal
            + stopwords, URLs, entities, punctuations, etc.
        + word normalization
            + tokenization, lemmatization, stemming
        + word standarization
            + regular expression, lookup tables
        + note: apart from three steps, other types of text processing includes:
            + encoding-decoding noise
            + grammar checker
            + spelling correction

## 2.1 Noise removal
Any piece of text which is not relevant to the context of the data and the endoutput can be specified as the noise. For example, language stopwords (commonly used words of a language: is, am, the, of, in, etc.), URLs or links, social media entities (mentions, hashtags), punctuation, and industry specific words.

A general approach for noise removal is to prepare a dictionary of noisy entities, and iterate the text object by tokens elimininating those tokens which are present in the noisy dictionary (see `Code 1`).

Another approach is to use the regular expressions while dealing with special patterns of noise. In `Code 2` removes a regex pattern from the input text.

## 2.2 Lexicon Normalization
Another type of textual noise is about the multiple repressentations exhibited by single word. For example, "play", "player", "played", and "playing" are the differents variations of a word "play". Though they mean different but contextuallity all are similar. This step coverts all the disparities of a word into their normalized form, also known as a "lemma". 

Normalization is a pivotal step for feature engineering with text as it converts the high dimensional features (N different features) to the low dimensional space space (1 feature), which is an ideal ask for any ML model.

The most common lexicon normalization practices (see `Code 3`) are:
    + stemming: stemming is a rudimentary rule-based process of stripping the suffixes ("-ing", "-ly", "-es", "-s", etc) from a word.
    + lemmatization: lemmatization, on other hand, is an organized & step by step procedure of obtaining the root form of the word, it makes use of vocabulary (dictionary importance of words) and morphological analysis (word structure and grammar relations).
    
## 2.3 Object Standarization
Text data often contains words or phrases which are not presented in any standart lexical dictionaries. These pieces are not recognized by search engines and models. For example, acronyms, hashtags with attached words, colloquial slangs, etc. With the help of regula expressions, and manually prepared data dictionaries, this type of noise can be fixed, the `Code 4` uses a dictionary lookup method to replace social media slangs from a text.

# 3. Text to features (featurine engineering on text data)
To analyse a preprocessed data, it needs to be converted into features. Depending upon the usage, text features can be constructed using assorted techniques:
    + syntactical parsing
    + entities /N-grams/ word-based features,
    + statistical features, word embeddings
    
## 3.1 Syntactic parsing
Syntactical parsing involves the analysis of words in the sentence for grammar an their arrangement that shows the relationships among the words. Dependency Grammar and Part of Speech Tags are the important attributes of text syntactics.

### 3.1.1 Dependecy Trees
