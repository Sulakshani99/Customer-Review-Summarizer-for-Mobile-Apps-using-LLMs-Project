
# Customer Review Summarizer for Mobile Apps using LLMs

This project leverages Large Language Models (LLMs), specifically a fine-tuned T5 model, to automatically summarize user reviews from Google Play Store apps. It is designed for efficient sentiment-aware summarization, helping developers and analysts quickly understand user feedback at scale.

## Features
- Summarizes thousands of app reviews into concise, sentiment-based summaries (Positive, Negative, Neutral)
- Uses a fine-tuned T5 model for high-quality abstractive summarization
- Supports custom review summarization and synthetic review generation
- Jupyter notebook for experimentation and demonstration

## Dataset
The dataset used is `googleplaystore_user_reviews.csv`, containing:
- App name
- Translated user review
- Sentiment (Positive, Negative, Neutral)
- Sentiment polarity and subjectivity scores

## Model
- Fine-tuned T5 (Text-to-Text Transfer Transformer) for review summarization
- Model files and tokenizer are in `t5_finetuned_reviews/`

## Project Structure
```
├── Customer-Review-Summarizer-Google-Play-Apps.ipynb  # Main notebook (training, evaluation, usage)
├── data/
│   └── googleplaystore_user_reviews.csv               # Review dataset
├── t5_finetuned_reviews/                             # Fine-tuned model and tokenizer
├── backend/                                          # (empty, for future API/backend)
├── frontend/                                         # (empty, for future UI)
└── README.md
```

## Setup & Installation
1. Clone this repository.
2. Install dependencies (in your Python environment):
	```bash
	pip install -U transformers datasets evaluate accelerate sentencepiece rouge_score
	```
3. Open the notebook `Customer-Review-Summarizer-Google-Play-Apps.ipynb` in Jupyter or VS Code.
4. Run the cells to load the dataset, model, and generate summaries.

## Example Usage
In the notebook, you can summarize reviews for a specific app:
```python
app_name = "10 Best Foods for You"
summaries = summarize_app_by_sentiment(app_name, per_group_limit=50, strip_prefix=True)
print("Positive Summary:\n", summaries.get("Positive", ""))
print("Negative Summary:\n", summaries.get("Negative", ""))
print("Neutral Summary:\n", summaries.get("Neutral", ""))
```

## Authors
- Group 49, Advanced AI Project

## License
For academic use only. Contact authors for other uses.
