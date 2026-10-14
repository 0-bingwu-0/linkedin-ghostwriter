# What Broke in My First RAG Project, and What Fixed It

This semester I built a study helper for my operating systems class. You ask it a question, like "What's the difference between a process and a thread?", and it answers from my professor's lecture slides instead of the whole internet.

It took three weekends. The first version worked fine in a demo. When I actually studied with it, it was confidently wrong about half the time. Here's what went wrong and how I fixed it, in case you're building something similar.

## How it works

The idea is called RAG, short for retrieval-augmented generation. It has two steps:

1. **Find the relevant notes.** I split the slides into chunks and turned each chunk into an embedding, a list of numbers that captures its meaning. When I ask a question, it finds the chunks closest in meaning to it.
2. **Answer from them.** It sends my question and those chunks to the model, and the model writes the answer.

Most tutorials stop here. This is also where my problems started.

## Problem 1: Chunks were too small

I started with one chunk per slide, because it seemed natural. But a slide is often a title, ten words, and a diagram the text can't capture. Search would find a slide that mentioned "semaphore," with nothing around it that explained what a semaphore does.

**Fix:** I grouped slides by lecture section, so each chunk covers one idea from start to finish. Answers got better right away. Bigger wasn't always better, though. When I tried a whole lecture per chunk, search got vague again. One section per chunk worked best for my slides.

## Problem 2: The model ignored my notes

Even when search found the right slides, the model sometimes answered from what it already knew. Usually that was close enough. But my professor teaches a few things in a specific way, and the exam follows the slides.

**Fix:** I changed the instructions: answer only from the slides provided, cite the slide numbers you used, and say "not in the slides" if the answer isn't there. The citations helped me too. I could check the source in a few seconds instead of just trusting it.

## Problem 3: I was testing on vibes

For the first two weekends, I'd change something, ask two questions, feel good, and move on. Then the next change would quietly break something else.

**Fix:** I wrote 20 questions from past quizzes, each with the answer and the slide it came from. After every change, I ran all 20 and checked two things: was the answer right, and did it cite the right slides? It's a tiny test set, but it showed me which changes actually helped. Section-sized chunks did. A fancier embedding model I tried barely made a difference.

## What I'd tell myself three weekends ago

* Use it for real, early. Demo questions are easy. The questions you have the night before a quiz are not.
* Make it show its sources. That's how you catch its mistakes, and how you learn where to look.
* Write your test questions first. 20 is enough to start.

Next, I'm adding practice questions: give it a lecture, and it quizzes me on it. I'll share how that goes.
