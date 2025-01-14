---
layout: review
title: Chain-of-Thought in LLMs
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

Prompt consists of triples: <input, chain-of-thought, output> <br>

A chain-of-thought is a series of intermediate natural language reasoning steps that lead to the final output. A prompting only approach is
important because it does not require a large training dataset and a single model checkpoint can perform many tasks without loss of generality.
We can think of this prompting in similarity to how humans think when breaking down a problem with multiple layers: <br>

*After Jane gives 2 flowers to her mom she has 10...then after she gives 3 to her dad she will have 7...so the answer is 7.*

Properties that make this method attractive: <br>

* Allows models to decompose multi-step problems into intermediate steps, which means additional computation can be allocated to problems that require more reasoning steps
* Provides a window into how the model thinks, giving us an idea of how it arrived to a specific output from a specific input
* Can be used for tasks such as math word problems, commonsense reasoning, and symbolic manipulation
* Can be readily elicited into models simply by including examples with chain-of-thought prompting

Important results

The study finds that this prompting is an emergent ability, meaning it only becomes apparent at larger model scales (100B parameters or more) and smaller models 
do not benefit. The prompting has larger gains for more complex problems seen by the **GSM8K** dataset and performance being negative or not existent with **SingleOp** dataset. <br>

Why does CoT prompting work?
* Clarify complex problems: models reason through each step logically
* Improve accuracy: errors reduced in larger models
* Activate pretrained knowledge: sequential reasoning helps the model utilize its prior training

Question to explore: Is the neural network actually "reasoning"?

