# Building for Tomorrow: Assessing the Temporal Persistence of Text Classifiers


Performance of text classification models can drop over time when new data to be classified is more distant in time from the data used for training, due to naturally occurring changes in the data, such as vocabulary change. A solution to this is to continually label new data to retrain the model, which is, however, often unaffordable to be performed regularly due to its associated cost. This raises important research questions on the design of text classification models that are intended to persist over time: do all embedding models and classification algorithms exhibit similar performance drops over time and is the performance drop more prominent in some tasks or datasets than others? With the aim of answering these research questions, we perform longitudinal classification experiments on three datasets spanning between 6 and 19 years. Findings from these experiments inform the design of text classification models with the aim of preserving performance over time, discussing the extent to which one can rely on classification models trained from temporally distant training data, as well as how the characteristics of the dataset impact this.

![image](https://user-images.githubusercontent.com/83759421/168052272-735a9daa-2255-49c3-a70a-73002793b79a.png)

![image](https://user-images.githubusercontent.com/83759421/168621656-36eade23-cfdb-4f29-b641-9165a334776d.png)


- We shed light into the temporal robustness of existing language models.
- We investigate the impact of classification model choice in cross-temporal performance.
- We analyse when and why model performance drops over time, which informs when a model needs adapting.
- We look at properties of the datasets to understand what impacts performance drop.
- We assess the potential and limitations of contextual language models to develop temporal robustness.

Preprint: https://arxiv.org/abs/2205.05435

**RQ1.** How does the choice of a language model impact classification performance over time across different datasets?

![image](https://user-images.githubusercontent.com/83759421/168621500-40dcd70d-6c9e-4280-8d33-de5d2c1c215f.png)

**RQ2.** How does the choice of an algorithmic architecture impact classification performance over time across different datasets?

![image](https://user-images.githubusercontent.com/83759421/168621385-66ad7ff6-6811-4460-8d41-68408b43700e.png)


**RQ3.** How does prediction performance vary across longitudinal datasets?

![image](https://user-images.githubusercontent.com/83759421/168621284-5260d07d-71c0-47fa-93be-28e7fbf3a596.png)


**RQ4.**  What are the linguistic features that can impact the temporal performance?

![image](https://user-images.githubusercontent.com/83759421/168621173-e3a4d5d7-4626-4ec9-8cf6-ccb457e7e5c6.png)

 
**RQ5.** How well do the contextual characteristics of context-based models generalise to evolving context over time?

![image](https://user-images.githubusercontent.com/83759421/168620894-4b8074c5-aad0-4b7c-8399-2ece6ee62b64.png)

![image](https://user-images.githubusercontent.com/83759421/168620969-24d573a4-6f25-4f2b-90d2-8311f5a30acb.png)




This paper is complementary to a survery paper:

Alkhalifa, Rabab, and Arkaitz Zubiaga. **"Capturing stance dynamics in social media: open challenges and research directions."** International Journal of Digital Humanities (2022): 1-21.

and pilot study proposed in workshop paper: 

Rabab Alkhalifa, Elena Kochkina, and Arkaitz Zubiaga. 2021. **Opinions are Made to be Changed: Temporally Adaptive Stance Classification**. In Proceedings of the 2021 Workshop on Open Challenges in Online Social Networks (OASIS '21). Association for Computing Machinery, New York, NY, USA, 27–32. https://doi.org/10.1145/3472720.3483620, https://github.com/OpinionChange2021/opinion_are_made_to_be_changed

Part of PhD work by _Rabab Alkhalifa_, raalkhalifa@iau.edu.sa/ r.a.a.alkhalifa@qmul.ac.uk and supervised by _Arkaitz Zubiaga_, https://www.zubiaga.org/

