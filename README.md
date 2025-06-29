**Introduction to Natural Language Processing**
# Assignment 1

**Author:**  &nbsp; Shilpak Deb   
**Roll No:** &nbsp; 2024201072

---

## Instructions for `tokenizer.py`:

### How to Execute:
```bash
python3 tokenizer.py
```

---

## Instructions for `language_model.py`:

### How to Execute:
```bash
python3 language_model.py <lm_type> <n_value> <corpus_path>
```

In **lm_type** usee 'n' for normal n-gram, 'l' for Laplace, 'g' for Good-Turing, or 'i' for Interpolation"

### How to perform Analysis:
*(**Warning:** Takes a long time)*

After execution, there is a prompt asking:

```bash
Run analysis? (Y/N): 
```

Press N (or other analogs to it - "no", "n", etc.) to skip recalculating the analysis - and "Y" (or its analogs) to perform the analysis

---

## Instructions for `generator.py`:

### How to Execute:
```bash
python3 generator.py <model_type> <n_value> <corpus_path> <k>
```

---

## Folder Contents:

**( Folder Name**: 2024201072_assignment1 **)**

### .py files:
   - **tokenizer.py**: &nbsp; Tokenizes text via regex
   - **language_model.py**: &nbsp; Creates a language model for n-grams with 3 settings (l - (Laplace), g - (Good-Turing), i - (Interpolation))
   - **generator.py**: &nbsp; Predicts next word in a sentence
### .txt files:
   - **LM1_1.txt**: &nbsp; 
   - **LM1_3.txt**: &nbsp; 
   - **LM1_5.txt**: &nbsp; 
   - **LM2_1.txt**: &nbsp; 
   - **LM2_3.txt**: &nbsp; 
   - **LM2_5.txt**: &nbsp; 
   - **LM3_1.txt**: &nbsp; 
   - **LM3_3.txt**: &nbsp; 
   - **LM3_5.txt**: &nbsp; 
   - **LM4_1.txt**: &nbsp; 
   - **LM4_3.txt**: &nbsp; 
   - **LM4_5.txt**: &nbsp; 
   - **LM5_1.txt**: &nbsp; 
   - **LM5_3.txt**: &nbsp; 
   - **LM5_5.txt**: &nbsp; 
   - **LM6_1.txt**: &nbsp; 
   - **LM6_3.txt**: &nbsp; 
   - **LM6_5.txt**: &nbsp; 
### readme files:
   - **Report.pdf**: &nbsp; Contains analysis of the results obtained from the LMs
### readme files:
   - **README.md**: &nbsp; What you are currently reading

---

## Adjustments made:

### Tokenization:

 - Changed all words to lower case during tokenization for easier word matching during probability calculation
 - Converted all newline characters to whitespaces due to some sentences in the corpus being randomly broken into multiple lines via newline
 - Removed punctuation during tokenization in order to calculate better probability values
 - Interpreted dialogues as separate sentences (eg: `"I am here", he said to me.`  ->  `[["i", "am", "here",], ["he", "said", "to", "me",],]`)
 - Removed underscore "_" from the corpus while tokenizing in order to prevent appearance of words like "_But"
 - Removed chapter titles in the form "CHAPTER I" or "[ 1 ]"
 - Removed extraneous portions at the beginning and end of corpus
 - Removed letter abbreviations like "A.B.C." due to them disrupting the overall probability calculations


### Language Model
 - Changed the `language_model.py` and `generator.py` to take an additional **n** variable as input for determining n-grams
 - Added an additional '**n**' language model type for normal n-gram probabilities
 - Used `<UNK>` tokens to denote rare words - including words which were never encountered or encountered only once

