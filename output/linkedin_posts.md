# LinkedIn Posts

Newest first. The posts below are examples; replace them with past posts that best show your style. Posts the AI writes go here too.

## 2026-10-29 · What I'd tell first-years about learning AI

A first-year in my dorm asked me how to start learning AI. I gave a pretty messy answer, so here's a better one.

Build something small you'll actually use. My first project was a to-do app with a chatbot bolted on. I never opened it again. I use my study helper every week, and that's why I kept fixing it.

Use AI to check your work, not to do it. I learned this in algorithms, and then again in compilers.

Before you change anything, write a few questions you already know the answers to. It's the only way to tell if a change helped.

And post what you learn, even when it's small. People will correct you. That's kind of the point.

## 2026-10-27 · I studied for my midterm with the tool I built

I took my OS midterm on Friday. For the first time, I studied with a tool I built myself.

It helped less than I expected, and in a different way.

I thought I'd ask it questions and learn from the answers. Mostly, I didn't. Reading its answers felt like studying. It's the same trap I fell into with ChatGPT in my algorithms class.

What worked was flipping it around. I had it quiz me on one lecture, answered without looking, then asked which slides I'd gotten wrong. That turned up three topics I thought I knew and didn't.

The grade isn't back yet. But I walked out knowing which answers I was sure of, which hasn't always been true.

Building the tool taught me a lot about AI. Using it taught me more about how I study.

## 2026-10-20 · 12 classmates used my study helper

Last week I shared my study helper with 12 classmates before our OS midterm. Within a day, they'd asked it things I never tested.

I'd built it around my own questions, which are mostly about concepts, like "what is a page fault?" Theirs were different:

1. "Which lecture covers deadlocks?" It couldn't say. It only knew the slide text, not which lecture a slide came from. Now every chunk carries its lecture title.
2. "Explain question 3 from last year's exam." It had never seen that exam, and it made up an answer anyway. Now it tells you what it doesn't have.
3. Questions in Mandarin and Spanish. It answered in English. Still working on that one.

Twelve people found more gaps in a day than I found in a month of testing on my own.

My test set went from 20 questions to 41. Half of the new ones are theirs.

## 2026-10-13 · A new model came out, so I ran my 20 questions

A new model came out last week, and my feed was full of charts saying it beats everything. I did what I do with every release now: I ran it on the 20 questions I test my study helper with.

The questions come from past quizzes in my OS class, and I know every answer.

My current setup gets 16 right. The new model got 17. The one it fixed needed two slides from different lectures, which is exactly the kind of question my helper struggles with.

It also cost about three times as much per question, and it was slower.

So I'm not switching yet. One more right answer isn't worth that on a student budget. But I wrote down which question it fixed. It shows me where my own setup is weak, and that's more useful to me than any chart.

Your test questions don't need to be fancy. Twenty is enough to see whether something is better for what you actually do.

## 2026-10-06 · I stopped asking AI for answers

For the first month of my algorithms class, I pasted every problem set into ChatGPT. I'd read the answer, nod, and move on. It felt very productive.

Then I took the first quiz without it. That went about as well as you'd guess.

Reading an answer and being able to get there yourself are two different things. AI made the first one effortless, so I mistook it for the second.

Now I use it differently. I ask for a hint, not the solution. When I think I understand something, I ask it to quiz me, and I don't look anything up until I've answered.

It's slower. My grades are better. And I can actually explain my own code now.

## 2026-09-28 · What broke in my first RAG project

I spent three weekends building a study helper for my operating systems class. You ask it a question, and it answers from the lecture slides.

The first version was confidently wrong about half the time.

Three things broke, and none of them were in the tutorial I started with:

1. Chunks were too small. A slide is often a title, ten words, and a diagram. Searching slide by slide found the right words with none of the context. Grouping slides by lecture section fixed most of it.
2. The model ignored my notes. Even when search found the right slides, it sometimes answered from what it already knew, which didn't always match how my professor teaches it. Telling it to answer only from the slides, and to cite slide numbers, kept it honest.
3. I was testing on vibes. I'd ask two questions, feel good, and move on. Writing 20 questions with known answers showed me which changes actually helped.

All of it showed up the first time I used it to study for real.

If you're learning AI, build something small for a class you're actually taking. You'll find the problems tutorials skip.

## 2026-09-22 · I let AI write my parser, then went to office hours

Last week I let an AI coding assistant write most of the parser for my compilers assignment. It passed every test on the first try.

Then I went to office hours with a question about one edge case, and the TA asked me to walk through how my parser handled it.

I couldn't. I knew what it did. I had no idea how.

The code wasn't bad. It was cleaner than what I would have written. But it was someone else's solution with my name on it, and I'd skipped the part where I learn how parsers work.

So I rewrote it myself, with the AI's version closed. It took a whole evening and came out messier. I can explain every line now.

What I do now: for class projects, I write the code and ask AI to review it. For my side project, where the goal is to ship something, I let it write more. Same tool, different job.

## 2026-09-08 · Embeddings finally clicked when I searched my own notes

I read about embeddings three times before they made sense. What finally worked was trying them on my own lecture notes.

Every explanation said something like "text turned into vectors that capture meaning." True, and it meant nothing to me.

So I split my OS notes into paragraphs, turned each one into an embedding, and searched for "how does the computer juggle several programs at once."

The top result was my paragraph on context switching. It never says "juggle" or "at once." It matched because it was about the same thing.

That was the moment. Embeddings let you search by meaning instead of by matching words. The vectors are just how the computer keeps track of what's close to what.

This is the first piece of a study helper I'm building this semester. If a concept isn't clicking for you, try it on something you already know well. Your own notes work great, because you can tell right away whether a result makes sense.
