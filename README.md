# Fine-tuning-MarianMT-for-English-Vietnamese-Translation
This project uses and fine-tunes MarianMT transformer for English to Vietnamese translation task
Through Huggingface, I use "Helsinki-NLP/opus-mt-en-vi" model of MarianMT for machine translation task from English to Vietnamese.
# Dataset
I use the IWSLT'15 English-Vietnamese data from [Stanford NLP] group and load it via Huggingface's "datasets" library.

| Dataset   | Sentences |
| --------- | --------- |
|Training   | 133318    |
|Development| 1269      |
|Test       | 1269      |
# Results
* BLEU Score: 33.90
* Parameters while training:
  * Epoch: 1
  * Number of examples: 800
  * Batch size: 16

Note: 800 examples were used mainly due to limited computational resources.

Aside from the fine-tuning, to compare the pre-trained and fine-tuned model directly, I use a paragraph of a single English text about the definition of Natural Language Processing from IBM's website (https://www.ibm.com/cloud/learn/natural-language-processing). To understand their performances, I back-translate the outputs of both of the models to English.

* The Full Text: "Natural language processing (NLP) refers to the branch of computer science—and more specifically, the branch of artificial intelligence or AI—concerned with giving computers the ability to understand text and spoken words in much the same way human beings can."

# Comparison of the models

# Pre-trained: 
* Vietnamese text: "Natural Language (NLP) đề cập đến ngành khoa học máy tính và cụ thể hơn là ngành trí tuệ nhân tạo hoặc phụ thuộc vào việc cung cấp cho máy tính khả năng hiểu văn bản và ngôn ngữ nói trên đường đi. một cách mà mọi người có thể"

* Back translation to English: "Natural Language (NLP) refers to the branch of computer science and more specifically, the branch of artificial intelligence or depends on providing computers with the ability to understand text and spoken language along the way. a way that people can"

# Fine-tuned:
* Vietnamese text: "Xử lý ngôn ngữ tự nhiên (NLP) muốn nói đến chi nhánh của khoa học máy tính và cụ thể hơn nữa, chi nhánh của trí tuệ nhân tạo hoặc AI đối xứng với việc cung cấp cho máy tính khả năng hiểu văn bản và ngôn ngữ nói theo cùng một cách mà con người có thể."

* Back-translation: "Natural Language Processing (NLP) refers to the branch of computer science and more specifically, the branch of artificial intelligence or symmetric AI that provides computers with the ability to understand text and language. language spoken in the same way that humans can."
