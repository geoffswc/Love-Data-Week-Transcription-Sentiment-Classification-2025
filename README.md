# Open-Source Technologies for Transcription & Sentiment Analysis

## Overview

This guide introduces open-source tools for transcription and sentiment analysis, focusing on researchers working on small-scale or personal projects. The tools covered—Whisper for transcription and Hugging Face Transformers for sentiment analysis and text classification—can be run locally or on platforms like Google Colab. These tools provide cost control, flexibility, and the ability to experiment without the risk of unintended charges commonly associated with cloud APIs.

## Benefits

### 1. Cost Control
   - **Preventing Unintended Costs**: Running models locally or on platforms like Google Colab ensures that researchers avoid the risks of unexpected charges. With cloud APIs, a bug in code could unintentionally lead to processing a large number of requests, potentially incurring high costs. By using open-source tools on Colab or locally, this risk is eliminated.
   - **Colab's Resource Management**: On Google Colab, there are no surprise charges—if usage exceeds the free tier limits, Google simply limits access for a period. Researchers do not incur unexpected costs. This provides an extra layer of protection compared to other cloud-based services that may result in high charges if not carefully managed. If additional resources are needed, Colab offers paid tiers for more power, but even then, charges are subscription based, predictable and fixed.
   - **Control Over Usage**: By using local models or Colab, researchers don't need to worry about relying on their institution's payment methods, which may not have the flexibility needed for high, unexpected costs. This setup offers greater control over usage and limits financial risk.

### 2. Flexibility
   - **Customization**: Open-source models provide full control over configurations, enabling researchers to fine-tune models and adapt them to the needs of their specific projects. This is especially important for researchers who want to experiment or modify existing models without restrictions.
   - **Unrestricted Experimentation**: Open-source tools eliminate the concerns of hitting API limits or dealing with pay-per-use models. Researchers are free to try different approaches, settings, and models without the fear of accumulating unexpected costs from bugs or overuse.

### 3. Ideal for Small Projects
   - **Low-Cost, Low-Scale Solutions**: Open-source tools are perfect for small datasets, personal projects, or prototype development. Researchers can focus on their experiments without the need for large cloud infrastructures, which can be both costly and time-consuming to manage.
   - **Quick Prototyping**: With these tools, researchers can quickly prototype ideas without the overhead of dealing with cloud services or managing API complexities.

## Drawbacks

### 1. Limited Resources
   - **GPU and Hardware Constraints**: Free resources like Google Colab’s GPU access are limited, and personal hardware may not be powerful enough to handle large datasets or long-running tasks efficiently. This can slow down processing, especially for complex models or large audio files.
   - **Scaling Challenges**: While open-source tools work well for small tasks, scaling up to large projects may require more powerful resources, which may not always be accessible.
   - **Limited Parallel Processings**: When you leverage cloud based APIs, 10,000 hours of video footage can be processed in 1 hour on 10,000 servers with 10,000 separate API calls. Locally, you may have to process these in series. So even if total compute time is the same, parallel processing can get your data processing done far more quickly.
   - **This might not matter so much....**: If you're a researcher and you just want to experiment and learn, this won't be an issue. Also, keep in mind that "scaling challenges" might not apply to a real world research data set. A few thousand hours of video footage might not be too big if you are using GPUs in Colab or a local environment, and you're willing to wait a day or two for your results. 

### 2. No 24/7 Support
   - **Community Support**: Open-source tools often come with community-driven support rather than official customer service. While active communities exist, issues may take longer to resolve without direct technical support, unlike cloud services such as AWS or Google Cloud that offer around-the-clock assistance.
   - **This might not matter so much...**: IT often talks about support levels (I remember Gold, Silver, Bronze at Berkeley), indicating committments to uptime and availability, speed and timing of response from an IT team, and production support. If your goal is a one-time data processing task for a research project, this may not have any real impact on your project. 

## Technologies Used in this Workshop

### 1. Whisper: Transcription Model
   - **Overview**: Whisper is an open-source automatic speech recognition (ASR) system developed by OpenAI. It supports a range of languages and can transcribe audio or video files into text. Available in multiple model sizes, Whisper balances between speed and accuracy.
   - **Training Data**: Whisper was trained on over 680,000 hours of multilingual data, including diverse audio sources such as clear, noisy, and accented speech. This large-scale, multitask dataset enables it to handle various transcription challenges.
   - **Source**: [Whisper: Robust Speech Recognition via Large-Scale Weak Supervision (OpenAI)](https://openai.com/research/whisper)
   - **How It Works**: Whisper processes audio or video files and outputs text transcription, with model size affecting accuracy and speed.

### 2. Hugging Face Transformers: Sentiment Analysis and Classification
   - **Overview**: Hugging Face’s Transformers library includes pre-trained models for sentiment analysis and text classification. Notable models include:
     - **DistilBERT** for sentiment analysis.
     - **BART** for zero-shot classification.
   - **Training Data**:
     - **DistilBERT** was pre-trained on the **BooksCorpus** and **English Wikipedia**. It was then fine-tuned on the **SST-2** dataset (Stanford Sentiment Treebank), which contains movie reviews labeled as positive or negative. This fine-tuning allows it to perform sentiment classification tasks.
     - **BART** was trained on the **MultiNLI** dataset, which is designed for text classification tasks.
   - **Sources**:
     - [DistilBERT: A distilled version of BERT (Hugging Face)](https://huggingface.co/distilbert-base-uncased)
     - [BookCorpus Dataset](https://huggingface.co/datasets/bookcorpus)
     - [BART: Denoising Sequence-to-Sequence Pre-training for Natural Language Generation, Translation, and Comprehension (Hugging Face)](https://huggingface.co/facebook/bart-large)
   - **How It Works**: These models process text input and classify it based on their training data. For example, **DistilBERT** categorizes sentiment as positive, neutral, or negative, while **BART** can classify text into categories without needing prior training on specific labels.


## Practical Considerations for Using General Models on Specialized Data

### 1. Limitations of General-Purpose Models
   - **Broad Datasets**: Models like DistilBERT and BART are trained on broad, general datasets, which may not always be suited to specialized domains (e.g., medical, legal). As a result, performance may be suboptimal on specialized data.
   - **Domain-Specific Terminology**: These models may struggle with domain-specific jargon or context, leading to less accurate results when used on specialized text.

### 2. Challenges with Specialized Models
   - **Data Scarcity**: Specialized models require large, labeled datasets, which can be difficult and costly to collect.
   - **High Costs**: Training specialized models from scratch is resource-intensive. Fine-tuning pre-trained models with smaller datasets is often a more practical and cost-effective solution.

### 3. Why General Models May Still Be the Best Option
   - **Practicality**: For many tasks, specialized models are not feasible due to data limitations. General models like DistilBERT or BART, despite their limitations, are often more practical and cost-effective for tasks that don’t require deep domain expertise.
   - **Fine-Tuning**: Fine-tuning general-purpose models on smaller, domain-specific datasets is a practical approach for researchers who need specialized performance but lack the resources to train models from scratch.

## Conclusion

Using open-source technologies like Whisper and Hugging Face Transformers offers a flexible, low-cost approach for transcription and sentiment analysis, particularly for researchers working on small-scale projects. While there are some limitations, especially with specialized data, these tools provide significant advantages, including cost control, flexibility, and ease of use. Fine-tuning general models for specific tasks can be an efficient way to handle specialized data, especially when resources for training new models are unavailable.

## Coding Workshop

For the hands-on section of this workshop:
1. Use Python to download video files from the Industry Archives (or any public mp4 link)
2. Use Whisper for transcription in Python.
3. Classify documents and assess sentiment analysis using Hugging Face Transformers.


