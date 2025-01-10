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
The focus is on arithmetic, common sense, and symbolic reasoning tasks. Specifically, when a model is given an input that has multiple layers of reasoning, we find that the output can lead to inaccurate results when dealing with challenging tasks.