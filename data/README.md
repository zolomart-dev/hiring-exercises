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
- Dataset Variations:
  - Explore how the number of products in `product_guide` varies across datasets.
  - Consider how these differences might affect matching performance.
- Methodology and Approaches:
  - Propose different strategies to solve the matching problem. Possibilities might include:
    - Rule-based approaches (e.g., regular expressions, heuristics, fuzzy matching)
    - Embedding-based methods (e.g., SBERT, other semantic similarity models)
    - Hybrid methods that combine both techniques
  - Discuss the trade-offs between different approaches (accuracy, scalability, interpretability).
- Implementation:
  - Implement your chosen approach (or a combination of approaches) in Python using Jupyter Notebook.
  - Include code, visualizations, and a clear explanation of your methodology.
  - Ensure your solution is runnable locally, and provide instructions on how to execute your notebook.
- Evaluation:
  - Measure and report the accuracy of your matching solution.
  - Provide insights into what worked well and what could be improved.
  - Consider discussing potential next steps or alternative approaches.

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

Your submission will be evaluated based on the following aspects:

- Problem Analysis: Clarity in understanding the matching challenge and data nuances.
- Technical Implementation: Quality, efficiency, and readability of your code.
- Innovation: Creativity in the approaches proposed and the solution implemented.
- Presentation: Clear documentation, visualizations, and explanation of your results.
- Practical Value: Insight into how your solution can be scaled or applied in a real-world scenario.
