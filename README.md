# Machine Translation with Transformers

Study project. My implementation of the algorithm described in _Attention Is All You Need_ and my first practical experience with transformers.

The whole project was completed on a single entry-level GPU so I only tried a limited number of options. This version does not use weight tying because source and target vocabulary sizes are different. No label smoothing in this version too.

The model was trained and tested on a dataset from the Tatoeba Project (just under 500,000 translation pairs). Most samples were single sentences but a few were longer with a total length of more than 100 words. I split some of the longer text sequences into individual sentences to keep sequence lengths below 50 words. All words were lower-cased. I have not used more advanced tokenizers in this version, so tokens are individual words.

Results obtained with various hyperparameters are summarized in results_metrics.xlsx. One obvious finding is that a single-block transfomer performed much worse than 3-layer LSTMs I had tried before (hLEPOR ~ 0.65 with beam search), to say nothing of more complex transformers.