---
title: "Playing with LLMs locally"
date: 2025-06-01T16:07:28+01:00
tags: [Hacking,LLM,]
---

# Playing with LLMs locally

After a talk by [Nick Burch at Berlin Buzzwords](https://www.youtube.com/watch?v=VzsOzQOhs6M) I finally got started playing with LLMs locally. The easiest way to get started for me: [llm tool](https://github.com/simonw/llm) by Simon Willison :)

## Backstory

Back when it came out in winter 2022 I started playing around with ChatGPT - mostly to generate texts from individual terms given as what teachers in German primary schools call "learning words" - usually they are handed out for pupils to get prepared for a dictation (written to check spelling skills): It's a lot more fun to prepare for theses tests with fun texts than with mere lists of words :) Back then the results were impressive - but also frightning given the implications for ease of generating mis-information, fake social media profiles, spamming search indeces and more.

Since then I've been on the edge with LLMs: Generated texts and images all looked like polished marketing material optimised for performance on social media - but lacked all human liveliness. Summaries on content was pretty much hit and miss: While for short videos it looked good, for longer ones models quickly went off the rails mixing in content that seemed to come from the training corpus but not from the piece to summarize. Asked to provide a summary of a book providing only the book title seemed to work OK for very popular English language literature, but fails for obvious reasons for niche German stuff - with the usual tendency of models to make things up rather than display a warning about the lower liklyhood of the generated text.

## Switching onmathe the commandline

Nick's talk did a great job providing an easy to understand intro to the ins and outs of LLMs for running them locally as an engineer. The most helpful slide for me: The one pointing to [llm tool](https://github.com/simonw/llm) - a commandline tool, written in Python, so easy to install e.g. through `pipx`. Using that several popular APIs can be accessed from the commandline, in addition several popular local LLMs have been integrated, so switching back and forth really is a matter of changing commandline options.
