# LughaatNLP

LughaatNLP is the first comprehensive Urdu language preprocessing library developed for NLP tasks in Pakistan. It provides essential tools for tokenization, lemmatization, stop word removal, and normalization specifically tailored for the Urdu language.

<p align="center">
  <img src="https://i.imgur.com/6lKyQlo.png" alt="Alt Text" width="500" height="500">
</p>

## Features

- **Tokenization**: Breaks down Urdu text into individual tokens, considering the intricacies of Urdu script and language structure.
- **Lemmatization**: Converts inflected words into their base or dictionary form, aiding in text analysis and comprehension.
- **Stop Word Removal**: Eliminates common Urdu stop words to focus on meaningful content during text processing.
- **Normalization**: Standardizes text by removing diacritics, normalizing character variations, and handling common orthographic variations in Urdu.
- **Stemming**: Reduces words to their root form, improving text analysis and comprehension in Urdu.
- **Spell Checker**: Identifies and corrects misspelled words in Urdu text, enhancing text quality and readability.

## Functions

# Normalization

### 1. `normalize_characters(text)`

This function normalizes the Urdu characters in the given text by mapping incorrect Urdu characters to their correct forms. Sometimes, single Unicode characters representing Urdu may be written in multiple forms, and this function normalizes them accordingly.

**Example:**

```python
text = "آپ کیسے ہیں؟"
normalized_text = urdu_normalizer.normalize_characters(text)
print(normalized_text)  # Output: اپ کیسے ہیں؟
```

### 2. `normalize_combine_characters(text)`

This function simplifies Urdu characters by combining certain combinations into their correct single forms. In Urdu writing, some characters are made up of multiple parts like ligatures or diacritics. This function finds these combinations in the text and changes them to their single character forms. It ensures consistency and accuracy in how Urdu text is represented.

**Example:**

```python
text = "اُردو"
normalized_text = urdu_normalizer.normalize_combine_characters(text)
print(normalized_text)  # Output: اُردو
```

### 3. `normalize(text)`

This function performs all-in-one normalization on the Urdu text, including character normalization, diacritic removal, punctuation handling, digit conversion, and special character preservation.

**Example:**

```python
text = "آپ کیسے ہیں؟ میں ۲۳ سال کا ہوں۔"
normalized_text = urdu_normalizer.normalize(text)
print("Normalize all at once together of Urdu: ", normalized_text)  # Output: اپ کیسے ہیں ؟ میں 23 سال کا ہوں ۔
```

### 4. `remove_diacritics(text)`

This function removes diacritics (zabar, zer, pesh) from the Urdu text.

**Example:**

```python
text = "کِتَاب"
diacritics_removed = urdu_normalizer.remove_diacritics(text)
print("Remove all Diacritic (Zabar - Zer - Pesh): ", diacritics_removed)  # Output: کتاب
```

### 5. `punctuations_space(text)`

This function remove spaces after punctuations (excluding numbers) and removes spaces before punctuations in the Urdu text.

**Example:**

```python
text = "کیا آپ کھانا کھانا چاہتے ہیں ؟ میں کھانا کھاؤں گا  ۔"
punctuated_text = urdu_normalizer.punctuations_space(text)
print(punctuated_text)  # Output: کیا آپ کھانا کھانا چاہتے ہیں؟ میں کھانا کھاؤں گا۔
```

### 6. `replace_digits(text)`

This function replaces English digits with Urdu digits.

**Example:**

```python
text = "میں 23 سال کا ہوں۔"
english_digits = urdu_normalizer.replace_digits(text)
print("Replace All maths numbers with Urdu number eg(2 1 3 1 -> ۲ ۱ ۳ ۱): ", english_digits)  # Output: میں ۲۳ سال کا ہوں۔
```

### 7. `remove_numbers_urdu(text)`

This function removes Urdu numbers from the Urdu text.

**Example:**

```python
text = "میں  22 ۲۳ سال کا ہوں۔"
no_urdu_numbers = urdu_normalizer.remove_numbers_urdu(text)
print("Remove Urdu numbers from text: ", no_urdu_numbers)  # Output: میں 22 سال کا ہوں۔
```

### 8. `remove_numbers_english(text)`

This function removes English numbers from the Urdu text.

**Example:**

```python
text = "میں ۲۳ 23 سال کا ہوں۔"
no_english_numbers = urdu_normalizer.remove_numbers_english(text)
print("Remove English numbers from text: ", no_english_numbers)  # Output: میں ۲۳ سال کا ہوں۔
```

### 9. `remove_whitespace(text)`

This function removes extra whitespaces from the Urdu text.

**Example:**

```python
text = "میں   گھر   جا   رہا   ہوں۔"
cleaned_text = urdu_normalizer.remove_whitespace(text)
print("Remove All extra space between words", cleaned_text)  # Output: میں گھر جا رہا ہوں۔
```

### 10. `preserve_special_characters(text)`

This function adds spaces around special characters in the Urdu text to facilitate tokenization.

**Example:**

```python
text = "میں@پاکستان_سے_ہوں۔"
preserved_text = urdu_normalizer.preserve_special_characters(text)
print("make a space between every special character and word so tokenize easily", preserved_text)  # Output: میں @ پاکستان _ سے _ ہوں ۔
```

### 11. `remove_numbers(text)`

This function removes both Urdu and English numbers from the Urdu text.

**Example:**

```python
text = "میں ۲۳ سال کا ہوں اور میری عمر 23 ہے۔"
number_removed = urdu_normalizer.remove_numbers(text)
print("Remove All numbers whether they are Urdu or English: ", number_removed)  # Output: میں سال کا ہوں اور میری عمر ہے۔
```

### 12. `remove_english(text)`

This function removes English characters from the Urdu text.

**Example:**

```python
text = "I am learning Urdu."
urdu_only = urdu_normalizer.remove_english(text)
print("Remove All English characters from text: ", urdu_only)  # Output:  ام لرننگ اردو
```

### 13. `pure_urdu(text)`

This function removes all non-Urdu characters and numbers from the text, leaving only Urdu characters and special characters used in Urdu.

**Example:**

```python
text = "I ?  # & am learning Urdu. میں اردو سیکھ رہا ہوں۔ 123"
pure_urdu_text = urdu_normalizer.pure_urdu(text)
print(pure_urdu_text)  # Output: میں اردو سیکھ رہا ہوں۔
```

### 14. `just_urdu(text)`

This function removes all non-Urdu characters, numbers, and special characters, just leaving only pure Urdu text even not special character used in urdu.

**Example:**

```python
text = "I am learning Urdu. میں اردو سیکھ رہا ہوں۔ 123"
just_urdu_text = urdu_normalizer.just_urdu(text)
print(just_urdu_text)  # Output: میں اردو سیکھ رہا ہوں 
```

### 15. `remove_urls(text)`

This function removes URLs from the Urdu text.

**Example:**

```python
text = "میں https://www.example.com پر گیا۔"
no_urls = urdu_normalizer.remove_urls(text)
print("Remove All URLs", no_urls)  # Output: میں  پر گیا۔
```

### 16. `remove_special_characters(text)`

This function removes all special characters from the Urdu text.

**Example:**

```python
text = "میں@پاکستان_سے_ہوں۔"
no_special_chars = urdu_normalizer.remove_special_characters(text)
print("Remove All Special characters", no_special_chars)  # Output: میں پاکستان سے ہوں
```

### 17. `remove_special_characters_exceptUrdu(text)`

This function removes all special characters from the Urdu text, except for those commonly used in the Urdu language (e.g., ؟, ۔, ،).

**Example:**

```python
text = "میں@پاکستان??_سے_ہوں؟"
urdu_special_chars = urdu_normalizer.remove_special_characters_exceptUrdu(text)
print("Remove All Special characters except those which are used in Urdu language eg( ؟ ۔ ، ): ", urdu_special_chars)  # Output: میں پاکستان سے ہوں؟
```
# Stop Words Removing

### 18. `remove_stopwords(text)`

This function removes stopwords from the Urdu text.

**Example:**

```python
text = "میں اس کتاب کو پڑھنا چاہتا ہوں۔"
filtered_text = urdu_normalizer.remove_stopwords(text)
print("Remove Stop words:", filtered_text)  # Output: کتاب پڑھنا چاہتا ہوں۔
```

# Tokenization

Tokenization involves breaking down Urdu text into individual tokens, considering the intricacies of Urdu script and language structure.

### 19. `urdu_tokenize(text)`

This function tokenizes the Urdu text into individual tokens (words, numbers, and punctuations).

**Example:**

```python
text = "میں پاکستان سے ہوں۔"
tokens = urdu_normalizer.urdu_tokenize(text)
print("Tokenization for Urdu language:", tokens)  # Output: ['میں', 'پاکستان', 'سے', 'ہوں۔']
```
# Lemmatization and Stemming

Lemmatization involves converting inflected words into their base or dictionary form, while stemming reduces words to their root form.

### 20. `lemmatize_sentence(sentence)`

This function performs lemmatization on the Urdu sentence, replacing words with their base or dictionary form.

**Example:**

```python
sentence = "میں کتابیں پڑھتا ہوں۔"
lemmatized_sentence = urdu_normalizer.lemmatize_sentence(sentence)
print("lemmatize the words ", lemmatized_sentence)  # Output: میں کتاب پڑھنا ہوں۔
```

### 21. `urdu_stemmer(sentence)`

This function performs stemming on the Urdu sentence, reducing words to their root or stem form.

**Example:**

```python
sentence = "میں کتابیں پڑھتا ہوں۔"
stemmed_sentence = urdu_normalizer.urdu_stemmer(sentence)
print("Urdu Stemming ", stemmed_sentence)  # Output: میں کتاب پڑھ ہوں۔
```
# Spell Checker

Spell checking involves identifying and correcting misspelled words in Urdu text.

### 22. `corrected_sentence_spelling(input_word, threshold)`

This function takes an input sentence and a similarity threshold as arguments and returns the corrected sentence with potentially misspelled words replaced by the most similar words from the vocabulary.

**Example:**

```python
sentence = 'سسب سےا بڑاا ملکا ہے'
corrected_sentence = spell_checker.corrected_sentence_spelling(sentence, 60)
print("This correct spelling of sentence itself", corrected_sentence)
```

### 23. `most_similar_word(input_word, threshold)`

This function takes an input word and a similarity threshold as arguments and returns the most similar word from the vocabulary based on the Levenshtein distance.

**Example:**

```python
word = 'پاکستاان'
most_similar = spell_checker.most_similar_word(word, 70)
print("This will return the most similar single word in string", most_similar)
```

### 24. `get_similar_words_percentage(input_word, threshold)`

This function takes an input word and a similarity threshold as arguments and returns a list of tuples containing similar words and their corresponding similarity percentages.

**Example:**

```python
word = 'پاکستاان'
similar_words_with_percentage = spell_checker.get_similar_words_percentage(word, 70)
print("This will return the most similar words in list with percentage", similar_words_with_percentage)
```

### 25. `get_similar_words(input_word, threshold)`

This function takes an input word and a similarity threshold as arguments and returns a list of similar words from the vocabulary based on the Levenshtein distance.

**Example:**

```python
word = 'پاکستاان'
similar_words = spell_checker.get_similar_words(word, 70)
print("This will return the most similar words in list only you can access word using index", similar_words)
```

These functions leverage the Levenshtein distance algorithm to calculate the similarity between the input word or sentence and the words in the vocabulary. The `threshold` parameter is used to filter out words with a similarity percentage below the specified threshold.

Note: These examples assume that you have an instance of the `UrduTextNormalizer` class named `spell_checker` and have imported the `Levenshtein` module for calculating the edit distance.

## Installation

You can install the `LughaatUrdu` library from PyPI using pip:

```
pip install lughaatNLP
```

## Usage

After installing the library, you can import the necessary functions or classes in your Python script:

```python
from lughaat_urdu import LughaatNLP

urdu_normalizer = LughaatNLP()
text = "آپ کیسے ہیں؟"
normalized_text = LughaatNLP(text)
print(normalized_text)
```
##	Future Work

The future roadmap for LughaatNLP includes the
following features: - Urdu language translator - Urdu chatbot models - Part-of-speech tagging (POS) - Named entity recognition (NER) - Text-to-speech and speech-to-text capabilities for Urdu - Urdu text summarization
To implement these features, resources such as servers and GPU for training are required. Therefore, Muhammad Noman is collecting funds to support the development and maintenance of this library.

## Contributing

This library was created by Muhammad Noman, a student at Iqra University. You can reach him via email at muhammadnomanshafiq76@gmail.com or connect with him on [LinkedIn](https://www.linkedin.com/in/muhammad-noman-shafiq-5982b62ab/).

If you find any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request on the GitHub repository.

## License

This project is licensed under the [MIT License](LICENSE).
