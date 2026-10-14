# LinkedIn Posts

Newest first. The two below are examples; replace them with past posts that best show your style. Posts the AI writes go here too.

## 2026-01-19 · What broke in my first RAG project

I spent three weekends building a study helper for my operating systems class. You ask it a question, and it answers from the lecture slides.

The first version was confidently wrong about half the time.

Three things broke, and none of them were in the tutorial I started with:

1. Chunks were too small. A slide is often a title, ten words, and a diagram. Searching slide by slide found the right words with none of the context. Grouping slides by lecture section fixed most of it.
2. The model ignored my notes. Even when search found the right slides, it sometimes answered from what it already knew, which didn't always match how my professor teaches it. Telling it to answer only from the slides, and to cite slide numbers, kept it honest.
3. I was testing on vibes. I'd ask two questions, feel good, and move on. Writing 20 questions with known answers showed me which changes actually helped.

All of it showed up the first time I used it to study for real.

If you're learning AI, build something small for a class you're actually taking. You'll find the problems tutorials skip.

## 2026-01-15 · I stopped asking AI for answers

For the first month of my algorithms class, I pasted every problem set into ChatGPT. I'd read the answer, nod, and move on. It felt very productive.

Then I took the first quiz without it. That went about as well as you'd guess.

Reading an answer and being able to get there yourself are two different things. AI made the first one effortless, so I mistook it for the second.

Now I use it differently. I ask for a hint, not the solution. When I think I understand something, I ask it to quiz me, and I don't look anything up until I've answered.

It's slower. My grades are better. And I can actually explain my own code now.
