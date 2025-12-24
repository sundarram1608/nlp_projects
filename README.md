### Course Work "INFO 555 Applied Natural Language Processing"
---

This repository contains the assignments successfully completed as a part of course work of Masters in Information Science with emphasis on Machine Learning with University of Arizona. <br> The assignments include:<br>
- Text Preprocessing<br>
- Text Similarity<br>
- Text Classification<br>
- Sequence Processing<br>
- Pre Trained Language Model<br>

Each of these assignments include seperate README.md that helps with the installation & use of the repositories.  

---

> ### Text Preprocessing<br>

This assignment includes text extraction, text cleaning, Tokenization and structuring the dataset.<br>
Libraries such as spacy, beautifulsoup, re & pandas are leveraged.<br>

---

> ### Text Similarity<br>

In this assignment, [Semantic Textual Similarity](https://alt.qcri.org/semeval2017/task1/) (STS) shared task organized within the 2017 editions of SemEval has been worked upon. The STS of sentence-pairs in English has been measured using Cosine Similarity and Word Mover's Distance. The task involved producing real-valued similarity scores ranging from 0 for complete dissimilar sentences to 5 for completely equivalent sentences, as can be seen in the following examples:

| Sentence 1                                              | Sentence 2                                            | Score |
| :---                                                    | :----                                                 | ---:  |
| The bird is bathing in the sink.                        | Birdie is washing itself in the water basin.          |   5   |
| John said he is considered a witness but not a suspect. | “He is not a suspect anymore.” John said.             |   3   |
| The black dog is running through the snow.              | A race car driver is driving his car through the mud. |   0   |

[gensim](https://radimrehurek.com/gensim/), a **Python** library that provides functionality to obtain text representations based on word embeddings (GloVe) has been used to obtain the numerical text representations<br>

---

> ### Text Classification<br>

In this assignment, [OffensEval](https://sites.google.com/site/offensevalsharedtask/) shared task, a part of the 2019 and 2020 editions of SemEval for Offensive language identification (Offensive/ non-offensive) and Automatic categorization of offense types(targeted or not) are worked upon.

[scikit-learn](https://scikit-learn.org/stable/), a **Python** Machine Learning library is leveraged<br>

---

> ### Sequence Processing<br>

In this assignment, [MeasEval](https://competitions.codalab.org/competitions/25770) shared task that was part of SemEval-2021 to extract counts, measurements, and related context from scientific documents has been worked upon. This complex task involved solving a number of steps that range from identifying quantities and units of measurement to identify relationships between them. <br>

This assignment contains two parts:<br>
- **Sequence Labelling**
  In this part, the focus was *Quantity* recognition (eg. *12 kg*) step that was approached as a Sequence Labelling task. <br> Recurrent Neural Network with [keras](https://keras.io/), a high-level Deep Learning API written in **Python** that provides a user-friendly interface for the [TensorFlow](https://www.tensorflow.org/) library, one of the most popular low-level Deep Learning frameworks is leveraged. <br>
  
- **Relation Extraction**
  In this part, the focus was to extract the *HasQuantity* relation. Given a sentence and the entities it contains, identify the *HasQuantity* relations that link *Quantity* entities with entities of other types. The task was approached as a Pairwise Relation Extraction. <br>
For example, the sentence in the image below contains 1 *Quantity* entity and 2 entities of other types, but only one of the latter is linked to the *Quantity* through the *HasQuantity* relation.

  ![image](sequence-processing/img/hasquantity.png)

  Convolutional Neural Network with [keras](https://keras.io/) is leveraged.

---

> ### Pre Trained Language Model<br>

In this assignment, [ComVE](https://competitions.codalab.org/competitions/21080) shared task that was part of SemEval-2020 to evaluate whether a system can distinguish if a natural language statement makes sense to humans or not and provide a reason has been worked up on. **ComVE** includes three subtasks that require models to acquire and apply commonsense knowledge.

- **SubTask A**<br>
  Given two similar statements that differ by only a few words, select the statement of the two that does not make sense.<br> For example, within the statements below, *Statement 2* is the nonsensical statement:<br>
     -- *Statement 1*: He put a turkey into the fridge.    
     -- *Statement 2*: He put an elephant into the fridge. <br>
  
  This subtask was approached as a Text Matching problem where the input is the two statements and the output is a label indicating which is the nonsensical one.

- **SubTask B**<br>
  Given a statement that does not make sense and three possible reasons, select which reason explains why the given statement is against common sense. For example, for the following nonsensical statement the correct answer is *Reason A*:<br>
    -- *Statement*: He put an elephant into the fridge.
    -- *Reason A*: An elephant is much bigger than a fridge.  
    -- *Reason B*: Elephants are usually white while fridges are usually white.  
    -- *Reason C*: An elephant cannot eat a fridge.<br>
       
  This subtask was approached as a Multiple Choice problem where the input is the nonsensical statement and the three possible explanations, and the output is a label indicating which of the reasons is the correct one.

- **SubTask C**<br>
  Given a statement that does not make sense, generate the reason why this statement does not make sense. For each nonsensical statement, three valid reasons are given as reference:<br>
    -- *Statement*: He put an elephant into the fridge.  
    -- *Reason A*: An elephant is much bigger than a fridge.  
    -- *Reason B*: A fridge is much smaller than an elephant.  
    -- *Reason C*: Most of the fridges aren't large enough to contain an elephant.<br>

  This subtask was approached as a Sequence-to-Sequence problem where the input is the nonsensical statement and the output is a valid reason.

For all these subtasks, Pre-trained Language Model [RoBERTa](https://huggingface.co/docs/transformers/model_doc/roberta), a model that uses **BERT**'s architecture was fine-tuned with [Transformers](https://huggingface.co/docs/transformers/index) library of Huggingface.<br>

