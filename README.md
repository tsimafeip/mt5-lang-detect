# mt5-lang-detect
Fine-Tuning the Multilingual Text-To-Text Transfer Transformer (MT5) for Predicting The Language Of The Given Text

This self-contained, reproducible Jupyter notebook includes the code and description of how to fine-tune and evaluate small pre-trained MT5-model (gs://t5-data/pretrained_models/mt5/small) on a new task of predicting the language a given text is written in (using the 15 languages from [XNLI](https://www.tensorflow.org/datasets/catalog/xnli) dataset).

Please note, that this notebook uses code from the sample [Jupyter notebook](https://github.com/google-research/text-to-text-transfer-transformer/blob/main/notebooks/t5-trivia.ipynb) provided by T5 authors along with several insights and ideas from the [notebook](https://github.com/mayhewsw/multilingual-t5/blob/master/notebooks/mt5-xnli.ipynb) by Stephen Mayhew.

## Modes of running
I see two modes of using this work. All modes are heavily relying on Google Colaboratory means.

- Following the whole notebook, loading the model from Google Storage, which was finetuned by me, and checking it at inference.
Optionally, checking the validity of the result metrics.
- Setting up your personal Google Storage folder and changing BASE_CLOUD_DIR respectively.

Additionally, I have tried to use local Colab runtime to save the model-related files, but it is not allowed due to [TPU-specifics](https://cloud.google.com/tpu/docs/troubleshooting#cannot_use_local_filesystem).

## Before you start
- It is advised to use Google Chrome if you want to explore Tensorboard interactively during fine-tuning. Also, it looks like this specific browser works very fast with Colab.
- Please log in to any Google Account when the notebook requests it. It is needed for the work with Google Storage, which assists as a data directory for faster loading.
- Google Colab is sometimes failing to provide enough TPUs. I can do nothing with it since the T5 model is based on TPU architecture. The only advice is to try again later.
