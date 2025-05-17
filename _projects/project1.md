---
layout: page
title: Psychological Resilience and Work-Family Conflict Analysis
description: NLP-based analysis of psychological resilience and work-family conflict among stay-at-home mothers through semi-structured interviews
img: assets/img/psychological_resilience_analysis.jpg
importance: 1
category: research
---

<style>
/* 项目详情页面样式 */
.project-detail-container {
  max-width: 1000px;
  margin: 0 auto;
  padding: 20px;
  line-height: 1.6;
}

.project-detail-container h1 {
  font-size: 32px;
  margin-bottom: 20px;
  color: #333;
}

.project-detail-container h2 {
  font-size: 24px;
  margin-top: 40px;
  margin-bottom: 15px;
  padding-bottom: 8px;
  border-bottom: 1px solid #eee;
  color: #444;
}

.project-detail-container p {
  margin-bottom: 15px;
  font-size: 16px;
}

.project-detail-container ul {
  margin-bottom: 20px;
  padding-left: 20px;
}

.project-detail-container li {
  margin-bottom: 8px;
}

.project-detail-container code {
  background-color: #f5f5f5;
  padding: 2px 5px;
  border-radius: 3px;
  font-family: Consolas, Monaco, 'Andale Mono', monospace;
  font-size: 14px;
}

.project-detail-container pre {
  background-color: #f5f5f5;
  padding: 15px;
  border-radius: 5px;
  overflow: auto;
  margin-bottom: 20px;
}

/* 代码高亮 */
.highlight {
  position: relative;
  margin-bottom: 20px;
  border-radius: 5px;
  overflow: hidden;
}

.highlight pre {
  padding: 15px;
  overflow: auto;
  font-family: Consolas, Monaco, 'Andale Mono', monospace;
  font-size: 14px;
  line-height: 1.5;
}

/* 可选：添加一些响应式设计 */
@media (max-width: 768px) {
  .project-detail-container {
    padding: 15px;
  }
  
  .project-detail-container h1 {
    font-size: 28px;
  }
  
  .project-detail-container h2 {
    font-size: 22px;
  }
}
</style>

<div class="project-detail-container">

# Psychological Resilience and Work-Family Conflict Analysis

## Project Overview
This research explores the psychological resilience of stay-at-home mothers facing work-family conflict using natural language processing (NLP) techniques. Through analyzing semi-structured interviews with 12 stay-at-home mothers, we examined how emotional resilience, behavioral resilience, and social support moderate work-family conflict, providing quantifiable insights into complex psychological phenomena.

## Research Background
Stay-at-home mothers represent a significant social group that often faces profound role conflicts between their educational responsibilities for children and personal career development. In China's cultural context, where education is highly valued, these mothers experience unique psychological adaptation challenges as they navigate between family responsibilities and personal development.

## Research Objectives
* Investigate how different dimensions of psychological resilience (emotional and behavioral) regulate psychological health in work-family conflict situations
* Explore the mechanisms through which emotional and behavioral resilience interact in the regulation process
* Examine how stay-at-home mothers utilize external support resources to enhance psychological resilience
* Apply NLP technology to analyze interview data for deeper understanding of psychological states and adaptation mechanisms

## Theoretical Framework
The research integrates social cognitive theory with psychological resilience models, utilizing text data analysis methods and NLP technology to mine emotional expressions, cognitive patterns, and social support characteristics from interview texts.

## Methodology

### Data Collection
* **Sample Selection**: 12 stay-at-home mothers with children in compulsory education, with at least one year of stay-at-home experience
* **Measurement**: Bi-directional Scale of Work-Family Conflict (BSWFC) for conflict level assessment
* **Interview Protocol**: 60-90 minute semi-structured interviews focusing on role conflict, emotional and behavioral responses, social support, and resilience construction

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
