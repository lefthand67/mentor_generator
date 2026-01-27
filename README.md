# Mentor Generator

Mentor Generator creates a personalized AI learning mentor tailored to your language, knowledge level, goals, and constraints.

In a 5-minute conversation, it generates two configuration files that define your personal mentor. These files accompany you throughout your learning journey, tracking progress across sessions.

> **Important notes:**
> 1. AI models can hallucinate. The prompts contain many checks, but there is no 100% guarantee.
> 2. Don't drag sessions out - change chats often to avoid context degradation.
> 3. This is an experiment, not a production-ready solution.

## Quick Start

1. Copy the contents of `mentor_generator.json`
2. Paste into a powerful AI chat (Gemini 2.5 Pro, DeepSeek, Claude Opus 4.5)
3. Answer 9 questions about your learning goals
4. Receive two files: `mentor_system_prompt` and `course_config`
5. Start learning sessions by attaching these files to new chats

> **Model recommendations:** Gemini 2.5 Pro and DeepSeek start working immediately. ChatGPT often reads the file verbatim and asks what to do - not recommended.

## The 3-File System

### Generated Files (You Create Once)

| File | Purpose | When to Modify |
|------|---------|----------------|
| `mentor_system_prompt` | Mentor personality, teaching rules, behavior | Never |
| `course_config` | Your profile, constraints, curriculum | Rarely (only if constraints change) |

### Session Files (Created During Learning)

| File | Purpose | When Created |
|------|---------|--------------|
| `session_1`, `session_2`, ... | Progress tracking, mastery records, notes | End of each learning session |

**Key principle:** Session files are never overwritten. Each session creates a new file.

## Learning Workflow

### Starting a Session

1. Open a **new chat** with your AI
2. Attach `mentor_system_prompt` and `course_config`
3. Attach all previous session files (`session_1`, `session_2`, etc.)
4. Say "Let's continue" or "Start session"

The mentor reads all files, synthesizes your history, and continues from where you left off.

### Ending a Session

1. Signal session end ("Let's stop here", "End session", or reach a natural conclusion)
2. Mentor outputs a new `session_N` file
3. Save this file to your course folder
4. Next session, attach it along with previous sessions

### Why New Chats?

AI chats have context limits. Starting fresh with your files attached gives the mentor full context without old conversation clutter degrading quality.

## Answering the Questions

The meta-prompt asks 9 questions. Answer clearly and specifically - vague answers yield poor personalization.

| Question | How to Answer |
|----------|---------------|
| Language | "English", "Русский", or any language |
| Topic | "Python for Data Analysis", "History of Byzantium" |
| Experience Level | "Beginner in programming but strong in math" |
| Learning Goals | "Practice through examples and conceptual clarity" |
| Constraints | "Only laptop, Windows, 4 GB RAM" |
| Depth | "Medium tech level, focus on reasoning" |
| Subtopics | "NumPy arrays, SQL JOIN operations" |
| Time/Strategy | "DEPTH-FIRST, 1 hour on 3 weekdays" or "TIME-BOXED, finish by March" |
| Mentor Tone | "Friendly but strict", "Like Richard Feynman" |

## Sharing Your Mentor

The separation of files enables sharing:

- Share your `mentor_system_prompt` with others learning the same topic
- Each person creates their own `course_config` with their profile
- Same teaching style, personalized per user

## File Format

Files are shown in JSON, but the content can be converted to YAML, Markdown, or plain text. The structure matters, not the format.

## Migration from v0.30.x

If you have an existing monolithic JSON from previous versions:

1. **Recommended:** Start fresh with the new system
2. **Manual migration:** Extract relevant sections into the new file structure
3. Your learning progress from old sessions cannot be automatically migrated

## Folder Structure

```
my_course/
├── mentor_system_prompt     # Attach every session
├── course_config            # Attach every session
└── sessions/
    ├── session_1            # Attach to session 2+
    ├── session_2            # Attach to session 3+
    └── ...
```

## Example Projects

Real courses created with Mentor Generator:

1. [llm_from_scratch_practice](https://github.com/lefthand67/llm_from_scratch_practice)
2. [python_threading_for_ai_course](https://github.com/lefthand67/python_threading_for_ai_course)

## Pitfalls

- **Weak models:** Always use top-tier AI models - weak models lose context quickly
- **Vague answers:** Be specific in your responses during setup
- **Hallucinations:** Cross-check mentor advice with trusted sources
- **Long sessions:** Change chats often to maintain quality

## Questions?

If you have questions or want feedback on your setup, open an issue with your configuration files and scenario.
