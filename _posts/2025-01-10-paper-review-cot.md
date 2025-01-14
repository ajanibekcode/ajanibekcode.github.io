---
layout: post
title: paper review Chain-of-Thought in LLMs
---

paper review Chain-of-Thought Prompting Elicits Reasoning in Large Language Models
================

<p class="meta">10 Jan 2025</p>

<h1>Overview</h1>
This is my review of the paper published by the Brain Team at Google Research. The title is *Chain-of-Thought Prompting Elicits Reasoning in Large Language Models*. This post will go over the main task at hand, analyzing the results, and discussing potential flaws/areas of improvement. A link to this paper can be found [here](https://arxiv.org/abs/2201.11903).

<h2>Task</h2>
The focus is on arithmetic, common sense, and symbolic reasoning tasks. Specifically, when a model is given an input that has multiple layers of reasoning, we find that the output can lead to inaccurate results when dealing with these sorts of challenging tasks. 

<h2>"Solution"</h2>
We have seen a range of benefits when increasing the size of the Language Model, but unlocking reasoning ability can help us achieve high performance on tasks such as arithmetic, commonsense, and symbolic reasoning. The proposed method is motivated by two ideas: <br>
1. Generating natural language rationales that lead to the final answer (prior work involves generating intermediate steps from scratch or finetuning a pretrained model)
2. in-context few-shot learning via prompting where one can "prompt" a model with a few input-output exemplars demonstrating the task (has been successful with question-answering tasks)

What is few-shot learning?
A machine learning technique where a model is trained to learn and make predictions on a very small amount of labeled data.