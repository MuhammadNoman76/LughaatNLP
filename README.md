# LughaatNLP

Introducing LughaatNLP, the all-in-one Urdu language toolkit designed for NLP tasks in Pakistan. It offers essential features like tokenization, lemmatization, stop word removal, POS tagging, NER, normalization, summarization, and even text-to-speech and speech-to-text capabilities, all crafted exclusively for Urdu. Unlock the power of Urdu NLP effortlessly with LughaatNLP!

<p align="center">
  <img src="https://i.imgur.com/6lKyQlo.png" alt="Alt Text" width="500" height="500">
</p>

## Documentation
Explore the full potential of LughaatNLP through its detailed [documentation](https://lughaatnlp.blogspot.com/2024/04/mastering-urdu-text-processing.html), which includes practical usage examples, installation guides, and API references.

## Google Colab Notebook
Get hands-on with LughaatNLP using the interactive [Google Colab Notebook](https://colab.research.google.com/drive/1lLaUBiFq61-B7GyQ0wdNg9FyLCraAcDU?usp=sharing) provided in the documentation. This notebook lets you experiment with the toolkit's functionalities directly in your browser.

## PyPI Package
Install LughaatNLP effortlessly via its [PyPI page](https://pypi.org/project/LughaatNLP) to integrate Urdu NLP capabilities into your Python projects seamlessly.

## YouTube Tutorial Series
Accelerate your understanding of LughaatNLP's features with the dedicated [YouTube tutorial playlist](https://www.youtube.com/playlist?list=PL4tcmUwDtJEIHZhAZ3XP9U6ZJzaS4RFbd), offering step-by-step guidance on utilizing the toolkit for various Urdu NLP tasks.

## Blogs and Articles
Gain insights into advanced techniques and best practices for mastering Urdu text processing through informative articles like:

 **Medium Link** :
- [Introducing LughaatNLP: A Powerful Urdu Language Preprocessing Library](https://medium.com/@muhammadnomanshafiq76/introducing-lughaatnlp-a-powerful-urdu-language-preprocessing-library-488af74d3dde)

 **LughaatNLP Blog** :
- [Mastering Urdu Text Processing](https://lughaatnlp.blogspot.com/2024/04/mastering-urdu-text-processing.html)



## Features

- **Tokenization**: Breaks down Urdu text into individual tokens, considering the intricacies of Urdu script and language structure.
- **Lemmatization**: Converts inflected words into their base or dictionary form, aiding in text analysis and comprehension.
- **Stop Word Removal**: Eliminates common Urdu stop words to focus on meaningful content during text processing.
- **Normalization**: Standardizes text by removing diacritics, normalizing character variations, and handling common orthographic variations in Urdu.
- **Stemming**: Reduces words to their root form, improving text analysis and comprehension in Urdu.
- **Spell Checker**: Identifies and corrects misspelled words in Urdu text, enhancing text quality and readability.
- **Part of Speech Extraction**: Tags words with their grammatical categories, enabling advanced syntactic analysis.
- **Named Entity Recognition (NER)**: Identify and extract names of entities like persons, organizations, or locations.
- **Text Summarization**: Generates concise summaries of Urdu text, facilitating quick understanding of lengthy content.
- **Text-to-Speech Conversion**: Converts Urdu text into spoken audio, enabling accessibility and language learning applications.
- **Speech-to-Text Conversion**: Transcribes spoken Urdu into written text, facilitating voice-based interactions and data entry.

## Installation

You can install the `LughaatUrdu` library from PyPI using pip:

```bash
pip install lughaatNLP
```

Alternatively, you can manually install it by downloading and unzipping the provided `LughaatNLP.rar` file and installing the wheel file using pip:

```bash
pip install path_to_wheel_file/LughaatNLP-1.0.2-py3-none-any.whl
```

## Required Packages

The LughaatNLP library requires the following packages:

- `python-Levenshtein`
- `tensorflow`
- `numpy`
- `scikit-learn`
- `scipy`
- `gtts`
- `SpeechRecognition`
- `Pydub`


You can install these packages using pip:

```bash
pip install python-Levenshtein tensorflow numpy scikit-learn scipy gtts SpeechRecognition pydub
```

## Usage

After installing the library, you can import the necessary functions or classes in your Python script:

```python
#importing Pakages
from LughaatNLP import LughaatNLP 
from LughaatNLP import POS_urdu 
from LughaatNLP import NER_Urdu
from LughaatNLP import TextSummarization
from LughaatNLP import  UrduSpeech

# Instance Calling 
urdu_text_processing = LughaatNLP() 
ner_urdu = NER_Urdu()
pos_tagger = POS_urdu()
speech_urdu = TextSummarization()
speech_urdu = UrduSpeech()
```

## Functions

# Normalization

### 1. `normalize_characters(text)`

This function normalizes the Urdu characters in the given text by mapping incorrect Urdu characters to their correct forms. Sometimes, single Unicode characters representing Urdu may be written in multiple forms, and this function normalizes them accordingly.

**Example:**

```python
text = "آپ کیسے ہیں؟"
normalized_text = urdu_text_processing.normalize_characters(text)
print(normalized_text)  # Output: اپ کیسے ہیں؟
```

### 2. `normalize_combine_characters(text)`

This function simplifies Urdu characters by combining certain combinations into their correct single forms. In Urdu writing, some characters are made up of multiple parts like ligatures or diacritics. This function finds these combinations in the text and changes them to their single character forms. It ensures consistency and accuracy in how Urdu text is represented.

**Example:**

```python
text = "اُردو"
normalized_text = urdu_text_processing.normalize_combine_characters(text)
print(normalized_text)  # Output: اُردو
```

### 3. `normalize(text)`

This function performs all-in-one normalization on the Urdu text, including character normalization, diacritic removal, punctuation handling, digit conversion, and special character preservation.

**Example:**

```python
text = "آپ کیسے ہیں؟ میں ۲۳ سال کا ہوں۔"
normalized_text = urdu_text_processing.normalize(text)
print("Normalize all at once together of Urdu: ", normalized_text)  # Output: اپ کیسے ہیں ؟ میں 23 سال کا ہوں ۔
```

### 4. `remove_diacritics(text)`

This function removes diacritics (zabar, zer, pesh) from the Urdu text.

**Example:**

```python
text = "کِتَاب"
diacritics_removed = urdu_text_processing.remove_diacritics(text)
print("Remove all Diacritic (Zabar - Zer - Pesh): ", diacritics_removed)  # Output: کتاب
```

### 5. `punctuations_space(text)`

This function remove spaces after punctuations (excluding numbers) and removes spaces before punctuations in the Urdu text.

**Example:**

```python
text = "کیا آپ کھانا کھانا چاہتے ہیں ؟ میں کھانا کھاؤں گا  ۔"
punctuated_text = urdu_text_processing.punctuations_space(text)
print(punctuated_text)  # Output: کیا آپ کھانا کھانا چاہتے ہیں؟ میں کھانا کھاؤں گا۔
```

### 6. `replace_digits(text)`

This function replaces English digits with Urdu digits.

**Example:**

```python
text = "میں 23 سال کا ہوں۔"
english_digits = urdu_text_processing.replace_digits(text)
print("Replace All maths numbers with Urdu number eg(2 1 3 1 -> ۲ ۱ ۳ ۱): ", english_digits)  # Output: میں ۲۳ سال کا ہوں۔
```

### 7. `remove_numbers_urdu(text)`

This function removes Urdu numbers from the Urdu text.

**Example:**

```python
text = "میں  22 ۲۳ سال کا ہوں۔"
no_urdu_numbers = urdu_text_processing.remove_numbers_urdu(text)
print("Remove Urdu numbers from text: ", no_urdu_numbers)  # Output: میں 22 سال کا ہوں۔
```

### 8. `remove_numbers_english(text)`

This function removes English numbers from the Urdu text.

**Example:**

```python
text = "میں ۲۳ 23 سال کا ہوں۔"
no_english_numbers = urdu_text_processing.remove_numbers_english(text)
print("Remove English numbers from text: ", no_english_numbers)  # Output: میں ۲۳ سال کا ہوں۔
```

### 9. `remove_whitespace(text)`

This function removes extra whitespaces from the Urdu text.

**Example:**

```python
text = "میں   گھر   جا   رہا   ہوں۔"
cleaned_text = urdu_text_processing.remove_whitespace(text)
print("Remove All extra space between words", cleaned_text)  # Output: میں گھر جا رہا ہوں۔
```

### 10. `preserve_special_characters(text)`

This function adds spaces around special characters in the Urdu text to facilitate tokenization.

**Example:**

```python
text = "میں@پاکستان_سے_ہوں۔"
preserved_text = urdu_text_processing.preserve_special_characters(text)
print("make a space between every special character and word so tokenize easily", preserved_text)  # Output: میں @ پاکستان _ سے _ ہوں ۔
```

### 11. `remove_numbers(text)`

This function removes both Urdu and English numbers from the Urdu text.

**Example:**

```python
text = "میں ۲۳ سال کا ہوں اور میری عمر 23 ہے۔"
number_removed = urdu_text_processing.remove_numbers(text)
print("Remove All numbers whether they are Urdu or English: ", number_removed)  # Output: میں سال کا ہوں اور میری عمر ہے۔
```

### 12. `remove_english(text)`

This function removes English characters from the Urdu text.

**Example:**

```python
text = "I am learning Urdu."
urdu_only = urdu_text_processing.remove_english(text)
print("Remove All English characters from text: ", urdu_only)  # Output:  ام لرننگ اردو
```

### 13. `pure_urdu(text)`

This function removes all non-Urdu characters and numbers from the text, leaving only Urdu characters and special characters used in Urdu.

**Example:**

```python
text = "I ?  # & am learning Urdu. میں اردو سیکھ رہا ہوں۔ 123"
pure_urdu_text = urdu_text_processing.pure_urdu(text)
print(pure_urdu_text)  # Output: میں اردو سیکھ رہا ہوں۔
```

### 14. `just_urdu(text)`

This function removes all non-Urdu characters, numbers, and special characters, just leaving only pure Urdu text even not special character used in urdu.

**Example:**

```python
text = "I am learning Urdu. میں اردو سیکھ رہا ہوں۔ 123"
just_urdu_text = urdu_text_processing.just_urdu(text)
print(just_urdu_text)  # Output: میں اردو سیکھ رہا ہوں 
```

### 15. `remove_urls(text)`

This function removes URLs from the Urdu text.

**Example:**

```python
text = "میں https://www.example.com پر گیا۔"
no_urls = urdu_text_processing.remove_urls(text)
print("Remove All URLs", no_urls)  # Output: میں  پر گیا۔
```

### 16. `remove_special_characters(text)`

This function removes all special characters from the Urdu text.

**Example:**

```python
text = "میں@پاکستان_سے_ہوں۔"
no_special_chars = urdu_text_processing.remove_special_characters(text)
print("Remove All Special characters", no_special_chars)  # Output: میں پاکستان سے ہوں
```

### 17. `remove_special_characters_exceptUrdu(text)`

This function removes all special characters from the Urdu text, except for those commonly used in the Urdu language (e.g., ؟, ۔, ،).

**Example:**

```python
text = "میں@پاکستان??_سے_ہوں؟"
urdu_special_chars = urdu_text_processing.remove_special_characters_exceptUrdu(text)
print("Remove All Special characters except those which are used in Urdu language eg( ؟ ۔ ، ): ", urdu_special_chars)  # Output: میں پاکستان سے ہوں؟
```
# Stop Words Removing

### 1. `remove_stopwords(text)`

This function removes stopwords from the Urdu text.

**Example:**

```python
text = "میں اس کتاب کو پڑھنا چاہتا ہوں۔"
filtered_text = urdu_text_processing.remove_stopwords(text)
print("Remove Stop words:", filtered_text)  # Output: کتاب پڑھنا چاہتا ہوں۔
```

# Tokenization

Tokenization involves breaking down Urdu text into individual tokens, considering the intricacies of Urdu script and language structure.

### 1. `urdu_tokenize(text)`

This function tokenizes the Urdu text into individual tokens (words, numbers, and punctuations).

**Example:**

```python
text = "میں پاکستان سے ہوں۔"
tokens = urdu_text_processing.urdu_tokenize(text)
print("Tokenization for Urdu language:", tokens)  # Output: ['میں', 'پاکستان', 'سے', 'ہوں۔']
```
# Lemmatization and Stemming

Lemmatization involves converting inflected words into their base or dictionary form, while stemming reduces words to their root form.

### 1. `lemmatize_sentence(sentence)`

This function performs lemmatization on the Urdu sentence, replacing words with their base or dictionary form.

**Example:**

```python
sentence = "میں کتابیں پڑھتا ہوں۔"
lemmatized_sentence = urdu_text_processing.lemmatize_sentence(sentence)
print("lemmatize the words ", lemmatized_sentence)  # Output: میں کتاب پڑھنا ہوں۔
```

### 2. `urdu_stemmer(sentence)`

This function performs stemming on the Urdu sentence, reducing words to their root or stem form.

**Example:**

```python
sentence = "میں کتابیں پڑھتا ہوں۔"
stemmed_sentence = urdu_text_processing.urdu_stemmer(sentence)
print("Urdu Stemming ", stemmed_sentence)  # Output: میں کتاب پڑھ ہوں۔
```
# Spell Checker

Spell checking involves identifying and correcting misspelled words in Urdu text.

### 1. `corrected_sentence_spelling(input_word, threshold)`

This function takes an input sentence and a similarity threshold as arguments and returns the corrected sentence with potentially misspelled words replaced by the most similar words from the vocabulary.

**Example:**

```python
spell_checker = LughaatNLP()
sentence = 'سسب سےا بڑاا ملکا ہے'
corrected_sentence = spell_checker.corrected_sentence_spelling(sentence, 60)
print("This correct spelling of sentence itself", corrected_sentence)
```

### 2. `most_similar_word(input_word, threshold)`

This function takes an input word and a similarity threshold as arguments and returns the most similar word from the vocabulary based on the Levenshtein distance.

**Example:**

```python
spell_checker = LughaatNLP()
word = 'پاکستاان'
most_similar = spell_checker.most_similar_word(word, 70)
print("This will return the most similar single word in string", most_similar)
```

### 3. `get_similar_words_percentage(input_word, threshold)`

This function takes an input word and a similarity threshold as arguments and returns a list of tuples containing similar words and their corresponding similarity percentages.

**Example:**

```python
spell_checker = LughaatNLP()
word = 'پاکستاان'
similar_words_with_percentage = spell_checker.get_similar_words_percentage(word, 70)
print("This will return the most similar words in list with percentage", similar_words_with_percentage)
```

### 4. `get_similar_words(input_word, threshold)`

This function takes an input word and a similarity threshold as arguments and returns a list of similar words from the vocabulary based on the Levenshtein distance.

**Example:**

```python
spell_checker = LughaatNLP()
word = 'پاکستاان'
similar_words = spell_checker.get_similar_words(word, 70)
print("This will return the most similar words in list only you can access word using index", similar_words)
```

These functions leverage the Levenshtein distance algorithm to calculate the similarity between the input word or sentence and the words in the vocabulary. The `threshold` parameter is used to filter out words with a similarity percentage below the specified threshold.

Note: These examples assume that you have an instance of the `UrduTextNormalizer` class named `spell_checker` and have imported the `Levenshtein` module for calculating the edit distance.

# Part of Speech

The `pos_tags_urdu` function is used for part-of-speech tagging in Urdu text. It takes an Urdu sentence as input and returns a list of dictionaries where each word is paired with its assigned part-of-speech tag, such as nouns (`NN`), verbs (`VB`), adjectives (`ADJ`), etc.

### 1. `pos_tagger.pos_tags_urdu (sentence)`

The example output demonstrates how words like "میرے" (`G` for postposition) and "تعلیم" (`NN` for noun) are tagged based on their grammatical roles within the sentence.

**Example:**

```python
from LughaatNLP import POS_urdu

pos_tagger = POS_urdu()

sentence = "میرے والدین نے میری تعلیم اور تربیت میں بہت محنت کی تاکہ میں اپنی زندگی میں کامیاب ہو سکوں۔"

pos_tagger = POS_urdu()
predicted_pos_tags = pos_tagger.pos_tags_urdu (sentence)

print(predicted_pos_tags)


```
## output 
```python
# output => [{'Word': 'میرے', 'POS_Tag': 'G'}, {'Word': 'والدین', 'POS_Tag': 'NN'},{'Word': 'نے', 'POS_Tag': 'P'},{'Word': 'میری', 'POS_Tag': 'G'},{'Word': 'تعلیم', 'POS_Tag': 'NN'},{'Word': 'اور', 'POS_Tag': 'CC'},{'Word': 'تربیت', 'POS_Tag': 'NN'},{'Word': 'میں', 'POS_Tag': 'P'},{'Word': 'بہت', 'POS_Tag': 'ADV'},{'Word': 'محنت', 'POS_Tag': 'NN'},{'Word': 'کی', 'POS_Tag': 'VB'},{'Word': 'تاکہ', 'POS_Tag': 'SC'},{'Word': 'میں', 'POS_Tag': 'P'},{'Word': 'اپنی', 'POS_Tag': 'GR'},{'Word': 'زندگی', 'POS_Tag': 'NN'},{'Word': 'میں', 'POS_Tag': 'P'},{'Word': 'کامیاب', 'POS_Tag': 'ADJ'},{'Word': 'ہو', 'POS_Tag': 'VB'},{'Word': 'سکوں', 'POS_Tag': 'NN'},{'Word': '۔', 'POS_Tag': 'SM'}]
```
# Name Entity Relationships

The `ner_tags_urdu` function performs named entity recognition on Urdu text, assigning named entity tags (such as `U-LOCATION` for locations) to identified entities in the input sentence. It outputs a dictionary where words are mapped to their corresponding named entity tags, facilitating tasks like information extraction and text analysis specific to Urdu language. 

### 1. `ner_urdu.ner_tags_urdu (sentence)`

The example output illustrates how entities like "پاکستان" are recognized as locations (U-LOCATION) within the provided sentence.

**Example:**

```python
from LughaatNLP import NER_Urdu

ner_urdu = NER_Urdu()

sentence = "اس کتاب میں پاکستان کی تاریخ بیان کی گئی ہے۔"

word_tag_dict= ner_urdu.ner_tags_urdu (sentence)

print(word_tag_dict)


```
## output 
```python
# output => {'اس': 'O', 'کتاب': 'O', 'میں': 'O', 'پاکستان': 'U-LOCATION', 'کی': 'O', 'تاریخ': 'O', 'بیان': 'O', 'گئی': 'O', 'ہے': 'O', '۔': 'O'}
```

# Text Summarization

The `TextSummarization` class offers automatic summarization of Urdu text by leveraging natural language processing techniques. It uses graph-based representation and scoring methods like BM25 and TF-IDF to identify and select the most important sentences for summarization. This class is designed to generate concise and informative summaries from unstructured Urdu text, making it valuable for applications requiring efficient text summarization capabilities.

### 1. `summarize(text, ratio)`

This Python program demonstrates the use of the `TextSummarization` class from the `LughaatNLP` module to summarize a given Urdu text based on a specified ratio. The input text is a news article discussing the integration of digital technology into governance and electoral processes in China. The program initializes a `TextSummarization` instance, sets a summary ratio of 1% (adjustable to other percentages), and then generates a summary using the `summarize` method. 

**Example:**

```python
from LughaatNLP import TextSummarization


text = '''
بھی حال ہی میں تیسرے انٹرنیشنل ڈیموکریسی فورم کا انعقاد بیجنگ میں کیا گیا ، جس میں 70 سے زائد ممالک اور خطوں کے تقریباً 300 عہدیداروں اور ماہرین نے اس بات پر تبادلہ خیال کیا کہ جمہوریت کو جدید ڈیجیٹل دور کی ضروریات اور گلوبل ساؤتھ کی مضبوطی کے مطابق کیسے ہونا چاہئے۔
وسیع تناظر میں آج، ڈیجیٹل ٹیکنالوجی چین کی جمہوری گورننس کے ساتھ گہرائی سے جڑی ہوئی ہے۔ اس وقت ووٹنگ کے دوران ڈیجیٹل ٹیکنالوجی کا استعمال، حکومتی پالیسیوں کو سمجھنے، مشاورت میں حصہ لینے اور حکومتی سرگرمیوں کی نگرانی جیسے عمل کو آسان بنا رہا ہے.چین کے سرکاری انتخابی طریقہ کار میں ڈیجیٹل ٹیکنالوجی کا انضمام ووٹر رجسٹریشن، امیدواروں کی معلومات کی فراہمی کے ساتھ ساتھ ووٹنگ اور گنتی کے عمل جیسے کاموں کو آسان بنارہا ہے۔
یہ انضمام حکومتی اداروں، رائے دہندگان اور امیدواروں کے درمیان تعامل کو بھی بڑھاتا ہے، حتمی طور پر اس بات کو یقینی بناتا ہے کہ جمہوری انتخابات عوام کی ضروریات کے مطابق زیادہ جوابدہ ہوں۔
مزید برآں، ڈیجیٹل ٹیکنالوجی حکومت کو عوامی تشویش کے مسائل کو حل کرنے کے لئے کاروباری اداروں، ماہرین اور سول مندوبین کے درمیان آن لائن تبادلہ خیال کا اہتمام کرنے کے قابل بنا رہی ہے، جس سے مشاورت زیادہ موثر ہوتی جا رہی ہے.ڈیجیٹل ٹیک فیصلہ سازی اور انتظام کے لئے چینلز کو بھی وسعت دیتی ہے۔
لوگ حکومت کی جانب سے شروع کیے گئے مختلف آن لائن پلیٹ فارمز جیسے ڈیجیٹل رائے عامہ کے چینلز اور آن لائن سروے کے ذریعے اپنی رائے کا اظہار کرسکتے ہیں اور مشاورت میں مشغول ہوسکتے ہیں۔ نتیجتاً ، سوشل گورننس کے لئے فیڈ بیک میکانزم نے درجہ بندی کی سطحوں کو کم کردیا ہے ، جس سے ردعمل اور کارکردگی میں تیزی سے اضافہ ہوا ہے۔
یہاں اس حقیقت کو بھی تسلیم کرنا پڑے گا کہ، ڈیجیٹل ٹیکنالوجی کا اثر محض کارکردگی کے فوائد سے کہیں زیادہ ہے. یہ سوشل میڈیا پلیٹ فارمز اور آن لائن رپورٹنگ سسٹم کی بدولت سرکاری کارروائیوں میں شفافیت اور احتساب کو فروغ دے رہی ہے۔ عوامی جانچ پڑتال کی نگرانی میں انتظامی عمل کا معائنہ بھی شامل ہے ، جو اس بات کو یقینی بناتا ہے کہ سرکاری سرگرمیاں اخلاقی معیارات پر مکمل عمل پیرا ہوں اور عوام کو جوابدہ ہوں۔
یوں چین میں ، ڈیجیٹل ٹیکنالوجی صرف ایک آلہ نہیں ہے۔ یہ ترقی کے لئے ایک محرک ہے جو شہریوں کو جمہوری عمل کو تشکیل دینے کے لئے بااختیار بناتا ہے. جدید پلیٹ فارمز اور شفاف حکمرانی کے طریقوں نے لوگوں کے لئے اپنے جمہوری حقوق کو براہ راست استعمال کرنے کے لئے زیادہ آسان اور موثر بنا دیا ہے۔
ڈیجیٹل ٹیکنالوجی سے ہٹ کر اگر تیسرے انٹرنیشنل ڈیموکریسی فورم کی مزید بات کی جائے تو فورم کے شرکاء نے جہاں تکنیکی ترقی کی وکالت کی وہاں یہ بھی واضح کیا کہ کوئی ایک طرز جمہوریت یا جمہوری ماڈل واحد انتخاب نہیں ہونا چاہئے۔مغربی ریاستوں کو ایسی سیاسی شکلوں کو قبول کرنا چاہیے جو ان کی اپنی سیاسی شکلوں سے مختلف ہیں۔ساتھ ساتھ یہ ضروری ہے کہ دنیا کو ایک ایسی کمیونٹی کے نقطہ نظر سے دیکھا جائے جس کی انسانیت کے لئے مشترکہ تقدیر ہو۔
اس ضمن میں چین کی جانب سے تجویز کردہ بین الاقوامی اقدامات بشمول بیلٹ اینڈ روڈ انیشی ایٹو، گلوبل ڈیولپمنٹ انیشی ایٹو، گلوبل سیکیورٹی انیشی ایٹو اور گلوبل سولائزیشن انیشی ایٹو مسابقت اور بالادستی کے نقطہ نظر سے یکسر جداگانہ نقطہ نظر فراہم کرتے ہیں اور عالمی چیلنجز کا چینی دانش کے تحت موئثر حل پیش کرتے ہیں۔

'''

summarizer = TextSummarization()
ratio = 0.01  # Summary ratio (e.g., keep 1% of the sentences or adjust according to your preference: 10%, 20%, 40%, etc. (1% to 100%))
summary = summarizer.summarize(text, ratio)
print(summary)
```
## output 
```python
#output =>
گلوبل سیکیورٹی انیشی ایٹو اور گلوبل سولائزیشن انیشی ایٹو مسابقت اور بالادستی کے نقطہ نظر سے یکسر جداگانہ نقطہ نظر فراہم کرتے ہیں اور عالمی چیلنجز کا چینی دانش کے تحت موئثر حل پیش کرتے ہیں ۔
```

### 2. `summarize_unstructured_text(text, ratio)`

The `summarize_unstructured_text` function for the `Text without the sentence Structure` in the `TextSummarizer` class is designed to summarize messy or unorganized Urdu text by automatically breaking it into understandable sentences. This function helps users quickly get a condensed summary of important information from raw text that may not follow typical sentence structures. It's useful for efficiently analyzing and extracting key details from various forms of unstructured Urdu text.

**Example:**

```python
from LughaatNLP import TextSummarization


# Example usage

# Text without the sentence Structure

text = "اس ضمن میں چین کی جانب سے تجویز کردہ بین الاقوامی اقدامات بشمول بیلٹ اینڈ روڈ انیشی ایٹو گلوبل ڈیولپمنٹ انیشی ایٹو گلوبل سیکیورٹی انیشی ایٹو اور گلوبل سولائزیشن انیشی ایٹو مسابقت اور بالادستی کے نقطہ نظر سے یکسر جداگانہ نقطہ نظر فراہم کرتے ہیں اور عالمی چیلنجز کا چینی دانش کے تحت موئثر حل پیش کرتے ہیں اس وقت ووٹنگ کے دوران ڈیجیٹل ٹیکنالوجی کا استعمال حکومتی پالیسیوں کو سمجھنے مشاورت میں حصہ لینے اور حکومتی سرگرمیوں کی نگرانی جیسے عمل کو آسان بنا رہا ہےچین کے سرکاری انتخابی طریقہ کار میں ڈیجیٹل ٹیکنالوجی کا انضمام ووٹر رجسٹریشن امیدواروں کی معلومات کی فراہمی کے ساتھ ساتھ ووٹنگ اور گنتی کے عمل جیسے کاموں کو آسان بنارہا ہے مزید برآں ڈیجیٹل ٹیکنالوجی حکومت کو عوامی تشویش کے مسائل کو حل کرنے کے لئے کاروباری اداروں ماہرین اور سول مندوبین کے درمیان آن لائن تبادلہ خیال کا اہتمام کرنے کے قابل بنا رہی ہے جس سے مشاورت زیادہ موثر ہوتی جا رہی ہےڈیجیٹل ٹیک فیصلہ سازی اور انتظام کے لئے چینلز کو بھی وسعت دیتی ہے بھی حال ہی میں تیسرے انٹرنیشنل ڈیموکریسی فورم کا انعقاد بیجنگ میں کیا گیا جس میں 70 سے زائد ممالک اور خطوں کے تقریباً 300 عہدیداروں اور ماہرین نے اس بات پر تبادلہ خیال کیا کہ جمہوریت کو جدید ڈیجیٹل دور کی ضروریات اور گلوبل ساؤتھ کی مضبوطی کے مطابق کیسے ہونا چاہئے یہ ترقی کے لئے ایک محرک ہے جو شہریوں کو جمہوری عمل کو تشکیل دینے کے لئے بااختیار بناتا ہے جدید پلیٹ فارمز اور شفاف حکمرانی کے طریقوں نے لوگوں کے لئے اپنے جمہوری حقوق کو براہ راست استعمال کرنے کے لئے زیادہ آسان اور موثر بنا دیا ہے ڈیجیٹل ٹیکنالوجی سے ہٹ کر اگر تیسرے انٹرنیشنل ڈیموکریسی فورم کی مزید بات کی جائے تو فورم کے شرکاء نے جہاں تکنیکی ترقی کی وکالت کی وہاں یہ بھی واضح کیا کہ کوئی ایک طرز جمہوریت یا جمہوری ماڈل واحد انتخاب نہیں ہونا چاہئے یہاں اس حقیقت کو بھی تسلیم کرنا پڑے گا کہ ڈیجیٹل ٹیکنالوجی کا اثر محض کارکردگی کے فوائد سے کہیں زیادہ ہے یہ سوشل میڈیا پلیٹ فارمز اور آن لائن رپورٹنگ سسٹم کی بدولت سرکاری کارروائیوں میں شفافیت اور احتساب کو فروغ دے رہی ہے لوگ حکومت کی جانب سے شروع کیے گئے مختلف آن لائن پلیٹ فارمز جیسے ڈیجیٹل رائے عامہ کے چینلز اور آن لائن سروے کے ذریعے اپنی رائے کا اظہار کرسکتے ہیں اور مشاورت میں مشغول ہوسکتے ہیں عوامی جانچ پڑتال کی نگرانی میں انتظامی عمل کا معائنہ بھی شامل ہے جو اس بات کو یقینی بناتا ہے کہ سرکاری سرگرمیاں اخلاقی معیارات پر مکمل عمل پیرا ہوں اور عوام کو جوابدہ ہوں یہ انضمام حکومتی اداروں رائے دہندگان اور امیدواروں کے درمیان تعامل کو بھی بڑھاتا ہے حتمی طور پر اس بات کو یقینی بناتا ہے کہ جمہوری انتخابات عوام کی ضروریات کے مطابق زیادہ جوابدہ ہوں نتیجتاً سوشل گورننس کے لئے فیڈ بیک میکانزم نے درجہ بندی کی سطحوں کو کم کردیا ہے جس سے ردعمل اور کارکردگی میں تیزی سے اضافہ ہوا ہے مغربی ریاستوں کو ایسی سیاسی شکلوں کو قبول کرنا چاہیے جو ان کی اپنی سیاسی شکلوں سے مختلف ہیں ساتھ ساتھ یہ ضروری ہے کہ دنیا کو ایک ایسی کمیونٹی کے نقطہ نظر سے دیکھا جائے جس کی انسانیت کے لئے مشترکہ تقدیر ہو وسیع تناظر میں آج ڈیجیٹل ٹیکنالوجی چین کی جمہوری گورننس کے ساتھ گہرائی سے جڑی ہوئی ہے"


summarizer = TextSummarization()
ratio = 0.01  # Summary ratio (e.g., keep 1% of the sentences or adjust according to your preference: 10%, 20%, 40%, etc. (1% to 100%))
summary = summarizer. summarize_unstructured_text(text, ratio)
print(summary)
```
## output 
```python

# output => جانب سے تجویز کردہ بین الاقوامی اقدامات بشمول بیلٹ اینڈ روڈ انیشی ایٹو گلوبل ڈیولپمنٹ انیشی ایٹو گلوبل سیکیورٹی انیشی ایٹو اور گلوبل سولائزیشن انیشی ایٹو مسابقت اور بالادستی کے نقطہ نظر سے یکسر جداگانہ نقطہ نظر فراہم کرتے ہیں۔
```
### Text-to-Speech & Speech-to-Text

The `UrduSpeechConverter` class provides functionality to convert Urdu text to speech and vice versa using the Google Text-to-Speech (gTTS) API and SpeechRecognition library. This library supports converting Urdu text to audio files (MP3, WAV, or OGG formats) and recognizing Urdu speech from audio files (MP3 or WAV formats). Before using this library, ensure that `ffmpeg` is installed on your computer, as it is required for audio file manipulation.

## Installation Requirements

Before using the `UrduSpeechConverter` library, ensure you have `ffmpeg` installed on your computer and that it is accessible via the command line. `ffmpeg` is essential for converting audio files to different formats, which is necessary for speech recognition tasks. If `ffmpeg` is not installed, please install it and set the environment variable path accordingly.

### 1. `text_to_speech(text, output_file_name, format)`

This function converts Urdu text to speech and saves the generated speech as an audio file in the specified format.

**Parameters:**
- `text`: The Urdu text to convert to speech.
- `output_file_folder`: The of the folder where you want to save audio.
- `output_file_name`: The name of the output audio file (without file extension).
- `format`: The format for the output audio file (`'wav'`, `'mp3'`, or `'ogg'`).

**Example Usage  1:**
```python
from LughaatNLP import  UrduSpeech

converter = UrduSpeech()

text = 'جانب سے تجویز کردہ بین الاقوامی اقدامات بشمول بیلٹ اینڈ روڈ انیشی ایٹو، گلوبل ڈیولپمنٹ انیشی ایٹو، گلوبل سیکیورٹی انیشی ایٹو اور گلوبل سولائزیشن انیشی ایٹو مسابقت اور بالادستی کے نقطہ نظر سے یکسر جداگانہ نقطہ نظر فراہم کرتے ہیں'

converter.text_to_speech(text, output_file_name='output', format='wav')
converter.text_to_speech(text, output_file_name='output', format='mp3')
converter.text_to_speech(text, output_file_name='output', format='ogg')
```

## Output 
```python
# output =>
# (save on the same directory) or 
Speech saved to output.wav
Speech saved to output.mp3
Speech saved to output.ogg
```
You can also specify an output folder path:

**Example Usage  2:**
```python
output_folder = r'C:\Users\YourName\Desktop\Testing\your-path'

converter.text_to_speech(text, output_folder, output_file_name='output', format='wav')
converter.text_to_speech(text, output_folder, output_file_name='output', format='mp3')
converter.text_to_speech(text, output_folder, output_file_name='output', format='ogg')
```

## Output 
```python
# output =>
Speech saved to CC:\Users\YourName\Desktop\Testing\your-path\output.wav
Speech saved to CC:\Users\YourName\Desktop\Testing\your-path\output.mp3
Speech saved to CC:\Users\YourName\Desktop\Testing\your-path\output.ogg
```

##	Future Work

The future roadmap for LughaatNLP includes the
following features: - Urdu language translator - Urdu chatbot models - Text-to-speech and speech-to-text capabilities for Urdu - Urdu text summarization
To implement these features, resources such as servers and GPU for training are required. Therefore, Muhammad Noman is collecting funds to support the development and maintenance of this library.

## Contributing

This library was created by Muhammad Noman, a student at Iqra University. You can reach him via email at muhammadnomanshafiq76@gmail.com or connect with him on [LinkedIn](https://www.linkedin.com/in/muhammad-noman76/).

If you find any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request on the [GitHub repository](https://github.com/MuhammadNoman76/LughaatNLP).

## License

This project is licensed under the [MIT License](https://drive.google.com/file/d/1YcxoYrL3atF7U7vYKK_KFiKvDF-YiywT/view?usp=drive_link).
