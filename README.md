> NEW! Challenge winners announced!

# ClariQ Overview


ClariQ (pronounced as Claire-ee-que) challenge is organized as part of the Conversational AI challenge series (ConvAI3) at [Search-oriented Conversational AI (SCAI) EMNLP workshop in 2020](https://scai.info).
The main aim of the conversational systems is to return an appropriate answer in response to the user requests. However, some user requests might be ambiguous. In IR settings such a situation is handled mainly through the diversification of a search result page.
It is however much more challenging in dialogue settings. Hence, we aim to study the following situation for dialogue settings:

* a user is asking an ambiguous question (a question to which one can return > 1 possible answers);
* the system must identify that the question is ambiguous, and, instead of trying to answer it directly, ask a good clarifying question.

The main research questions we aim to answer as part of the challenge are the following:

* **RQ1**: When to ask clarifying questions during dialogues?
* **RQ2**: How to generate the clarifying questions?

The detailed description of the challenge can be found [in the following document](ConvAI3_ClariQ2020.pdf).

# How to participate?

- In order to get to the leaderboard please **register your team** [here](https://docs.google.com/forms/d/e/1FAIpQLSer8lvNvtt-SBwEtqZKjMtPJRWmw5zHUxoNgRJntzBIuVXrmw/viewform).
- The datasets, baselines and evaluation scripts for the Stage 1 are available in the following repository [https://github.com/aliannejadi/ClariQ](https://github.com/aliannejadi/ClariQ)
- [Email us if you have any questions](mailto:clariq@convai.io)
- [![Ask us questions at chat https://gitter.im/ClariQ/community](https://badges.gitter.im/ClariQ/community.svg)](https://gitter.im/ClariQ/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


# News 
- June 10, 2020: Microsoft Research is sponsoring data collection for the Stage 1
- July 7, 2020: Announcing the Stage 1 of ClariQ challenge 
- July 8, 2020: Announcing the performance of the baselines
- July 20, 2020: Send us your solution for Stage 1 every Friday via [email](mailto:clariq@convai.io) 
- July 25, 2020: Ask us question [![Join the chat at https://gitter.im/ClariQ/community](https://badges.gitter.im/ClariQ/community.svg)](https://gitter.im/ClariQ/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) 
- July 30, 2020: Please join our kick-off webinar on August 4, 8 am PST (convert to your time zone) using the following [meeting link](https://uva-live.zoom.us/j/91023840049), where 
    - we give a brief overview of the challenge;
    - show how to run baselines; 
    - answer all your questions.    
- July 30, 2020: Don't want to miss any updates please register [here](https://docs.google.com/forms/d/e/1FAIpQLSer8lvNvtt-SBwEtqZKjMtPJRWmw5zHUxoNgRJntzBIuVXrmw/viewform) 
- August 4, 2020: Google is sponsoring the competion prize (see the details below)
- August 4, 2020: We held the kick-off webinar. Missed it? You can watch the playback [here](https://www.youtube.com/watch?v=2cSLNScJqFk).
- August 10, 2020: New baselines for the `question_relevance` have been added. The code is also available on Google Colab. 
- September 08, 2020: Due to multiple requests, we have extended the deadline for participation in Stage 1 for one week.
- September 22, 2020: Amazon Science is sponsoring the Stage 2 of the challenge
- September 23, 2020: We are happy to announce four teams which were selected for the Stage 2: 
    - Karl
    - NTES_ALONG
    - TAL ML
    - Soda
- September 23, 2020: Stage 2 files and instructions are added to the ClariQ GitHub repo.
- November 19, 2020: Stage 2 results are out.
- November 19, 2020: Challenge winners are announced.

# Awards 

Google is sponsoring the competition award with the GCP Credits, which we are planning to award as follows:

* 1st place: ~~$2'500~~ $3'000 credits
* 2nd place: ~~$1'500~~ $2'000 credits
* ~~3rd place: $1'000 credits~~

**IMPORTANT!** Please note that GCP Credits can only be granted where available and are subject to the [Terms and Conditions](https://cloud.google.com/terms?hl=en) and product availability. If the competition winner is from a region where the program is not launched, we will, unfortunately, not be able to issue the prize. 

# Challenge Design

The challenge will be run in two stages:

## Stage 1: intial dataset (sponsored by Microsoft Research)
In Stage 1, we provide to the participants the datasets that include:
* **User Request:** an initial user request in the conversational form, e.g., "What is Fickle Creek Farm?", with a label reflects if clarification is needed to be ranged from 1 to 4;
* **Clarification questions:** a set of possible clarifying questions, e.g., "Do you want to know the location of fickle creek farm?";
* **User Answers:** each question is supplied with a user answer, e.g., "No, I want to find out where can i purchase fickle creek farm products."

To answer **RQ1**: Given a user request, return a score [1 −4] indicating the necessity of asking clarifying questions.

To answer **RQ2**: Given a user request which needs clarification, returns the most suitable clarifying question. Here participants are able to choose: (1) either select the clarifying question from the provided question bank (all clarifying questions we collected), aiming to maximize the precision, (2) or
choose not to ask any question (by choosing `Q0001` from the question bank.)

The dataset is stored in the following repository [https://github.com/aliannejadi/ClariQ](https://github.com/aliannejadi/ClariQ), together with evaluation scripts and baseline.

## Stage 2: human-in-the-loop (sponsored by Amazon Science)

The TOP-4 systems from Stage 1 are exposed to real users. Their responses—answers and clarifying questions—are rated by the users.
At that stage, the participating systems are put in front of human users. The systems are rated on their overall performance.
At each dialog step, a system should give either a factual answer to the user's query or ask for clarification.
Therefore, the participants would need to:
  - ensure their system can answer simple user questions
  - make their own decisions on when clarification might be appropriate
  - provide clarification question whenever appropriate
  - interpret user's reply to the clarifying question

The participants would need to strike a balance between asking too many questions
and providing irrelevant answers.

Note that the setup of this stage is quite different from Stage 1. Participating systems would likely need to operate as a generative model, rather than a retrieval model. One option would be to cast the problem as generative from the beginning and solve the retrieval part of Stage 1, e.g., by ranking the offered candidates by their likelihood.

Alternatively, one may solve Stage 2 by retrieving a list of candidate answers (e.g., by invoking Wikipedia API or the [Chat Noir](https://www.chatnoir.eu) API that we describe above) and ranking them as in Stage 1.

For further information about Stage 2 design and auxiliary files, please visit [ClariQ repo](https://github.com/aliannejadi/ClariQ).

# Timeline
- **Stage 1** will take place from July 7, 2020 -- ~~September 9, 2020~~ September 16, 2020. Up until ~~September 9, 2020~~ September 16, 2020 participants will be able to submit their models (source code) and solutions to be evaluated on the test set using automated metrics (which we will run on our servers).  The current leaderboards will be visible to everyone.
- **Stage 2** will start on ~~September 10, 2020~~ September 17 2020. On ~~September 10, 2020~~ September 17 2020 the run submission for Stage 1 will be locked, and the best teams will be invited to submit their codes for the second stage to be evaluated over the next month using crowd workers.


Winners will be announced at SCAI@EMNLP2020 which will take place in November 19-20 (exact details TBD).


# Evaluation

Participants' models will then be compared in two ways after two stages: 
*  automated evaluation metrics on a new test set hidden from the competitors; 
*  evaluation with crowd workers through MTurk.

The winning will be chosen based on these scores. 

## Metrics

There are three types of metrics we will evaluate:

* **Automated metrics** As system automatic evaluation metrics we use MRR, P@[1,3,5,10,20], nDCG@[1,3,5,20].
These metrics are computed as follows: a selected clarifying question, together with its corresponding answer are added to the original request.
The updated query is then used to retrieve (or re-rank) documents from the collection. The quality of a question is then evaluated by taking into account how much the question and its answer affect the performance of document retrieval. Models are also evaluated in how well they are able to rank relevant questions higher than other questions in the question bank. For this task, that we call 'question relevance', the models are evaluated in terms of Recall@[10,20,30]. Since the precision of models is evaluated in the document relevance task, here we focus only on recall.

* **Crowd workers** given the entrant's model code, we will run live experiments where Turkers chat to their model given instructions identical to the creation of the original dataset, but with new profiles, and then score its performance. Turkers will score the models between 1-5.

# Rules

* Participants must provide their source code so that the hidden test set evaluation and live experiments can be computed without the team's influence, and so that  the competition has further impact as those models can be released for future research to build off them. Code can be in any language but a thin python wrapper must be provided in order to work with our evaluation and live experiment code.
* We will require that the winning systems also release their training code so that their work is reproducible (although we also encourage that for all systems).
* Participants are free to augment training with other datasets as long as they are publicly released (and hence, reproducible). Hence, all entrants are expected to work on publicly available data or release the data they use to train. 


# Submission

## Stage 1
Please send two files per run as to `clariq@convai.io`, indicating your team's name, as well as your run ID. 
Each team is allowed to send a maximum of one run per week.
You'll also need to share your GitHub repository with us. The run files should be formatted as described below.

### Run file format
Each run consists of two separate files: 

* Ranked list of questions for each topic;
* Predicted `clarification_need` label for each topic. 

Below we explain how each file should be formatted.

#### Question ranking
This file is supposed to contain a ranked list of questions per topic. The number of questions per topic could be any number, but we evaluate only the top 30 questions. We follow the traditional TREC run format. Each line of the file should be formatted as follows:

    <topic_id> 0 <question_id> <ranking> <relevance_score> <run_id>

Each line represents a relevance prediction. `<relevance_score>` is the relevance score that a model predicts for a given `<topic_id>` and `<question_id>`. `<run_id>` is a string indicating the ID of the submitted run. `<ranking>` denotes the ranking of the `<question_id>` for `<topic_id>`. Practically, the ranking is computed by sorting the questions for each topic by their relevance scores.
Here are some example lines:

	170 0 Q00380 1 6.53252 sample_run
	170 0 Q02669 2 6.42323 sample_run
	170 0 Q03333 3 6.34980 sample_run
	171 0 Q03775 1 4.32344 sample_run
	171 0 Q00934 2 3.98838 sample_run
	171 0 Q01138 3 2.34534 sample_run

This run file will be used to evaluate both question relevance and document relevance. Sample runs can found in `./sample_runs/` directory.
Also, sample Google Colab Notebookes are available. Please check [ClariQ repo](https://github.com/aliannejadi/ClariQ) for more information.

#### Clarification need
This file is supposed to contain the predicted `clarification_need` labels. Therefore, the file format is simply the `topic_id` and the predicted label. Sample lines can be found below:

    171 1
    170 3
    182 4

More information and example run files can be found at [https://github.com/aliannejadi/ClariQ](https://github.com/aliannejadi/ClariQ).
## Stage 2
To submit an entry, create a private repo with your model that works with our evaluation code, and share it with the following github accounts: [aliannejadi](https://github.com/aliannejadi), [varepsilon](https://github.com/varepsilon), [julianakiseleva](https://github.com/julianakiseleva).

See [https://github.com/aliannejadi/ClariQ](https://github.com/aliannejadi/ClariQ) for example baseline submissions.

You are free to use any system (e.g. PyTorch, Tensorflow, C++,..) as long as you can wrap your model for the evaluation. The top level README should tell us your team name, model name, and where the eval_ppl.py, eval_hits.py etc. files are so we can run them. Those should give the numbers on the validation set. Please also include those numbers in the README so we can check we get the same. We will then run the automatic evaluations on the hidden test set and update the leaderboard. You can submit a maximum of once per week.

We will use the same submitted code for the top performing models for computing human evaluations when the submission system is locked on ~~September 9, 2020~~ September 17, 2020. The deadline for submitting systems for Stage 2 is November 1, 2020.

The submitted systems must produce the output in a reasonable time window (1-2 hours) on our system with the following configuration:
 
 * CPU: Core i7-7700
 * RAM: 32 Gb RAM
 * GPU: 1080 Ti
 
**Note:** All submitted systems must be accompanied with a ready-to-use Docker container.

# Automatic Evaluation Leaderboard (hidden test set)

## Document Relevance

**Dev**

| ًRank | Creator    | Model Name | MRR    | P@1    | nDCG@3 | nDCG@5 |
| ---- | ---------- | -------------------- | ------ | ------ | ------ | ------ |
| -    | ClariQ     | Oracle BestQuestion  | 0.4882 | 0.4187 | 0.3337 | 0.3064 |
| 1    | Karl       | Roberta              | 0.3640 | 0.2813 | 0.2002 | 0.1954 |
| 2    | NTES_ALONG | Reranker-v4          | 0.3761 | 0.3000 | 0.2113 | 0.1955 |
| 3    | Soda       | BERT+BM25-v2         | 0.3180 | 0.2437 | 0.1625 | 0.1550 |
| 4    | NTES_ALONG | Reranker-v2          | 0.3573 | 0.2625 | 0.2112 | 0.1982 |
| 5    | ClariQ     | BM25                 | 0.3096 | 0.2313 | 0.1608 | 0.1530 |
| 6    | Soda       | BERT+BM25            | 0.3096 | 0.2313 | 0.1608 | 0.1530 |
| 7    | ClariQ     | NoQuestion           | 0.3000 | 0.2063 | 0.1475 | 0.1530 |
| 8    | Pinta      | BERT-v3              | 0.3596 | 0.2750 | 0.1879 | 0.1882 |
| 9    | NTES_ALONG | BM25+Roberta         | 0.3606 | 0.2813 | 0.1942 | 0.1891 |
| 10  | CogIR      | BERTlets-fusion<br>-topics-passages | 0.3103 | 0.2125 | 0.1747 | 0.1701 |
| 11   | Pinta      | BERT                 | 0.3297 | 0.2250 | 0.1792 | 0.1701 |
| 12    | CogIR      | BERTlets-fusion-<br>topics-div-passages-v2       | 0.3315 | 0.2500 | 0.1763 | 0.1660 |
| 13    | CogIR      | BERTlets-fusion-<br>topics-div-passages       | 0.3236 | 0.2250 | 0.1739 | 0.1653 |
| 14   | Pinta      | BERT-v2              | 0.3158 | 0.2313 | 0.1669 | 0.1600  
| 15    | Karl       | Roberta-v2           | 0.3811 | 0.2938 | 0.2193 | 0.2093 |
| 16    | NTES_ALONG | Reranker-v3          | 0.3520 | 0.2687 | 0.2033 | 0.1925 |
| 17    | NTES_ALONG | Recall+Rerank        | 0.3627 | 0.2750 | 0.2047 | 0.1935 |
| 18   | Soda       | BERT-based-v2        | 0.3306 | 0.2437 | 0.1699 | 0.1702 |
| 19   | Soda       | BERT-based           | 0.3497 | 0.2625 | 0.1849 | 0.1762 |
| 20   | Algis      | USE-QA               | 0.3517 | 0.2563 | 0.1943 | 0.1815 |
| 21   | Pinta      | Triplet              | 0.3573 | 0.2688 | 0.1988 | 0.1920 |  
| 22   | TAL ML     | Roberta+++           | 0.3619 | 0.2750 | 0.2060 | 0.1979 |
| 23   | NTES_ALONG | Recall+Rescore       | 0.3722 | 0.2813 | 0.2185 | 0.2047 |  
| 24   | NTES_ALONG | BM25_plus+Roberta    | 0.3587 | 0.2813 | 0.1952 | 0.1869 |
| 25   | Algis      | BART-based           | 0.3628 | 0.2687 | 0.2003 | 0.1914 |
| 26   | TAL ML     | Roberta++            | 0.3583 | 0.2687 | 0.1977 | 0.1931 |
| 27   | ClariQ     | BERT-ranker          | 0.3453 | 0.2563 | 0.1824 | 0.1744 |
| 28   | ClariQ     | BERT-reranker        | 0.3453 | 0.2563 | 0.1824 | 0.1744 |
| -    | ClariQ     | Oracle WorstQuestion | 0.0841 | 0.0125 | 0.0252 | 0.0313 |

**Test**

| ًRank | Creator    | Model Name | MRR    | P@1    | <ins>nDCG@3</ins> | nDCG@5 |
| ---- | ---------- | -------------------- | ------ | ------ | ------ | ------ |
| -    | ClariQ     | Oracle BestQuestion  | 0.4881 | 0.4275 | **0.2107** | 0.1759 |
| 1    | Karl       | Roberta              | 0.3190 | 0.2342 | **0.1265** | 0.1130 |
| 2    | NTES_ALONG | Reranker-v4          | 0.3140 | 0.2379 | **0.1229** | 0.1097 |
| 3    | Soda       | BERT+BM25-v2         | 0.3216 | 0.2453 | **0.1196** | 0.1097 |
| 4    | NTES_ALONG | Reranker-v2          | 0.3034 | 0.2119 | **0.1171** | 0.1033 |
| 5    | ClariQ     | BM25                 | 0.3134 | 0.2193 | **0.1151** | 0.1061 |
| 6    | Soda       | BERT+BM25            | 0.3134 | 0.2193 | **0.1151** | 0.1061 |
| 7    | ClariQ     | NoQuestion           | 0.3223 | 0.2268 | **0.1134** | 0.1059 |
| 8    | Pinta      | BERT-v3              | 0.3044 | 0.2119 | **0.1131** | 0.1021 |
| 9    | NTES_ALONG | BM25+Roberta         | 0.3045 | 0.2156 | **0.1108** | 0.1025 |
| 10   | CogIR      | BERTlets-fusion<br>-topics-passages | 0.3025 | 0.2193 | **0.1078** | 0.0983 |
| 11   | Pinta      | BERT                 | 0.2934 | 0.2045 | **0.1078** | 0.0969 |
| 12    | CogIR      | BERTlets-fusion-<br>topics-div-passages-v2       | 0.2885 | 0.1859 | **0.1072** | 0.1010 |
| 13    | CogIR      | BERTlets-fusion-<br>topics-div-passages       | 0.2908 | 0.1970 | **0.1055** | 0.0990 |
| 14   | Pinta      | BERT-v2              | 0.2815 | 0.1933 | **0.1043** | 0.0934 |  
| 15    | Karl       | Roberta-v2           | 0.2890 | 0.1933 | **0.1035** | 0.0941 |
| 16    | NTES_ALONG | Reranker-v3          | 0.3006 | 0.2230 | **0.1031** | 0.0970 |
| 17    | NTES_ALONG | Recall+Rerank        | 0.2948 | 0.1933 | **0.1029** | 0.0919 |
| 18   | Soda       | BERT-based-v2        | 0.2803 | 0.1896 | **0.1021** | 0.0981 |
| 19   | Soda       | BERT-based           | 0.2600 | 0.1784 | **0.0983** | 0.0915 |
| 20    | Algis      | USE-QA               | 0.2782 | 0.1822 | **0.0978** | 0.1003 |
| 21   | Pinta      | Triplet              | 0.2672 | 0.1747 | **0.0968** | 0.0906 |  
| 22   | TAL ML     | Roberta+++           | 0.2835 | 0.2007 | **0.0965** | 0.0915 |
| 23   | NTES_ALONG | Recall+Rescore       | 0.2799 | 0.1970 | **0.0955** | 0.0856 |  
| 24   | NTES_ALONG | BM25_plus+Roberta    | 0.2720 | 0.1822 | **0.0930** | 0.0870 |  
| 25   | Algis      | BART-based           | 0.2622 | 0.1710 | **0.0923** | 0.0848 |
| 26   | TAL ML     | Roberta++            | 0.2602 | 0.1747 | **0.0922** | 0.0833 |
| 27   | ClariQ     | BERT-ranker          | 0.2562 | 0.1784 | **0.0896** | 0.0821 |
| 28   | ClariQ     | BERT-reranker        | 0.2553 | 0.1784 | **0.0892** | 0.0818 |
| -    | ClariQ     | Oracle WorstQuestion | 0.0541 | 0.0000 | **0.0097** | 0.0154 |

## Question Relevance

**Dev**

| ًRank | Creator    | Model Name   | Recall@5 | Recall@10 | Recall@20 | Recall@30 |
| ---- | ---------- | ------------- | -------- | --------- | --------- | --------- |
| 1    | NTES_ALONG | Reranker-v4   | 0.3604 | 0.6749 | 0.8478 | 0.8761 |
| 2    | NTES_ALONG | Reranker-v3   | 0.3648 | 0.6753 | 0.8510 | 0.8744 |
| 3    | NTES_ALONG | Reranker-v2   | 0.3648 | 0.6738 | 0.8417 | 0.8633 |
| 4    | CogIR      | BERTlets-fusion-<br>topics-div-passages-v2       | 0.3542 | 0.6424 | 0.7653 | 0.7997 |
| 5    | TAL ML     | Roberta++     | 0.3649 | 0.6694 | 0.8265 | 0.8587 |
| 6    | Karl       | Roberta-v2    | 0.3611 | 0.6539 | 0.7993 | 0.8384 |
| 7    | CogIR      | BERTlets-fusion<br>-topics-passages       | 0.3555   | 0.6429    | 0.7640    | 0.7854    |
| 8    | Karl       | Roberta       | 0.3618   | 0.6631    | 0.8128    | 0.8434    |
| 9    | Soda       | BERT+Bm25     | 0.3454   | 0.6166    | 0.7354    | 0.7621    |
| 10   | Soda       | BERT+Bm25-v2  | 0.3398   | 0.6166    | 0.7525    | 0.7792    |
| 11   | Soda       | BERT-based    | 0.3523   | 0.6247    | 0.7354    | 0.7636    |
| 12   | NTES_ALONG | Recall+Rerank | 0.3674   | 0.6678    | 0.7869    | 0.8085    |
| 13   | Soda       | BERT-based-v2 | 0.3544   | 0.6287    | 0.7544    | 0.8177    |
| 14    | Pinta      | BERT          | 0.3492 | 0.6196 | 0.7337 | 0.7632 |
| 15    | CogIR      | BERTlets-fusion-<br>topics-div-passages       | 0.3528 | 0.6393 | 0.7506 | 0.7890 |
| 16    | NTES_ALONG | BM25_plus+Roberta | 0.3637 | 0.6409  | 0.7484    | 0.7793    |
| 17    | Pinta      | BERT-v3       | 0.3583 | 0.6358 | 0.7616 | 0.7852 |
| 18   | NTES_ALONG | Recall+Rescore | 0.3648  | 0.6553    | 0.8230    | 0.8367    |
| 19   | ClariQ     | BERT-ranker   | 0.3494   | 0.6134    | 0.7248    | 0.7542    |
| 20   | Pinta      | BERT-v2              | 0.3528 | 0.6393 | 0.7506 | 0.7890 |
| 21   | Algis      | BART-based    | 0.3333 | 0.5910 | 0.6689 | 0.6926 
| 22   | Algis      | USE-QA        | 0.3469   | 0.6112    | 0.7052    | 0.7228    |
| 23    | NTES_ALONG | BM25+Roberta  | 0.3629  | 0.6389    | 0.7285    | 0.7657    |
| 24   | TAL ML     | Roberta+++     | 0.3508 | 0.6215 | 0.7672 | 0.7978 |
| 25   | ClariQ     | BERT-reranker | 0.3475   | 0.6122    | 0.6913    | 0.6913    |
| 26   | ClariQ     | BM25          | 0.3245   | 0.5638    | 0.6675    | 0.6913    |
| 27   | Pinta      | Triplet       | 0.3471   | 0.5871    | 0.6653    | 0.6846    |

**Test**

| ًRank | Creator    | Model Name   | Recall@5 | Recall@10 | Recall@20 | <ins>Recall@30</ins> |
| ---- | ---------- | ------------- | -------- | --------- | --------- | --------- |
| 1    | NTES_ALONG | Reranker-v4   | 0.3404 | 0.6329 | 0.8335 | **0.8744** |
| 2    | NTES_ALONG | Reranker-v3   | 0.3414 | 0.6351 | 0.8316 | **0.8721** |
| 3    | NTES_ALONG | Reranker-v2   | 0.3382 | 0.6242 | 0.8177 | **0.8685** |
| 4    | CogIR      | BERTlets-fusion-<br>topics-div-passages-v2       | 0.3384 | 0.6314 | 0.8073 | **0.8573** |
| 5    | TAL ML     | Roberta++     | 0.3395 | 0.6251 | 0.8176 | **0.8568** |
| 6    | Karl       | Roberta-v2    | 0.3355 | 0.6237 | 0.7990 | **0.8492** |
| 7    | CogIR      | BERTlets-fusion<br>-topics-passages       | 0.3314   | 0.6149    | 0.8074    | **0.8448**    |
| 8    | Karl       | Roberta       | 0.3406   | 0.6255    | 0.8006    | **0.8436**    |
| 9    | Soda       | BERT+BM25     | 0.3272   | 0.6061    | 0.8013    | **0.8433**    |
| 10   | Soda       | BERT+BM25-v2  | 0.3013   | 0.5866    | 0.8006    | **0.8433**    |
| 11   | Soda       | BERT-based    | 0.3338   | 0.6099    | 0.8023    | **0.8432**    |
| 12   | NTES_ALONG | Recall+Rerank | 0.3435   | 0.6296    | 0.7959    | **0.8424**    |
| 13   | Soda       | BERT-based-v2 | 0.3067   | 0.5893    | 0.7991    | **0.8415**    |   
| 14    | Pinta      | BERT          | 0.3438 | 0.6228 | 0.7987 | **0.8409** |
| 15    | CogIR      | BERTlets-fusion-<br>topics-div-passages       | 0.3333 | 0.6225 | 0.8039 | **0.8392** |
| 16    | NTES_ALONG | BM25_plus+Roberta | 0.3361 | 0.6219  | 0.7960    | **0.8360**    |
| 17    | Pinta      | BERT-v3       | 0.3291 | 0.6066 | 0.7902 | **0.8345** |
| 18   | NTES_ALONG | Recall+Rescore | 0.3432  | 0.6229    | 0.7857    | **0.8211**    |
| 19   | ClariQ     | BERT-ranker   | 0.3440   | 0.6242    | 0.7849    | **0.8190**    |
| 20   | Pinta      | BERT-v2              | 0.3271 | 0.6012 | 0.7884 | **0.8188** |  
| 21   | Algis      | BART-based    | 0.3408 | 0.6156 | 0.7721 | **0.8081** |
| 22   | Algis      | USE-QA        | 0.3454   | 0.6071    | 0.7688    | **0.8013**    |
| 23    | NTES_ALONG | BM25+Roberta | 0.3329   | 0.6027    | 0.7650    | **0.8004**    |
| 24   | TAL ML     | Roberta+++     | 0.3212 | 0.5786 | 0.7204 | **0.7739** |
| 25   | ClariQ     | BERT-reranker | 0.3444   | 0.6062    | 0.7585    | **0.7682**    |
| 26   | ClariQ     | BM25          | 0.3170   | 0.5705    | 0.7292    | **0.7682**    |
| 27   | Pinta      | Triplet       | 0.3330   | 0.5809    | 0.7289    | **0.7589**    |


## Clarification Need Prediction

<table>
  <tr>	  
    <td rowspan="2">ً<b>Rank</b></td>
    <td rowspan="2"><b>Creator</b></td>
    <td rowspan="2"><b>Model Name</b></td>
    <td colspan="3" align="center"><b>Dev</b></td>
    <td colspan="3" align="center"><b>Test</b></td>
  </tr>
  <tr>
    <td><b>P</b></td>
    <td><b>R</b></td>
    <td><b>F1</b></td>
    <td><b>P</b></td>    
    <td><b>R</b></td>
    <td><b><u>F1</u></b></td>
  </tr>
  <tr>
    <td>1</td>
    <td>TAL ML</td>
    <td>Roberta+++</td>
<td>0.6039</td>
<td>0.5600</td>
<td>0.5551</td>
<td>0.5981</td>
<td>0.6557</td>
	  <td><b>0.6070</b></td>
  </tr>
  <tr>
    <td>2</td>
    <td>CactusJam</td>
    <td>Roberta+<br>Stats</td>
    <td>0.6200</td>
<td>0.5800</td>
<td>0.5717</td>
<td>0.5963</td>
<td>0.5902</td>
  <td><b>0.5416</b></td>
  </tr>
  <tr>
    <td>3</td>
    <td>TAL ML</td>
    <td>Roberta++</td>
    <td>0.5807</td>
<td>0.5400</td>
<td>0.5375</td>
<td>0.5290</td>
<td>0.5574</td>
	  <td><b>0.5253</b></td>
  </tr>	
  <tr>
    <td>4</td>
    <td>Algis</td>
    <td>Roberta+<br>CatBoost</td>
    <td>0.1402</td>
    <td>0.2800</td>
    <td>0.1854</td>
    <td>0.5171</td>    
    <td>0.5246</td>
    <td><b>0.5138</b></td>
  </tr>
<tr>
    <td>5</td>
    <td>NTES_ALONG</td>
    <td>cneed_add_<br>prior_v2</td>
    <td>0.6200</td>
<td>0.6000</td>
<td>0.5984</td>
<td>0.5007</td>
<td>0.5082</td>
	<td><b>0.5018</b></td>
  </tr>
<tr>
    <td>6</td>
    <td>NTES_ALONG</td>
    <td>cneed_merge</td>
    <td>0.5830</td>
    <td>0.5200</td>
    <td>0.5192</td>
    <td>0.4847</td>    
    <td>0.5082</td>
	<td><b>0.4960</b></td>
  </tr>

<tr>
    <td>7</td>
    <td>NTES_ALONG</td>
    <td>cneed_dist</td>
    <td>0.5452</td>
    <td>0.5200</td>
    <td>0.5177</td>
    <td>0.4852</td>    
    <td>0.4918</td>
	<td><b>0.4868</b></td>
  </tr>
  <tr>
    <td>8</td>
    <td>Karl</td>
    <td>Roberta-v2</td>
    	<td>0.4609</td>
	<td>0.4600</td>
	<td>0.4356</td>
	<td>0.4465</td>
	<td>0.5410</td>
	  <td><b>0.4871</b></td>
  </tr>
  <tr>
    <td>9</td>
    <td>NTES_ALONG</td>
    <td>Roberta+prior</td>
    <td>0.4554</td>
    <td>0.4600</td>
    <td>0.4567</td>
    <td>0.4926</td>    
    <td>0.4754</td>
	  <td><b>0.4799</b></td>
  </tr>
  <tr>
    <td>10</td>
    <td>Algis</td>
    <td>BartBoost</td>
<td>0.7008</td>
<td>0.7000</td>
<td>0.6976</td>
<td>0.4813</td>
<td>0.4754</td>
	<td><b>0.4756</b></td>
  </tr>
  <tr>
    <td>11</td>
    <td>Soda</td>
    <td>BERT-based-v2</td>
    <td>0.5218</td>
    <td>0.4800</td>
    <td>0.4253</td>
    <td>0.3931</td>    
    <td>0.4918</td>
	  <td><b>0.4350</b></td>
  </tr>
  <tr>
    <td>12</td>
    <td>Soda</td>
    <td>BERT-based</td>
    <td>0.5224</td>
    <td>0.5400</td>
    <td>0.5180</td>
    <td>0.3901</td>    
    <td>0.4754</td>
	  <td><b>0.4282</b></td>
  </tr>
<tr>
    <td>13</td>
    <td>Soda</td>
    <td>BERT+BM25</td>
    <td>0.5386</td>
    <td>0.5600</td>
    <td>0.5360</td>
    <td>0.3930</td>    
    <td>0.4754</td>
	<td><b>0.4273</b></td>
  </tr>
<tr>
    <td>14</td>
    <td>Soda</td>
    <td>BERT+BM25-v2</td>
    <td>0.5992</td>
    <td>0.5800</td>
    <td>0.5793</td>
    <td>0.4304</td>    
    <td>0.4262</td>
	<td><b>0.4207</b></td>
  </tr>
<tr>
    <td>15</td>
    <td>Pinta</td>
    <td>BERT-v3</td>
<td>0.4083</td>
<td>0.5000</td>
<td>0.4248</td>
<td>0.3789</td>
<td>0.4590</td>
	<td><b>0.4147</b></td>
  </tr>
<tr>
    <td>16</td>
    <td>Pinta</td>
    <td>Triplet</td>
    <td>0.4161</td>
    <td>0.4800</td>
    <td>0.4178</td>
    <td>0.3665</td>    
    <td>0.4590</td>
	<td><b>0.4074</b></td>
  </tr>
  <tr>
    <td>17</td>
    <td>Pinta</td>
    <td>BERT</td>
<td>0.5204</td>
<td>0.5000</td>
<td>0.5014</td>
<td>0.3929</td>
<td>0.4098</td>
	  <td><b>0.4004</b></td>
  </tr>
  <tr>
    <td>18</td>
    <td>NTES_ALONG</td>
    <td>Roberta</td>
    <td>0.3967</td>
    <td>0.5200</td>
    <td>0.4305</td>
    <td>0.3546</td>    
    <td>0.4754</td>
	  <td><b>0.3995</b></td>
  </tr>
  <tr>
    <td>19</td>
    <td>Pinta</td>
    <td>XGB</td>
    <td>0.5027</td>
<td>0.4800</td>
<td>0.4841</td>
<td>0.3776</td>
<td>0.3770</td>
	  <td><b>0.3771</b></td>
  </tr>
</table>

# Stage 2: Multi-turn Conversations Evalation

## Document Relevance

**Test**

| ًRank | Creator    | Model Name | MRR    | P@1    | nDCG@3 | nDCG@5 |
| ---- | ---------- | -------------------- | ------ | ------ | ------ | ------ |
| 1    | NTES_ALONG   | -              | 0.1798 | 0.1161 | 0.0553 | 0.0536 |
| 2    | TAL ML       | -              | 0.1669 | 0.1067 | 0.0522 | 0.0494 |

# Challenge Winners

- First place: NTES_ALONG: Wenjie Ou, Yue Lin
- Second place: TAL ML: Hang Li, Yu Kang, Tianqiao Liu, Guowei Xu, Wenbiao Ding, Zitao Liu

# Organizing team
 
- [Mohammad Aliannejadi](http://aliannejadi.com), *University of Amsterdam*, Amsterdam
- [Julia Kiseleva](https://twitter.com/julia_kiseleva), *Microsoft Research*, Seattle
- [Mikhail Burtsev](https://www.linkedin.com/in/mikhail-burtsev-85a47b9/), *MIPT*, Moscow
- [Aleksandr Chuklin](https://www.linkedin.com/in/chuklin/), *Google AI*, Zürich
- [Jeff Dalton](http://www.dcs.gla.ac.uk/~jeff/), *University of Glasgow*, Glasgow


# Previous ConvAI competitions

- [ConvAI @ NIPS 2017](http://convai.io/2017) (The Conversational Intelligence Challenge) 
- [ConvAI2 @ NeurIPS 2018](http://convai.io/2018) (The Persona-Chat Challenge).

# Sponsors
Sponsorship of data collection:

The Stage 1 of the challenge is sponsored by:
<a href="https://www.microsoft.com/en-us/research/" style="max-width: 60%"><img src="ms_logo.png"></a>

The Stage 2 of the challenge is sponsored by:
<a href="https://www.amazon.science/" style="max-width: 30%"><img src="amazon.science high-res Logo.png"></a>

Participants prize is sponsored by:
<a href="https://research.google" style="max-width: 30%"><img src="google_logo.png"></a>

