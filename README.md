# mt5-lang-detect
Fine-Tuning the Multilingual Text-To-Text Transfer Transformer (MT5) for Predicting The Language Of The Given Text

This self-contained, reproducible Jupyter notebook includes the code and description of how to fine-tune and evaluate small pre-trained MT5-model (gs://t5-data/pretrained_models/mt5/small) on a new task of predicting the language a given text is written in (using the 15 languages from [XNLI](https://www.tensorflow.org/datasets/catalog/xnli) dataset).

Please note, that this notebook heavily relies on the sample [Jupyter notebook](https://github.com/google-research/text-to-text-transfer-transformer/blob/main/notebooks/t5-trivia.ipynb) provided by T5 authors along with several insights and ideas from the [notebook](https://github.com/mayhewsw/multilingual-t5/blob/master/notebooks/mt5-xnli.ipynb) by Stephen Mayhew.

## Modes of running
Basically, I see three modes of using this work. Please note that all three modes are heavily relying on Google Colaboratory, I have not tested it with local runtime.

- Following the whole notebook, loading my finetuned model from Google Storage and checking it on inference. Optionally, checking the correctness of the reported metrics by uncommenting corresponding cells.
- Fine-tuning model by yourself using the Colab runtime to reproduce and verify the whole process. Please note, that the newly created model will be lost after the runtime utilization. For this mode please change LOCAL_RUNTIME_MODEL to True.
- Setting up your personal Google Storage folder and fully replicating my original work.

## Before you start
- It is advised to use Google Chrome if you want to explore Tensorboard interactively during fine-tuning. Also, it looks like that this specific browser works very fast with Colab.
- Please login at any Google Account when the notebook requests it. It is required for the work with Google Storage, which is used as a data directory for faster loading.
- Google Colab is sometimes failing to provide enough TPUs. I can do nothing with it, since the base T5 model heavily relies on TPU architecture. The only advice is to try again later.
