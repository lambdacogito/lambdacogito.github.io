---
layout: post
title: "LLM formats"
date: 2023-09-22
author: "Jamin Chen"
header-img: "img/post-bg-universe.jpg"
tags: ["AGI", "LLM"]
---

Language models can be saved and loaded in various formats, here are the most known frameworks:

* **PyTorch Model**: This is a common format for models trained using the PyTorch framework. It represents the state_dict (or the "state dictionary"), which is a Python dictionary object that maps each layer in the model to its trainable parameters (weights and biases).

* **TensorFlow Checkpoints**: TensorFlow is another popular framework for training machine learning models. A checkpoint file contains the weights of a trained model. Unlike a full model, it doesn't contain any description of the computation that the model performs, it's just the weights. That's useful because often the models can be large and storing the full model in memory can be expensive.

* **Hugging Face Transformers**: Hugging Face is a company known for their Transformers library, which provides state-of-the-art general-purpose architectures. They have their own model saving and loading mechanisms, usually leveraging PyTorch or TensorFlow under the hood. You can save a model using the save_pretrained() method and load it using from_pretrained().

Here is a brief overview of the different language model file formats:

* **GGML** stands for Google's Transformer-XL model format. It is a text-based format that stores the model's parameters in a human-readable format. GGML is a good choice for debugging and understanding how the model works.

* **HF** stands for Hugging Face's Transformers format. It is a binary format that stores the model's parameters in a compressed format. HF is a good choice for production deployment, as it is more efficient than GGML.

* **Checkpoints (.ckpt)** are saved states of a language model's training process. They can be used to resume training, or to load a model that has already been trained. Checkpoints can be useful for debugging, or for saving a model's progress so that it can be resumed later.

* **ONNX** is a cross-platform format for machine learning models. It can be used to store and share language models between different frameworks.

* **Safetensor** is a new format for storing tensors safely. It is designed to be more secure than traditional formats, such as pickle, which can be used to execute arbitrary code. Safetensor is also faster than pickle, making it a good choice for production deployment. Pytorch .pb is a binary format for storing neural networks. It is efficient and can be loaded quickly.

* **Pytorch (.pt)** is the most common extension for PyTorch language models. It is a binary file that stores the model's parameters and state. Pytorch .pth is another common extension for PyTorch language models. It is a text-based file that stores the model's parameters and state.

* **.bin** file is a binary file that stores the parameters and state of a language model. It is a more efficient way to store a language model than a text-based file, such as a .pth file. This is because a binary file can be compressed, which makes it smaller and faster to load.
