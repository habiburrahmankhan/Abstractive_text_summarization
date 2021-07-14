#  Abstractive Text Summarization
---

## [demo Frontend](https://habiburrahmankhan.github.io/Abstractive_text_summarization/)

## Problems Statement 
* There are two major problems with using Sequence-to-Sequence models for text summarization:

> Sometimes the generated summary contains inaccurate facts due to encountering of out of vocabulary words.

> Sometimes phrases/words get repeated multiple times in the summary.
---
## Proposed Methodology
* To tackle the problem of inaccurate facts, we will use a hybrid pointer generator that can copy words from the original text via pointing. This helps deal with the problem of out of vocabulary words. However, it is ensured that the ability to generate new words is not compromised.
* To avoid the repetition of words/phrases in the summary, we use a coverage vector to track and control the coverage of the original text. This will avoid repetition.
---
* Source of the image : “Get To The Point: Summarization with Pointer-Generator Networks”: Abigail See, Peter J. Liu, Christopher D. Manning
 
!["Information Source: “Get To The Point: Summarization with Pointer-Generator Networks”: Abigail See, Peter J. Liu, Christopher D. Manning
"](https://github.com/habiburrahmankhan/Abstractive_text_summarization/blob/main/articture.png)

--- 

## Dataset description
The dataset used contains over 3,00,000 news articles.
These news articles belong to two prominent news agencies:
* CNN
* Dailymail

### [The source of the dataset is: ](www.tensorflow.org/datasets/catalog/cnn_dailymail)

The distribution of the dataset will be as follows:
* Testing: 10,000 articles.
* Validation: 10,000 articles.
* Training: Rest of the dataset (Around 2,90,000).
Also, since the number of Dailymail articles(2,19,000) is greater than the number of CNN articles(92,000), the data from both sets have been divided proportionately in the aforementioned distribution (Testing, Validation, and Training).

* Before using the dataset we first prepare the data to be ready for fast and efficient processing.
* We first tokenize the data, then we convert our data into binary format, and then we divide the data into many files for our convenience.
* Since we are using Recurrent Neural Networks, we use sequential data in the form of tokens.
* To generate these tokens we perform tokenization of our articles as well as reference summaries.
* For tokenization, we use Stanford NLP Tokenizer which is a software that has been developed by Stanford University.

#### Creating vocabulary
* We also count the number of time each token appears in the dataset.
* With this we create a vocabulary file which list the token(word) and its frequency over the dataset.


[link of vocab file  ](https://github.com/habiburrahmankhan/Abstractive_text_summarization/blob/main/vocab)

Next, we convert the tokenized files into .bin(binary) files.
This is done to enable better efficiency and speedup the training process.
We generate three files:
1. Train.bin
2. Valid.bin
3. Test.bin

---
## Training & Validating 
* The model was trained using Google Colaboratory on around 3,00,000 news articles.
* It was trained for around 2,50,000 iterations (around 15 epochs).
* The model was validated on another 10,000 articles to check for overfitting.
* The model was also tested on 10,000 articles.

#### [Link of the Saved model  & generated summary ](https://drive.google.com/drive/u/5/folders/1lkhd8o2B_YMRu_gMvxGFCJKFxVN2FOia)


![image of training ](https://github.com/habiburrahmankhan/Abstractive_text_summarization/blob/main/visualisation_img/training_screen_shot.png)

### Training Loss Image 
![img](https://github.com/habiburrahmankhan/Abstractive_text_summarization/blob/main/visualisation_img/Training_loss.png)

### Validation  Loss Image 
![img](https://github.com/habiburrahmankhan/Abstractive_text_summarization/blob/main/visualisation_img/validation_loss.png)



---
* chunked folder contain **train and test** binary file of 1000 articles each. 

[link of all  file  ](https://github.com/habiburrahmankhan/Abstractive_text_summarization/tree/main/chunked)

* frontend folder contain file related to frontend visvalisation 
* visualisation_img folder contain screenshot taken during training 

#### to run 
```
!python /path of run_summariztion /run_summarization.py -mode=train --data_path=/path of chunked train /chunked/train_* --vocab_path=/path of vocab /vocab --log_root=/path to save checkpoint /check_point --exp_name=myexperiment --coverage=1
```
for detail visit this file **ats_run_file.ipynb**

---




### A report andd presentation is also available 
### read report or presentation  for clear understanding
* introduction
* literature review 
* proposed method 
* experimental result & explanation 
* conclustion & future work 

---

#### if you want to run on google colab use **ats_run_file.ipynb**

---

## Rough Score 
![rough scrore](https://github.com/habiburrahmankhan/Abstractive_text_summarization/blob/main/visualisation_img/screenshot_of_roughmatrix.png)






----
## -----------Thank you For Reading -------------
----

for any problem contact me ##### [hrkhan](https://hrkhan.in/)