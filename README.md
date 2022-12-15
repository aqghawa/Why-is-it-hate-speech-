# Why-is-it-hate-speech-
## Introduction
The increase in popularity of social media was also followed by an increase in hate speech. The pervasiveness of hate speech can increase prejudice and discrimination against the targeted social groups. While there are models that perform hate speech detection very well, they have a tendency to be biased and not very explainable. This makes it difficult to understand why a model labels a non-hateful piece of text as hateful. This may also lead to models that are biased towards certain groups. These models have the tendency to be biased towards specific words (e.g., 'nigger') \cite{DelVigna:2017}; however, the presence of certain words don't necessarily indicate that the text is hateful. This mistaken judgement may strengthen the discrimination against the target group of such a word \cite{LanguageUnderstanding}. To this end, the model's bias towards specific words/expressions should be eliminated.

## Methodology
Firstly, we tokenize each word in the text, and similarly, we ensure that each token corresponds to one rationale. Next, we embed the text and embed the rationale in a similar manner, ensuring that we set [PAD] tokens to 0 in the rationale embeddings to avoid duplication of embedding. Next, we mask random token rationales. Finally, we construct an BERT-MRP model, by adding an MLP layer on top of bert. We train the model with BCE loss only on the masked tokens.

![Methodology Diagram](Methods.jpg)
