# Building-for-Tomorrow


Performance of text classification models can drop over time when new data to be classified is more distant in time from the data used for training, due to naturally occurring changes in the data, such as vocabulary change. A solution to this is to continually label new data to retrain the model, which is, however, often unaffordable to be performed regularly due to its associated cost. This raises important research questions on the design of text classification models that are intended to persist over time: do all embedding models and classification algorithms exhibit similar performance drops over time and is the performance drop more prominent in some tasks or datasets than others? With the aim of answering these research questions, we perform longitudinal classification experiments on three datasets spanning between 6 and 19 years. Findings from these experiments inform the design of text classification models with the aim of preserving performance over time, discussing the extent to which one can rely on classification models trained from temporally distant training data, as well as how the characteristics of the dataset impact this.

![image](https://user-images.githubusercontent.com/83759421/168052272-735a9daa-2255-49c3-a70a-73002793b79a.png)

We shed light into the temporal robustness of existing language models.
We investigate the impact of classification model choice in cross-temporal performance.
We analyse when and why model performance drops over time, which informs when a model needs adapting.
We look at properties of the datasets to understand what impacts performance drop.
We assess the potential and limitations of contextual language models to develop temporal robustness.


![image](https://user-images.githubusercontent.com/83759421/168053210-97ed26c2-5bb7-488b-819d-26afd19f0224.png)


This paper is complementary to a survery paper:

Alkhalifa, Rabab, and Arkaitz Zubiaga. **"Capturing stance dynamics in social media: open challenges and research directions."** International Journal of Digital Humanities (2022): 1-21.

and pilot study: 

Rabab Alkhalifa, Elena Kochkina, and Arkaitz Zubiaga. 2021. **Opinions are Made to be Changed: Temporally Adaptive Stance Classification**. In Proceedings of the 2021 Workshop on Open Challenges in Online Social Networks (OASIS '21). Association for Computing Machinery, New York, NY, USA, 27–32. https://doi.org/10.1145/3472720.3483620, https://github.com/OpinionChange2021/opinion_are_made_to_be_changed

Part of PhD work by _Rabab Alkhalifa_, raalkhalifa@iau.edu.sa/ r.a.a.alkhalifa@qmul.ac.uk and supervised by _Arkaitz Zubiaga_, https://www.zubiaga.org/

