---
layout: archive
title: "Research Methods"
permalink: /research-method
author_profile: true
---

While you are working on the student study group project, consider this as a practice to develop the base materials for your Master/Ph.D thesis.
I listed some useful approaches.

## Requirement Analysis

The following methods are commonly used for analyzing requirements and needs assessment in management research.

| Research Question | Suggested Method |
| :--- | :--- |
| Which attributes are important? How is our performance? | **Importance-Performance Analysis (IPA)** |
| What is the priority of needs based on discrepancies? | **Borich's Needs Assessment Model** |
| How can we visualize Borich Needs Assessment Model? | **The Locus of Focus (TLfF)** |

### Importance-Performance Analysis (IPA)
**IPA** is a widely used technique to identify areas that require improvement or resource allocation by comparing the importance of attributes to their perceived performance. It helps prioritize attributes into four quadrants: "Keep up the good work," "Concentrate here," "Low priority," and "Possible overkill."

Online app for IPA

[https://huggingface.co/spaces/dealmoa/analytics](https://huggingface.co/spaces/dealmoa/analytics)

This paper used IPA method for analyzing tourism dataset.

*Boley, B. B., McGehee, N. G., & Hammett, A. T. (2017). Importance-performance analysis (IPA) of sustainable tourism initiatives: The resident perspective. Tourism management, 58, 66-77.* https://doi.org/10.1016/j.tourman.2016.10.002
### Borich's Needs Assessment Model
The **Borich model** calculates the **Mean Weighted Discrepancy Score (MWDS)** to prioritize needs. It accounts for both the importance of a competency and the individual's perceived ability in that area, providing a more nuanced view of where development is most needed.

### The Locus of Focus (TLfF)
The **TLfF** is a visualization technique specifically designed for the results of Borich's model. It plots importance against the discrepancy to highlight critical areas for focus, making it easier to interpret complex needs assessment data.

## Web App Development Tools

We use the following tools to develop interactive applications, dashboards, and research prototypes. *With these tools, you can leverage your Python skills to transfrom ideas to reality very easily.*

- [**Gradio**](https://www.gradio.app/): A fast way to demo your machine learning model with a friendly web interface.

Example: Online chat app like ChatGPT

```
import gradio as gr

def greet(name, intensity):
    return "Hello, " + name + "!" * int(intensity)

demo = gr.Interface(
    fn=greet,
    inputs=["text", "slider"],
    outputs=["text"],
    api_name="predict"
)

demo.launch()
```
- [**Streamlit**](https://streamlit.io/): A powerful framework for building data-rich web applications with Python, ideal for data science projects.

Example: Show text on the web

```
import streamlit as st
import pandas as pd
import numpy as np

st.title('Uber pickups in NYC')
```
- [**Huggingface space**](https://huggingface.co/): Free Python-based web app hosting site. Most of my apps are runing on this site.
  - [https://huggingface.co/spaces/dealmoa/THU_AI](https://huggingface.co/spaces/dealmoa/THU_AI)
  - [https://huggingface.co/spaces/dealmoa/analytics](https://huggingface.co/spaces/dealmoa/analytics)
- [**Vercel**](https://vercel.com/): Free Node-based web app hosting site.
  - [https://courseai-one.vercel.app/](https://courseai-one.vercel.app/)
---
