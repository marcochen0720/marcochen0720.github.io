---
layout: projects
title: Psychological Resilience and Work-Family Conflict Analysis
description: NLP-based analysis of psychological resilience and work-family conflict among stay-at-home mothers through semi-structured interviews
img: images/psych_nlp.png
importance: 1
category: research
---

# Psychological Resilience and Work-Family Conflict Analysis

## Project Overview

This research explores the psychological resilience of stay-at-home mothers facing work-family conflict using natural language processing (NLP) techniques. Through analyzing semi-structured interviews with 12 stay-at-home mothers, we examined how emotional resilience, behavioral resilience, and social support moderate work-family conflict, providing quantifiable insights into complex psychological phenomena.

## Research Background

Stay-at-home mothers represent a significant social group that often faces profound role conflicts between their educational responsibilities for children and personal career development. In China's cultural context, where education is highly valued, these mothers experience unique psychological adaptation challenges as they navigate between family responsibilities and personal development.

## Research Objectives

- Investigate how different dimensions of psychological resilience (emotional and behavioral) regulate psychological health in work-family conflict situations
- Explore the mechanisms through which emotional and behavioral resilience interact in the regulation process
- Examine how stay-at-home mothers utilize external support resources to enhance psychological resilience
- Apply NLP technology to analyze interview data for deeper understanding of psychological states and adaptation mechanisms

## Theoretical Framework

The research integrates social cognitive theory with psychological resilience models, utilizing text data analysis methods and NLP technology to mine emotional expressions, cognitive patterns, and social support characteristics from interview texts.

## Methodology

### Data Collection

- **Sample Selection**: 12 stay-at-home mothers with children in compulsory education, with at least one year of stay-at-home experience
- **Measurement**: Bi-directional Scale of Work-Family Conflict (BSWFC) for conflict level assessment
- **Interview Protocol**: 60-90 minute semi-structured interviews focusing on role conflict, emotional and behavioral responses, social support, and resilience construction

### NLP-Based Analysis Framework

A four-stage data analysis process was implemented:

```python
# Stage 1: Data Preprocessing
def data_preprocessing(text_data):
    """Process interview text data through manual review, sentence segmentation, and word tagging"""
    cleaned_data = manual_review(text_data)  # Remove irrelevant content and ensure reliability
    sentences = sentence_segmentation(cleaned_data)  # Split text into grammatically coherent sentences
    tagged_data = pos_tagging(sentences)  # Identify grammatical units (nouns, verbs, etc.)
    return tokenize_and_filter(tagged_data)  # Break sentences into semantic units and remove stopwords

# Stage 2: Sentiment Analysis
def emotional_fluctuation_analysis(preprocessed_data):
    """Quantitatively assess emotional tendencies in the interview data"""
    # Using VADER for sentiment scoring with Chinese optimization via BosonNLP
    vader_analyzer = SentimentIntensityAnalyzer()
    sentiment_scores = []
  
    for text_segment in preprocessed_data:
        scores = vader_analyzer.polarity_scores(text_segment)
        # Combine with BosonNLP for Chinese text optimization
        boson_score = boson_sentiment(text_segment)
        combined_score = optimize_score(scores, boson_score)
        sentiment_scores.append(combined_score)
  
    # Track emotional changes throughout the interview
    emotional_patterns = track_emotion_patterns(sentiment_scores)
    return sentiment_scores, emotional_patterns

# Stage 3: Topic Modeling
def extract_topics(preprocessed_data):
    """Extract latent topics from interview text using NMF"""
    # TF-IDF vectorization
    vectorizer = TfidfVectorizer(
        max_features=1000,
        token_pattern=r"(?u)\b\w+\b",
        stop_words=list(get_stopwords()),
        min_df=2,
        max_df=0.95
    )
  
    # Create TF-IDF matrix
    tfidf_matrix = vectorizer.fit_transform(preprocessed_data)
  
    # Apply NMF for topic extraction
    nmf_model = NMF(
        n_components=12,  # 12 predefined topics based on research framework
        random_state=42,
        max_iter=500
    )
  
    topic_matrix = nmf_model.fit_transform(tfidf_matrix)
    feature_names = vectorizer.get_feature_names_out()
  
    # Extract topic words with weights
    topic_words = []
    for topic_idx, topic in enumerate(nmf_model.components_):
        top_words_idx = topic.argsort()[:-15:-1]
        top_words = [(feature_names[i], topic[i]) for i in top_words_idx]
        topic_words.append(top_words)
  
    return topic_matrix, topic_words

# Stage 4: Psychological Resilience Conceptualization
def map_resilience_indicators(topic_matrix, topic_words):
    """Map extracted topics to psychological resilience dimensions"""
    # Map topics to emotional resilience, behavioral resilience, and social support dimensions
    resilience_map = {
        'emotional_resilience': ['love', 'feelings', 'difficulties', 'reflection'],
        'behavioral_resilience': ['daily life', 'self-growth', 'work', 'goals', 'decision-making'],
        'external_support': ['companionship and support', 'family', 'education']
    }
  
    # Calculate prevalence of resilience dimensions across interviews
    resilience_prevalence = calculate_prevalence(topic_matrix, resilience_map)
    return resilience_prevalence
```

### Semantic Embedding

We used the paraphrase-multilingual-MiniLM-L12-v2 model to generate semantic vector representations of interview texts, enabling us to capture implicit semantic relationships and deeper psychological patterns beyond explicit keywords.

## Key Findings

### Emotional Patterns

Sentiment analysis revealed four typical emotional patterns among stay-at-home mothers:

1. **High Baseline-Low Fluctuation**: Some participants (e.g., Participants 2 and 6) maintained high average emotional intensity (>0.85) with minimal fluctuation, reflecting stable emotional regulation abilities.
2. **Generally Positive with Local Valleys**: Most participants showed generally positive emotional states with occasional downturns during specific interview segments, suggesting emotional resilience with contextual sensitivity.
3. **Periodic Fluctuation**: Some participants (e.g., Participants 3 and 8) displayed periodic emotional fluctuations, potentially reflecting emotional compartmentalization strategies.
4. **Peak-Valley Alternation**: Individual participants (e.g., Participant 4) showed frequent alternation between emotional highs and lows, demonstrating high emotional sensitivity but also rapid recovery capabilities.

### Topic Distribution Analysis

Our NMF topic modeling identified 12 key topics that fell into three major categories:

1. **Emotional Dimension**: Topics related to "love" and "feelings" distributed primarily in the first quadrant of semantic space, highly correlated with "positive emotions" (r=0.72, p<0.01) and "social processes" (r=0.68, p<0.01).
2. **Cognitive-Behavioral Dimension**: Topics like "reflection" and "decision-making" clustered in the third quadrant, significantly correlated with "cognitive mechanisms" (r=0.65, p<0.01) and "work" (r=0.59, p<0.01).
3. **Social Support Dimension**: Topics related to "family" and "companionship and support" showed cross-quadrant distribution, indicating their bridging function across psychological processes. The "education" topic showed highest semantic similarity with "self-efficacy" (cos=0.83) and "social capital" (cos=0.79).

### Psychological Resilience Mechanisms

Our analysis identified significant differences in how emotional resilience and behavioral resilience moderate work-family conflict:

1. **Emotional Resilience**: Functions primarily through emotional regulation and recovery processes, helping individuals accept negative emotions from conflicts and reduce psychological burden.
2. **Behavioral Resilience**: Operates through task management and self-efficacy construction, helping individuals actively address external challenges through practical strategies.
3. **Family and Social Support**: Significantly enhances individual psychological resilience, providing both emotional buffering and practical assistance during role conflicts.

## Research Implications

### Theoretical Contributions

- Expanded work-family conflict theory to include stay-at-home mothers as a specific and growing demographic
- Enriched psychological resilience theory with detailed operational mechanisms in role conflict contexts
- Pioneered the integration of NLP technology in psychological resilience research, providing a novel cross-disciplinary methodological paradigm

### Practical Value

- Informed psychological intervention designs targeting stay-at-home mothers' emotional regulation and behavioral adaptation
- Provided evidence-based guidance for family education policies and social support systems
- Created a methodological bridge between qualitative interview approaches and quantitative data analysis in psychological research

## Future Development

Ongoing and future developments of this research include:

- Expanding the sample size and demographic diversity to enhance generalizability
- Integrating physiological data for multi-modal analysis of psychological resilience
- Developing targeted intervention programs based on identified resilience mechanisms
- Conducting cross-cultural comparative studies to understand cultural influences on psychological adaptation

## Publications & Presentations

- Thesis: "Psychological Resilience and Work-Family Conflict of Stay-at-Home Mothers: A Semi-Structured Interview Analysis" (2025)
- Conference presentation: "NLP Applications in Work-Family Conflict Research" (2025)
