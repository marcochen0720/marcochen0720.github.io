---
layout: page
title: NLP-based Interview Content Analysis
description: A computational approach to analyzing psychological interview data using sentiment analysis and topic modeling
img: assets/img/nlp_interview_analysis.jpg
importance: 1
category: research
---
# NLP-based Interview Content Analysis

## Project Overview

This project implements a comprehensive natural language processing (NLP) system to analyze semi-structured interview transcripts from psychological studies. By applying sentiment analysis and topic modeling techniques, the system transforms qualitative interview data into quantifiable insights.

## Research Objectives

- Identify emotional patterns across different participant groups
- Detect common themes that might be missed in manual coding
- Provide quantitative metrics for comparing interview content
- Reduce time required to analyze large volumes of interview data

## Methodology

### Data Collection

- Semi-structured interviews with 10 participants
- Transcription and preprocessing of interview content
- Text segmentation and cleaning

### Sentiment Analysis

The system employs SnowNLP to evaluate emotional intensity throughout the interviews:

```python
def sentiment_analysis(self, text, sentences=None):
    """Using SnowNLP for sentiment analysis"""
    if sentences is None:
        sentences = self.sentence_segmentation(text)

    # Calculate overall sentiment score
    overall_sentiment = SnowNLP(text).sentiments

    # Calculate sentiment score for each sentence, filtering short sentences
    sentence_sentiments = []
    valid_sentences = []

    for sent in sentences:
        sent = sent.strip()
        sent_length = len(sent)

        if sent_length >= self.min_sentence_length:
            try:
                sentiment_score = SnowNLP(sent).sentiments
                sentence_sentiments.append({
                    'sentence': sent,
                    'sentiment_score': sentiment_score,
                    'length': sent_length
                })
                valid_sentences.append(sentiment_score)
            except Exception as e:
                continue

    # Use the average of valid sentences as the overall score
    if valid_sentences:
        overall_sentiment = np.mean(valid_sentences)

    return overall_sentiment, sentence_sentiments
```

### Topic Modeling

The system employs Non-negative Matrix Factorization (NMF) to identify 12 key psychological themes:

1. Love
2. Feelings
3. Self-growth
4. Difficulties
5. Reflection
6. Work
7. Education
8. Daily life
9. Decision-making
10. Goals
11. Companionship and support
12. Family

```python
def extract_topics(self, texts):
    """Topic extraction"""
    # Text preprocessing
    processed_texts = [self.preprocess_text(text) for text in texts]

    # TF-IDF transformation
    tfidf_matrix = self.vectorizer.fit_transform(processed_texts)

    # NMF topic modeling
    topic_matrix = self.nmf_model.fit_transform(tfidf_matrix)

    # Get feature names
    feature_names = self.vectorizer.get_feature_names_out()

    # Extract topic words and sort by weight
    topic_words = []
    for topic_idx, topic in enumerate(self.nmf_model.components_):
        # Get top 15 most important words
        top_words_idx = topic.argsort()[:-15:-1]
        top_words = [(feature_names[i], topic[i]) for i in top_words_idx]

        # Filter low-weight words
        significant_words = [(word, weight) for word, weight in top_words if weight > 0.01]

        # Add to topic words list
        topic_words.append(significant_words)

    return topic_matrix, topic_words
```

## Key Findings

### Sentiment Distribution

Analysis of sentiment scores across interviews revealed:

- Average sentiment intensity: 0.73
- Range of sentiment scores: 0.42 to 0.89
- Positive sentiment dominance in family-related discussions
- Lower sentiment scores when discussing work challenges

### Topic Distribution

Topic modeling identified prominent themes across interviews:

- Family and relationships (21%)
- Work and career development (18%)
- Self-reflection and personal growth (16%)
- Challenges and problem-solving (14%)
- Educational experiences (11%)
- Other topics (20%)

## Visualizations

The system generates multiple visualization types:

- **Sentiment distribution histograms** showing emotional intensity across interviews
- **Topic distribution pie charts** for each participant
- **Word frequency bar charts** highlighting key terms
- **Topic keyword clouds** visualizing important terms by topic
- **Sentiment trend analysis** tracking emotional patterns

## Conclusions & Future Work

This computational approach to interview analysis demonstrates the value of applying NLP techniques to psychological research data. The system successfully identified emotional patterns and thematic content that provide valuable insights for researchers.

Future development will focus on:

- Incorporating more advanced transformer-based models
- Developing interactive visualization dashboards
- Expanding topic models to include more nuanced psychological dimensions
- Adding cross-cultural analysis capabilities

## Publications

This project has contributed to the following research outputs:

- Conference presentation: "Computational Methods for Qualitative Data Analysis" (2023)
- Workshop: "NLP Applications in Psychological Research" (2023)
