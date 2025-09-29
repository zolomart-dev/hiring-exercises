# Welcome AI-focused Product Exercise

```
TIMEBOX:    2-3 days max
LANGUAGES:  Python
RUNTIMES:   Python
FRAMEWORKS: FastAPI, Langchain, spaCy, etc
TESTS:      nice to have, but not mandatory
DOCS:       nice to have, but not mandatory
```

## Overview

This exercise is to implement the best possible solution for the exercises below in the time allotted. We're evaluating your ability to take a set of requirements and spike a holistic solution that demonstrates craftsmanship, thoughtfulness and good architectural design. This is **NOT** a test of how well you know Python, nor should you try to impress us with overly clever and obtuse solutions. If you want to impress us, build something that is highly accurate and fast :smiley:.

## Problem Description

Customers send WhatsApp messages to order products, but these messages are unstructured and can be in either English or Mandarin. The challenge is to:

1. Process text messages in different formats and languages (English and Mandarin)
2. Extract crucial information:
   - Product name
   - Quantity
   - Unit (if specified)
   - Delivery location (if specified)
   - Delivery date (if specified)
   - Packing size (if specified)
3. Return structured data that can be used for order processing and product matching (Out of current scope)

## Deliverables

1. A functioning AI service (FastAPI app or framework of your choice) with at least one endpoint (/extract) that:

   - Accepts a WhatsApp message (raw text) as input.
   - Returns the extracted structured information as JSON.

2. Documentation (README or inline comments) describing:

   - Approach and assumptions made.
   - Limitations.
   - Proposal for how you would improve extraction accuracy if given more time/resources (e.g., better training data, hybrid approaches, fine-tuning, external APIs, feedback loops, etc.).、

3. (Optional but nice-to-have): Tests and evaluation examples.

## Requirements & Expectations

- The solution should handle messages in both English and Mandarin.
- The output must include, where applicable:
  - product_name
  - quantity
  - unit
  - delivery_location
  - delivery_date
  - packing_size
- If a field is not present in the message, return it as null.
- Handle variations in phrasing, spelling, and mixed language where possible.
- Focus on accuracy and robustness. Simpler but more accurate solutions are preferred over overly complex but brittle ones.

## Examples

### Example 1: English

Input:

```
Hi, I want to order 20 kg of Jasmine rice to be delivered to Jalan Ampang this Friday.
```

Expected Output:

```
{
  "items": [
    {
      "product_name": "Jasmine rice",
      "quantity": 20,
      "unit": "kg",
      "packing_size": null
    }],
  "delivery_location": "Jalan Ampang",
  "delivery_date": "Friday"
}
```

### Example 2: Mandarin

Input:

```
我要订购5箱苹果，下星期一送去吉隆坡。
```

Expected Output:

```
{
  "items": [
    {
      "product_name": "苹果",
      "quantity": 5,
      "unit": "箱",
      "packing_size": null
    }],
  "delivery_location": "吉隆坡",
  "delivery_date": "下星期一"
}
```

### Example 3: Mixed / Informal

Input:

```
Pls send me 10 bags Milo 2kg pack to Penang tomorrow.
```

Expected Output:

```
{
  "items": [
    {
      "product_name": "Milo",
      "quantity": 10,
      "unit": "bags",
      "packing_size": "2kg"
    }],
  "delivery_location": "Penang",
  "delivery_date": "tomorrow"
}
```

### Example 4: Missing Details

Input:

```
Can I get 3 cartons of Coke (1kg)?
```

Expected Output:

```
{
  "items": [
    {
      "product_name": "Coke",
      "quantity": 3,
      "unit": "cartons",
      "packing_size": "1kg"
    }],
  "delivery_location": null,
  "delivery_date": null
}
```

### Example 5: Multiple Items

Input:

```
I want to order 2 kg of Jasmine rice (10kg pack) and 5 boxes of eggs.
```

Expected Output:

```
{
  "items": [
    {
      "product_name": "Jasmine rice",
      "quantity": 2,
      "unit": "kg",
      "packing_size": "10kg pack"
    },
    {
      "product_name": "eggs",
      "quantity": 5,
      "unit": "boxes",
      "packing_size": null
    }],
  "delivery_location": null,
  "delivery_date": null
}
```

### Example 6: Multiple Items in List Form

Input:

```
Fish fillet-5ctn
Prawn meat -1ctn
King prawn-
Cwp bill on next month
```

Expected Output:

```
{
  "items": [
    {
      "product_name": "Fish fillet",
      "quantity": 5,
      "unit": "ctn",
      "packing_size": null
    },
    {
      "product_name": "Prawn meat",
      "quantity": 1,
      "unit": "ctn",
      "packing_size": null
    },
    {
      "product_name": "King prawn",
      "quantity": 0,
      "unit": null,
      "packing_size": null
    }],
  "delivery_location": null,
  "delivery_date": null
}
```

### Example 7: Items with Packaging Size

Input:

```
Boneless chicken 10kg
Pork chop bone in 5kg
Beef brisket 5kg
Beef short plate 1mm 2kg

Deliver 1 Oct
```

Expected Output:

```
{
  "items": [
    {
      "product_name": "Boneless chicken",
      "quantity": 10,
      "unit": "kg",
      "packing_size": null
    },
    {
      "product_name": "Pork chop bone in",
      "quantity": 5,
      "unit": "kg",
      "packing_size": null
    },
    {
      "product_name": "Beef brisket",
      "quantity": 5,
      "unit": "kg",
      "packing_size": null
    },
    {
      "product_name": "Beef short plate",
      "quantity": 2,
      "unit": "kg",
      "packing_size": "1mm"
    }],
  "delivery_location": null,
  "delivery_date": "1 Oct"
}
```

## Evaluation Criteria

- _Correctness & Accuracy_: Does the service extract information correctly?
- _Robustness_: Does it handle both English and Mandarin? Can it deal with informal or mixed inputs?
- _Architecture & Code Quality_: Is the code clear, maintainable, and thoughtfully structured?
- _Documentation_: Are the assumptions, approach, and limitations clearly explained?
- _Improvement Proposal_: Does the candidate provide a practical plan to enhance accuracy?
