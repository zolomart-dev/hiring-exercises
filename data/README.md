# ZOLO Data Engineering/Science Product Exercise

```
TIMEBOX:    7 days
LANGUAGES:  Python
FRAMEWORKS: Jupyter
```

## Overview

In this exercise, you will research and implement a subset of ZOLO's matching problem. The purpose is to assess your ability to analyze data, develop a solution, and present clear, actionable results. This exercise is not a test of your Jupyter, Python, or SQL skills per se, but rather an opportunity to demonstrate your problem-solving approach, research capabilities, and technical presentation.

## Problem Description

ZOLO's core functionality involves matching unstructured user text to a specific subset of catalog products (referred to as the "product guide") for each customer. In the provided datasets:

- `input` Column: Contains unstructured text from user orders (e.g., messages sent via WhatsApp).
- `product_guide` Column: Contains a comma-separated list of products available in the order guide for that customer.
- `match` Column: Represents the correct product from the `product_guide` that corresponds to the user's input.

Your goal is to build a matching system that achieves the highest possible accuracy in predicting the correct product (the `match`) based on the given unstructured `input` and the list of products in `product_guide`.

## Key Areas to Explore

- Data Analysis:
  - Analyze the language used in the `input` versus the `product_guide` columns.
  - Identify differences in terminology, abbreviations, or style.
  - Explore how the number of products in `product_guide` varies across datasets and how these differences might affect matching performance.
- Methodology and Approaches:
  - Propose different strategies to solve the matching problem. Possibilities might include:
    - Rule-based approaches (e.g., regular expressions, heuristics, fuzzy matching)
    - Embedding-based methods (e.g., SBERT, other semantic similarity models)
    - Hybrid methods that combine both techniques
  - Discuss the trade-offs between different approaches (accuracy, scalability, interpretability).
- Implementation:
  - Implement your chosen approach (or a combination of approaches) in Python using Jupyter Notebook.
  - Include code, visualizations, and a clear explanation of your methodology.
- Evaluation:
  - Measure and report the accuracy of your matching solution.
  - Provide insights into what worked well and what could be improved.
- Next Steps:
  - Discuss potential next steps or alternative approaches, give your wildest ideas! This will be a great opportunity to show us your creativity.

## Submission Guidelines

- Format:
  - Your submission should be a well-documented Jupyter Notebook.
- Content:

  - A clear description of your research and thought process.
  - Code implementation with comments and explanations.
  - Visualizations or metrics that support your analysis and results.
  - A conclusion summarizing your findings and potential future improvements.

- Instructions:
  - Refer to the [submission instructions](https://github.com/zolomart-dev/hiring-exercises/blob/master/README.md#general-instructions) for detailed guidelines.

## Evaluation Criteria

- Innovation: Creativity in the approaches proposed and crazy new ideas you want to try out beyond this exercise with us. (This is a very important part of the exercise!)
- Depth of Analysis: How well do you identify linguistic challenges and dataset nuances?
- Technical Rigor: Are your methods appropriate and optimized?
- Clarity: Can stakeholders understand your process and results?

Tip: Focus on a simple, well-explained solution rather than overly complex models.
