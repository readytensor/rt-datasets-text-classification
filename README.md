# Datasets for Text-Classification Base category on Ready Tensor

This repo contains all files related to the datasets used in algorithm evaluation for the Text Classification - Base category.

The `datasets` folder contains the main data files and the schema files for all the benchmark datasets under Text Classification - Base category. Within each dataset folder in `datasets`:

- The `raw` folder contains the original data files from the source (see attributions below).
- `processed` folder contains the compressed, processed files. These files are used in algorithm evaluations. The file with suffix "\_train.csv" is used for training, "\_test.csv" is used for testing (without the targets), "\_test_key.csv" contains the targets for the test data. This test key file is used to generate scores by comparing with predictions. The JSON file with suffix "\_schema.json" is the schema file for the corresponding dataset.
- The Jupyter notebook file within each dataset folder is used to convert the raw data file(s) in `raw` folder into the processed form in `processed` folder.
- The folder `schema_cfg` contains a csv which is needed by the schema generation script (described below) .

`schema_gen` folder contains a schema gen config file (YAML) and a python script which are used to generate the JSON schema files stored in the `processed` folder for each dataset. The generated schema file conforms to the Ready Tensor specification for this category.

---

The following is the list of datasets along with a brief description for each and its attribution:

---

## Amazon Musical Instruments Reviews

#### Alias (in scorecards): musical_instruments

#### Domain / Industry: Ecommerce / Music

#### Description

This is a dataset of feedback on musical instruments sold on Amazon. Features include the review text, a summary of the review, and the overall rating (on a 1-5 integer scale). The task in this case is to correctly classify each sample using the review text and the summary into one of the five rating categories.
The text field is created by concatenating the ‘summary’ and ‘reviewText’ fields in the original data.

#### Dataset characteristics

- number of samples = 10,261
- number of classes = 5

#### Attribution

Original data is available on Kaggle here:
https://www.kaggle.com/datasets/eswarchandt/amazon-music-reviews

---

## Clickbait

#### Alias (in scorecards): clickbait

#### Domain / Industry: Technology / News / Media

#### Description

This dataset contains a collection of two types of headlines - clickbait and non-clickbait.
The clickbait article headlines are collected from ‘BuzzFeed’, ‘Upworthy’, ‘ViralNova’, ‘Thatscoop’, ‘Scoopwhoop’ and ‘ViralStories’.
The non-clickbait article headlines are collected from ‘WikiNews’, ’New York Times’, ‘The Guardian’, and ‘The Hindu’.
The task is to accurately classify a headline into the clickbait or non-clickbait class.

#### Dataset characteristics

- number of samples = 10,000\*
- number of classes = 2
- Original dataset contains 32,000 samples. A random sample of 10,000 was chosen to fit within the size specifications for the Text-Classification Base category.

#### Attribution

Data comes from this study:

Abhijnan Chakraborty, Bhargavi Paranjape, Sourya Kakarla, and Niloy Ganguly. "Stop Clickbait: Detecting and Preventing Clickbaits in Online News Media”. In Proceedings of the 2016 IEEE/ACM International Conference on Advances in Social Networks Analysis and Mining (ASONAM), San Fransisco, US, August 2016.

Original data can be found here:

https://github.com/bhargaviparanjape/clickbait?ref=hackernoon.com

---

## Drug Reviews

#### Alias (in scorecards): drug_reviews

#### Domain / Industry: Healthcare / Pharmaceutical

#### Description

The dataset provides patient reviews on specific drugs along with related conditions. Furthermore, reviews are grouped into reports on the three aspects benefits, side effects and overall comment. Additionally, ratings are available concerning overall satisfaction as well as a 5 step side effect rating and a 5 step effectiveness rating. The data was obtained by crawling online pharmaceutical review sites.

The the 5-step effectiveness rating is used as the target feature.

The three types of reviews (namely, benefits, side effects, and overall comment) are concatenated into a single document and used as the input document for the classification task.

The task is to predict the 5-step effectiveness rating class using the three review fields.

#### Dataset characteristics

- number of samples = 4,143
- number of classes = 5

#### Attribution

Source:

Surya Kallumadi
Kansas State University
Manhattan, Kansas, USA

Felix Gräßer
Institut für Biomedizinische Technik
Technische Universität Dresden
Dresden, Germany

Original data can be found here:

https://archive.ics.uci.edu/ml/datasets/Drug+Review+Dataset+(Druglib.com)

UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.

---

## Ecommerce Categories

#### Alias (in scorecards): ecommerce_categories

#### Domain / Industry: Ecommerce / Retail

#### Description

This is the classification based E-commerce text dataset. There are 4 categories of products - "Electronics", "Household", "Books" and "Clothing & Accessories", which are the most common products sold on most ecommerce websites. The task is to predict the category of the product given its description.

#### Dataset characteristics

- number of samples = 50,428
- number of classes = 4

#### Attribution

Dataset is available on Kaggle:

https://www.kaggle.com/datasets/saurabhshahane/ecommerce-text-classification

Original source:

Gautam. (2019). E commerce text dataset (version - 2) [Data set]. Zenodo.

https://doi.org/10.5281/zenodo.3355823

---

## Fake Job Postings

#### Alias (in scorecards): fake_job_postings

#### Domain / Industry: Employment / Human Resources / Miscellaneous

#### Description

This dataset contains ~18K job descriptions out of which about 800 are fake. The data consists of both textual information and meta-information about the jobs. The dataset can be used to create classification models which can learn the job descriptions which are fraudulent.

The task is to classify each job posting into the fake vs genuine categories using the concatenated text from company profile, description, and requirements fields.

#### Dataset characteristics

- number of samples = 17,880
- number of classes = 2

#### Attribution

Original dataset is available on Kaggle:

https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction

Acknowledgement:

The University of the Aegean | Laboratory of Information & Communication Systems Security

---

## Hate Speech

#### Alias (in scorecards): hate_speech

#### Domain / Industry: Internet / Media / Social Network

#### Description

This dataset contains 24783 tweets which have been categorized into three classes: offensive language, hate speech, and neither. The task is to accurate categorize each tweet into the correct class.

Caution: The data contains content that is racist, sexist, homophobic, and offensive in many ways.

#### Dataset characteristics

- number of samples = 24,783
- number of classes = 3

#### Attribution

Data comes from this study:

Davidson, Thomas and Warmsley, Dana and Macy, Michael and Weber, Ingmar,
``Automated Hate Speech Detection and the Problem of Offensive Language'', Proceedings of the 11th International AAAI Conference on Web and Social Media, 2017.

Data can be found here:

https://github.com/t-davidson/hate-speech-and-offensive-language

---

## Movie Reviews

#### Alias (in scorecards): movie_reviews

#### Domain / Industry: Entertainment / Film

#### Description

This dataset contains 2,000 movie review documents labeled with respect to their overall sentiment polarity (positive or negative). The task is to predict the sentiment polarity using the review text.

#### Dataset characteristics

- number of samples = 2,000
- number of classes = 2

#### Attribution

Data comes from this study:

Bo Pang and Lillian Lee,
``A Sentimental Education: Sentiment Analysis Using Subjectivity Summarization
Based on Minimum Cuts'', Proceedings of the ACL, 2004.

Data can be found here:

http://www.cs.cornell.edu/people/pabo/movie-review-data

Dataset on page: polarity dataset v2.0

---

## Newsgroups

#### Alias (in scorecards): newsgroups

#### Domain / Industry: News / Media

#### Description

The newsgroups dataset comprises around ~18,000 newsgroups posts that are organized into 20 different newsgroups, each corresponding to a different topic. Some of the newsgroups are very closely related to each other (e.g. comp.sys.ibm.pc.hardware / comp.sys.mac.hardware), while others are highly unrelated (e.g misc.forsale / soc.religion.christian).

The task is to predict the newsgroup (i.e. one of the 20 topics) given the text in the post.

The original dataset was split into train and test sets based on messages posted before and after a specific date. In our evaluation, we combined all the data from the splits, and created random 90%/10% splits over this combined dataset for training and evaluation to keep the evaluation setup consistent across all benchmark datasets.

The data was obtained from scikit-learn datasets which provided an ability to remove meta-data such as headers, footers and quotes (references to other posts in a thread). We have used these filters so that the text classification task is focused on the main post content, rather than other meta-data.

We removed a small number of posts which became null (empty) after removal of meta-data.

#### Dataset characteristics

- number of samples = 18,466
- number of classes = 20
  Note that the original dataset contains a total of 18,846 samples over the train and test splits. We have applied filters (described in the ‘Description’ section above) which then yielded the final dataset with 18,466 samples.

#### Attribution

Original data can be found here:

http://qwone.com/~jason/20Newsgroups/

The same is available (with additional filtering) with scikit-learn. See documentation here:

https://scikit-learn.org/stable/modules/generated/sklearn.datasets.fetch_20newsgroups.html#sklearn.datasets.fetch_20newsgroups

---

## Spam Text

#### Alias (in scorecards): spam_text

#### Domain / Industry: Telecom

#### Description

The SMS Spam Collection is a public set of SMS labeled messages that have been collected for mobile phone spam research. The task involves classifying the messages into spam or ham (i.e. not-spam).

#### Dataset characteristics

- number of samples = 5,574
- number of classes = 2

#### Attribution

Source:

Tiago A. Almeida
Department of Computer Science
Federal University of Sao Carlos (UFSCar)
Sorocaba, Sao Paulo - Brazil

JosÃ© MarÃ­a GÃ³mez Hidalgo
R&D Department Optenet
Las Rozas, Madrid - Spain

Data can be found here:

https://archive.ics.uci.edu/ml/datasets/SMS+Spam+Collection

UCI Machine Learning Repository [http://archive.ics.uci.edu/ml]. Irvine, CA: University of California, School of Information and Computer Science.

---

## Tweet Emotions

#### Alias (in scorecards): tweet_emotions

#### Domain / Industry: Internet / Media / Social Network

#### Description

The data is a collection of tweets annotated with the emotions behind them.

Each tweet is classified into one of 13 different emotions.

#### Dataset characteristics

- number of samples = 8,000
- number of classes = 13
  Original dataset contains 39,827 samples. A random sample of 8,000 was chosen to fit within the size specifications for this problem category.

#### Attribution

This public domain dataset is collected from data.world platform who have kindly released it under Public License.

Dataset can be found here:

https://www.kaggle.com/pashupatigupta/emotion-detection-from-text

---
