# 🚀 Step-by-Step User Guide

Mentor generator is your personal AI mentor, which creates a customized training program just for you. Unlike static courses, the mentor generator adapts to your language, knowledge level, goals, and even technical constraints.

In just 5 minutes of conversation, it generates a unique configuration file—a digital “core” of your personal mentor, which will accompany you throughout your educational journey, keep track of your progress, and evolve together with you.

Start — and your ideal mentor will be created.

> Warning:
> 1. AI models can hallucinate (just like any person). The prompt contains many checks and cross-checks, but there is no 100% guarantee against hallucinations.
> 2. The huge prompt size allows for a maximum set of model rules, but may also confuse it. Don’t drag sessions out, change chats more often, and be prepared for possible mentor malfunctions.
> 3. Remember this is an experiment, not a solution ready for industrial deployment.

## Step 1: Getting the JSON File

Copy the contents of the `mentor_generator.json` file and paste it into the chat window of any powerful model.

> Attention! This monolithic and extremely large prompt must only be loaded into very powerful models. Local models will quickly lose context.
> ChatGPT5 usually reads the file verbatim and starts asking you what you want it to do. On the other hand, models like Gemini 2.5 Pro, Deepseek start working immediately, so we recommend using them.

## Step 2: Understanding Dialogue Principles

The dialogue scenario is pre-written in the prompt itself. The AI will ask you questions one by one, guiding you through the steps described below.

1. The AI starts the session in Russian and introduces itself.
2. Then it automatically switches to the language of your response.
   * If you reply in English, it continues in English.
   * If you reply in Spanish, it continues in Spanish, etc.
3. It asks one question at a time; answer them in the same sequence. If you realize you forgot to say something, you can clearly state that in another reply (for example: "I forgot to mention…").
4. After all questions, a “pedagogical validation” step is performed to ensure the mentor’s design matches your profile. You do not need to understand the details of the check; the step is required for the model’s self-control.
5. After your confirmation, it generates a new JSON file—the system prompt for your personal learning mentor.

Afterwards, you will use this generated JSON as a system message in future sessions.

## Step 3: How to Answer the Questions

Answer with brief, clear sentences, but the more detail you give, the more personalized the result will be.

💡 Tip: Don't be vague and don't jump between topics, so as not to confuse the AI. A bad answer is not in your interest.

| Prompt Question           | How to Answer                                                             |
| ------------------------- | ------------------------------------------------------------------------- |
| Language                  | “English”, “Русский”, or any supported language.                   |
| Topic                     | “Python for Data Analysis”, “History of Byzantium”, etc..          |
| Experience Level          | “Beginner in programming but strong in math.”.                     |
| Learning Goals            | “Practice through examples and conceptual clarity.”.                |
| Constraints               | “Only laptop, Windows 7, 4 GB RAM.”.                               |
| Depth                     | “Medium tech level, focus on reasoning.”.                          |
| Subtopics                 | “NumPy arrays, SQL JOIN operations, project structure.”.           |
| Time Limits               | “1 hour per day, in the evenings.”.                                |
| Mentor Tone/Role          | “Friendly but strict.”, “More experienced colleague.” You may name a specific real or fictional person. |

The mentor uses these answers to create a structured JSON file with a system prompt.

## Step 4: Saving and Reusing Your Personalized Prompt

When the AI displays the JSON block, copy it exactly as is, including brackets.

Save it. Afterwards, you can reuse it by pasting the saved JSON into any new chat.

## Step 5: Continuing Sessions (Managing State)

Your mentor prompt supports session continuity:

* It tracks your progress via `additional_context`.
* Upon restart, the AI reads `additional_context` and resumes where you stopped.
* The JSON updates only on certain triggers (session end, milestone achievement, progress check).

When the AI says “Updating your learning progress…”, it will display a new JSON block—copy and save it, replacing the previous one.

Wishing you an interesting and engaging learning experience!

***

## Real-World Example (For Deep Learning Engineers):

Suppose you want a customized mentor for “Deep Learning with PyTorch,” and your technical limitation is: “Only a Linux laptop, 8GB RAM.” You reply to each prompt as shown in the table above. The AI generates a JSON system prompt tailored to your exact context. This lets you resume your session after a break, and your learning program adapts as you progress. If a topic feels unclear (e.g., “backpropagation math”), you clarify it in the next answer—the mentor evolves with your feedback.

## Pitfalls and Peer Review

- Overly large prompts can crash or confuse weaker models: always use top-tier, current AI models for these workflows.
- Vague answers yield poor personalization; always be specific in your responses.
- Expect occasional model hallucinations: cross-check all mentor advice with trusted sources or your own expertise.
- Treat this as an experimental workflow, not a production-ready solution.

For professional use, always review each stage of mentor generation and verify the final JSON configuration against your learning goals and constraints. This ensures the system prompt is reliable and safe for serious learning.

If you have further questions on best practices, configuration pitfalls, or want peer review of your setup, please provide your JSON block and scenario for feedback.
