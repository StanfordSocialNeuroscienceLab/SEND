# Information Repository for the Stanford Emotional Narratives Dataset

This repository contains information about the first version of the Stanford Emotional Narratives Dataset (SENDv1), described in the following [paper](http://dx.doi.org/10.1109/TAFFC.2019.2955949):

Ong, D. C., Wu, Z., Zhi-Xuan, T., Reddan, M., Kahhale, I., Mattek, A., & Zaki, J. (2021). Modeling emotion in complex stories: the Stanford Emotional Narratives Dataset. *IEEE Transactions on Affective Computing*, 12(3), 579-594.

This repository is maintained by Desmond Ong. Questions, comments, etc should be directed to desmond (dot) ong (at) utexas (dot) edu

We plan to release (parts of) the SEND to researchers in psychology, affective computing and related fields for research purposes only.





### Description of the SENDv1

In the SENDv1 reported in the Transactions on Affective Computing [paper](http://dx.doi.org/10.1109/TAFFC.2019.2955949), participants were invited into the lab to share positive and negative events in their lives. Recordings were self-paced, and there was no experimenter in the room. 

Participants' privacy and comfort were our top priority: after the videos were made, participants watched them again, and were then asked to consent for us to use each video in future research. If participants chose to withhold consent from any video, the experimenter would immediately delete that video in front of the participants, and this was made clear to the participants. Consent was entirely voluntary, with no penalty for withholding consent. 

- One level of consent (which we will label "Limited-Use") allowed us to let future participants watch the videos (for example, to collect additional ratings), but not to be shared with the general public.
- The most permissive level of consent (which we will label "Share-Ok") allowed us to show screenshots or clips in public, and to release these clips to researchers.

We then selected a subset of the consented videos to form the first version of the SEND. Of the 193 video clips in the SENDv1, 81 (42%) were consented at "Limited-Use", with the remaining 112 (58%) were consented at the more permissive "Share-Ok". The breakdown of consent according to the 60:20:20 Train/Valid/Test set that we report in the paper is:


| Levels | Train | Validation | Test | Total |
| ---  | --- | --- | --- | --- |
| Limited-Use | 60 clips | 13 clips | 8 clips | 81 clips |
| Share-Ok | 54 clips | 27 clips | 31 clips | 112 clips |
| Total | 114 clips | 40 clips | 39 clips | 193 clips |


Academic researchers can request access to the SENDv1 (see below), and can gain access to the raw videos only for the videos with "Share-Ok" consent. Researchers will be able to access, for all videos, (i) extracted features, and (ii) valence ratings. More details about the extracted features and the valence ratings can be found in our [paper](http://dx.doi.org/10.1109/TAFFC.2019.2955949), referenced at the top of this readme. The table below offers a clearer summary of what data can be accessed:


| Data | Limited-Use Consent | Share-Ok Consent |
| --- | --- | --- |
| Raw video/transcript | No | Yes |
| Extracted video features - AUs extracted using Emotient by iMotions | Yes | Yes |
| Extracted acoustic features - eGeMAPS using openSmile | Yes | Yes |
| Extracted linguistic features - GloVe embeddings (averaged over 5s windows) | Yes | Yes |
| Self-report valence ratings | Yes | Yes |
| Crowd-sourced independent observer ratings of speaker valence | Yes | Yes |


### Licenses and Requesting Access

In order to request access to the SEND, please fill out this [form](https://docs.google.com/forms/d/e/1FAIpQLSeDOEVB5p_W-MagZbIKQoB3pFCb0JW-NX7Br068M8m1ILJ3Lg/viewform?usp=sf_link). You will have to agree to the end-user license agreement.


### Performance Results of Different Models on SEND
Multiple deep learning models were built to solve the SEND task as a time-series sentiment analysis task. The [CCC](https://en.wikipedia.org/wiki/Concordance_correlation_coefficient) score is used to evaluate performance of the model. Future models developed for solving the SEND task, please open an issue and we will update this table.

| Model           | A | T | V | AT | TV | AV | ATV | Paper / Source |  Code |
| ------------- | :-----:| :-----:| --- | --- | --- | --- | --- | --- | --- |
| LSTM | 0.10 | 0.38 | 0.12 | 0.08 | 0.28 | 0.10 | 0.14 | [Modeling emotion in complex stories: the Stanford Emotional Narratives Dataset](https://arxiv.org/pdf/1912.05008.pdf) | [Official](https://github.com/desmond-ong/TAC-EA-model) |
| VRNN | 0.11 | 0.43 | 0.11 | 0.32 | 0.24 | 0.14 | 0.17 | [Modeling emotion in complex stories: the Stanford Emotional Narratives Dataset](https://arxiv.org/pdf/1912.05008.pdf) | [Official](https://github.com/desmond-ong/TAC-EA-model) |
| MFT | --- | --- | --- | 0.36 | 0.40 | 0.06 | 0.42 | [Attending to Emotional Narratives](arxiv.org/abs/1907.04197) | [Official](https://github.com/frankaging/ACII2019-transformer) |
| Transformer + LSTM | --- | 0.54 | --- | --- | --- | --- | --- | [Structured Self-Attention Weights Encode Semantics in Sentiment Analysis](https://arxiv.org/abs/2010.04922) | [Official](https://github.com/frankaging/LAT_for_Transformer) |
| Human | --- | --- | --- | --- | --- | --- | 0.50 | --- | --- |

### Why is this the first version of the SEND?

We plan this to be a large, on-going project that will investigate empathy and emotion understanding through emotional narratives (and hopefully in the future, emotional dialogues too). In the short term, we are working on expanding this dataset to include a wider diversity of demographics---different age ranges, different socio-economic backgrounds, and even different cultural / language backgrounds. Our first release contains a good-sized dataset of English-speaking American targets, with a pretty diverse set of emotional narratives. We plan to supplement the SEND with future releases.



## Erratum
June 15, 2021: We noticed an error in the demographic reporting in the paper (just for gender, Table 1). The incorrect and updated values are:

|            | Training | Validation | Test | Total |
| ------------- | --- | --- | --- | --- | 
| \# Targets | 29 | 10 | 10 | 49 |
| \# Female | <strike>18 (62\%)</strike> 16 (55\%) | <strike>6 (60\%)</strike> 5 (50\%) | 6 (60\%) | <strike>30 (61%)</strike> 27 (55%) |




