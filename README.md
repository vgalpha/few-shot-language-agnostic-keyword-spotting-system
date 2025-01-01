# Few Shot Language Agnostic Keyword Spotting System
This proposal was submitted as a part of the [Smart India Hackathon 2024](https://www.sih.gov.in/) which is is a premier nationwide initiative designed to engage students in solving some of the most pressing challenges faced in everyday life.

## Problem Statement
The problem statement requires development of **Few Shot Language Agnostic Key Word Spotting system (FSLAKWS) system**. 
Such a system would be able to localize and classify the presence of keywords of interest in a variable duration audio file even when very few (Few Shot) examples per keyword are given for training. 

The key requirements of the system are mentioned below: - 
* The system should be language agnostic 
* The system should be able to handle audio files at various sample rates (8k-48k). 
* The system should be able to upgrade to additional keywords.

## Our Solution: FEW SHOT TRANSFER LEARNING
We propose to use transfer learning technique to solve this problem. Our solution requires the following steps:

### Dataset Preparation
1. We will utilise open source datasets like [Common Voice](https://commonvoice.mozilla.org/en/datasets), [Google Speech commands](https://huggingface.co/datasets/google/speech_commands) to create a large multilingual dataset of audio files. This is important because the model needs to be language agnostic.  
2. We will perform preprocessing and augmentation on the audio files using techniques like noise injection, shifting to create a robust dataset for training. 

### Embedding Model
1. We will train a large Convolutional Neural Network on the above dataset.
2. The audio files will be fed into the CNN in form of spectrograms.

### Few Shot Training
1. The penultimate layer of the above embedding model will be used as the feature vector.
2. A layer of neurons will be added in front of this feature vector and the model will be trained in a transfer learning setup by freezing the weights of the other layers.
3. The training will involve only few samples per keyword.

## Impact and Benefits
* Language Agnosticism: The model can be extended to various languages without the need for extensive retraining.
* Enhanced Accessibility: This technology can improve accessibility for non-native speakers allowing them to interact with devices using their preferred language
* Support for Emerging Technologies: This technology aligns with the growing trend of AI-driven applications and smart devices. 