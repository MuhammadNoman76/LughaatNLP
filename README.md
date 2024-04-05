# LughaatNLP

LughaatNLP is the first comprehensive Urdu language preprocessing library developed for NLP tasks in Pakistan. It provides essential tools for tokenization, lemmatization, stop word removal, and normalization specifically tailored for the Urdu language.

## Features

- **Tokenization**: Breaks down Urdu text into individual tokens, considering the intricacies of Urdu script and language structure.
- **Lemmatization**: Converts inflected words into their base or dictionary form, aiding in text analysis and comprehension.
- **Stop Word Removal**: Eliminates common Urdu stop words to focus on meaningful content during text processing.
- **Normalization**: Standardizes text by removing diacritics, normalizing character variations, and handling common orthographic variations in Urdu.
- **Stemming**: Reduces words to their root form, improving text analysis and comprehension in Urdu.
- **Spell Checker**: Identifies and corrects misspelled words in Urdu text, enhancing text quality and readability.

## Functions

### 1. `normalize_characters(text)`

This function normalizes the Urdu characters in the given text by mapping incorrect Urdu characters to their correct forms.

**Example:**

```python
text = "آپ کیسے ہیں؟"
normalized_text = urdu_normalizer.normalize_characters(text)
print(normalized_text)  # Output: اپ کیسے ہیں؟
```

### 2. `normalize_combine_characters(text)`

This function combines certain Urdu character combinations into their combined forms.

**Example:**

```python
text = "اُردو"
normalized_text = urdu_normalizer.normalize_combine_characters(text)
print(normalized_text)  # Output: اُردو
```

### 3. `remove_diacritics(text)`

This function removes diacritics (zabar, zer, pesh) from the Urdu text.

**Example:**

```python
text = "کِتَاب"
diacritics_removed = urdu_normalizer.remove_diacritics(text)
print(diacritics_removed)  # Output: کتاب
```

### 4. `punctuations_space(text)`

This function adds spaces after punctuations (excluding numbers) and removes spaces before punctuations in the Urdu text.

**Example:**

```python
text = "کیا آپ کھانا کھانا چاہتے ہیں؟میں کھانا کھاؤں گا۔"
punctuated_text = urdu_normalizer.punctuations_space(text)
print(punctuated_text)  # Output: کیا آپ کھانا کھانا چاہتے ہیں ؟ میں کھانا کھاؤں گا ۔
```

### 5. `replace_digits(text, with_english=True)`

This function replaces Urdu digits with English digits or vice versa, depending on the value of the `with_english` parameter.

**Example:**

```python
text = "میں ۲۳ سال کا ہوں۔"
english_digits = urdu_normalizer.replace_digits(text, with_english=True)
print(english_digits)  # Output: میں 23 سال کا ہوں۔
```

### 6. `remove_whitespace(text)`

This function removes extra whitespaces from the Urdu text.

**Example:**

```python
text = "میں   گھر   جا   رہا   ہوں۔"
cleaned_text = urdu_normalizer.remove_whitespace(text)
print(cleaned_text)  # Output: میں گھر جا رہا ہوں۔
```

### 7. `preserve_special_characters(text)`

This function adds spaces around special characters in the Urdu text to facilitate tokenization.

**Example:**

```python
text = "میں@پاکستان_سے_ہوں۔"
preserved_text = urdu_normalizer.preserve_special_characters(text)
print(preserved_text)  # Output: میں @ پاکستان _ سے _ ہوں ۔
```

### 8. `remove_stopwords(text)`

This function removes stopwords from the Urdu text.

**Example:**

```python
text = "میں اس کتاب کو پڑھنا چاہتا ہوں۔"
filtered_text = urdu_normalizer.remove_stopwords(text)
print(filtered_text)  # Output: کتاب پڑھنا چاہتا ہوں۔
```

### 9. `remove_numbers(text)`

This function removes both Urdu and English numbers from the Urdu text.

**Example:**

```python
text = "میں ۲۳ سال کا ہوں اور میری عمر 23 ہے۔"
number_removed = urdu_normalizer.remove_numbers(text)
print(number_removed)  # Output: میں سال کا ہوں اور میری عمر ہے۔
```

### 10. `remove_english(text)`

This function removes English characters from the Urdu text.

**Example:**

```python
text = "I am learning Urdu."
urdu_only = urdu_normalizer.remove_english(text)
print(urdu_only)  # Output:  ام لرننگ اردو
```

### 11. `pure_urdu(text)`

This function removes all non-Urdu characters, numbers, and special characters (except those used in Urdu) from the text, leaving only pure Urdu text.

**Example:**

```python
text = "I am learning Urdu. میں اردو سیکھ رہا ہوں۔ 123"
pure_urdu_text = urdu_normalizer.pure_urdu(text)
print(pure_urdu_text)  # Output: میں اردو سیکھ رہا ہوں۔
```

### 12. `just_urdu(text)`

This function removes all non-Urdu characters and numbers from the text, leaving only Urdu characters and special characters used in Urdu.

**Example:**

```python
text = "I am learning Urdu. میں اردو سیکھ رہا ہوں۔ 123"
just_urdu_text = urdu_normalizer.just_urdu(text)
print(just_urdu_text)  # Output: میں اردو سیکھ رہا ہوں۔ ۔
```

### 13. `remove_urls(text)`

This function removes URLs from the Urdu text.

**Example:**

```python
text = "میں https://www.example.com پر گیا۔"
no_urls = urdu_normalizer.remove_urls(text)
print(no_urls)  # Output: میں  پر گیا۔
```

### 14. `remove_special_characters(text)`

This function removes all special characters from the Urdu text.

**Example:**

```python
text = "میں@پاکستان_سے_ہوں۔"
no_special_chars = urdu_normalizer.remove_special_characters(text)
print(no_special_chars)  # Output: میں پاکستان سے ہوں
```

### 15. `remove_special_characters_exceptUrdu(text)`

This function removes all special characters from the Urdu text, except for those commonly used in the Urdu language (e.g., ؟, ۔, ،).

**Example:**

```python
text = "میں@پاکستان_سے_ہوں؟"
urdu_special_chars = urdu_normalizer.remove_special_characters_exceptUrdu(text)
print(urdu_special_chars)  # Output: میں پاکستان سے ہوں؟
```

### 16. `normalize(text)`

This function performs all-in-one normalization on the Urdu text, including character normalization, diacritic removal, punctuation handling, digit conversion, and special character preservation.

**Example:**

```python
text = "آپ کیسے ہیں؟ میں ۲۳ سال کا ہوں۔"
normalized_text = urdu_normalizer.normalize(text)
print(normalized_text)  # Output: اپ کیسے ہیں ؟ میں 23 سال کا ہوں ۔
```

### 17. `urdu_tokenize(text

This function tokenizes the Urdu text into individual tokens (words, numbers, and punctuations).

**Example:**

```python
text = "میں پاکستان سے ہوں۔"
tokens = urdu_normalizer.urdu_tokenize(text)
print(tokens)  # Output: ['میں', 'پاکستان', 'سے', 'ہوں۔']
```

### 18. `lemmatize_sentence(sentence)`

This function performs lemmatization on the Urdu sentence, replacing words with their base or dictionary form.

**Example:**

```python
sentence = "میں کتابیں پڑھتا ہوں۔"
lemmatized_sentence = urdu_normalizer.lemmatize_sentence(sentence)
print(lemmatized_sentence)  # Output: میں کتاب پڑھنا ہوں۔
```

### 19. `urdu_stemmer(sentence)`

This function performs stemming on the Urdu sentence, reducing words to their root or stem form.

**Example:**

```python
sentence = "میں کتابیں پڑھتا ہوں۔"
stemmed_sentence = urdu_normalizer.urdu_stemmer(sentence)
print(stemmed_sentence)  # Output: میں کتاب پڑھ ہوں۔
```

## Installation

You can install the `LughaatUrdu` library from PyPI using pip:

```
pip install lughaat-urdu
```

## Usage

After installing the library, you can import the necessary functions or classes in your Python script:

```python
from lughaat_urdu import UrduTextNormalizer

urdu_normalizer = UrduTextNormalizer()
text = "آپ کیسے ہیں؟"
normalized_text = urdu_normalizer.normalize(text)
print(normalized_text)
```

## Contributing

If you find any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request on the GitHub repository.

## License

This project is licensed under the [MIT License](LICENSE).
