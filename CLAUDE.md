# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Mentor Generator is a **meta-prompt engineering project** that creates personalized AI learning mentors. The system generates two configuration files that define a customized learning experience.

This is **not a traditional software project** - there is no build system, no package manager, no automated tests. The JSON/template files are the product.

## Architecture

### File Structure

```
mentor_generator/
├── mentor_generator.json              # Meta-prompt (questionnaire only)
├── templates/
│   ├── mentor_system_prompt.template  # Template for mentor behavior rules
│   └── course_config.template         # Template for user profile/curriculum
├── README.md
├── CLAUDE.md
└── changelog
```

### Generated Output (Per User)

```
user_course/
├── mentor_system_prompt    # Static mentor rules (attach every session)
├── course_config           # User profile + curriculum (attach every session)
└── sessions/
    ├── session_1           # Immutable session records
    ├── session_2
    └── ...
```

### Core Files

#### `mentor_generator.json` (Meta-Prompt)

Contains ONLY the questionnaire logic:
- **meta_prompt_logic** - Instructions for conducting 9-question collection
- **interactive_input_sequence** - The questions and flow control
- **validation** - Pedagogical validation checks
- **persona_mapping_protocol** - Translates persona preferences into instructions
- **guidance_for_user** - Hardcoded user instructions (printed verbatim)
- **file_generation_protocol** - How to fill and output templates
- **template_references** - Points to template files

#### `templates/mentor_system_prompt.template`

Defines mentor behavior (filled once during generation):
- **mentor_profile** - Persona, tone, teaching style
- **mentor_self_control** - Self-correction, peer review checks
- **session_files_protocol** - How to read attached files
- **session_protocols** - First session vs subsequent session behavior
- **interaction_flow** - Turn-taking, emergency brakes
- **learning_framework** - Mastery-gated progression rules
- **session_output_protocol** - Exact template for session file output

#### `templates/course_config.template`

Defines user-specific data (filled once during generation):
- **user_profile** - Language, assessment, skills, goals
- **constraints_and_strategy** - Hardware, pacing choice
- **curriculum** - Phased learning progression
- **mentor_failure_log** - Error tracking for self-correction

### Key Design Patterns

1. **Separation of Concerns**: Meta-prompt and mentor are different roles in different files
2. **Template-First Output**: Mentor fills exact templates, never "decides" what to include
3. **Immutable Session History**: Each session creates a new file, old files never modified
4. **Predictability Through Constraints**: Output format is constrained, not instructed
5. **Reusable Mentor Templates**: Same mentor_system_prompt works for multiple users
6. **Format-Agnostic**: JSON shown, but YAML/Markdown/text equally valid

### Learning Strategies

- **DEPTH-FIRST**: Mastery-gated, time is variable, knowledge quality guaranteed
- **TIME-BOXED**: Deadline-driven, content depth may be reduced to meet timeline

## Usage Workflow

### Creating a Mentor (Meta-Prompt Phase)

1. Copy `mentor_generator.json` content
2. Paste into powerful LLM chat
3. Answer 9 questions
4. AI validates and outputs TWO files
5. Save both files to course folder

### Learning Sessions

1. Open new chat, attach `mentor_system_prompt` + `course_config` + all `session_N` files
2. Say "Let's continue"
3. Learn with mastery-gated progression
4. At session end, mentor outputs `session_N` file
5. Save new session file, repeat

## Recommended Models

- Gemini 2.5 Pro (starts immediately)
- DeepSeek (starts immediately)
- Claude Opus 4.5
- NOT ChatGPT-5 (reads verbatim and asks what to do)

## JSON/Template Conventions

- `_notes` and `_template_notes` fields contain instructions for AI, never overwritten
- Placeholders marked with `<...>` are filled during generation
- Top-level fields are human-readable and machine-usable
- Version tracked in `metadata.version`

## When Editing

- Preserve all `_notes` fields exactly as-is
- Maintain JSON validity (files must parse correctly)
- Follow existing naming conventions (snake_case for keys)
- Version bumps: `metadata.version` and `metadata.modified`
- Update `changelog` for significant changes
- Update `RELEASE_NOTES.md` for releases
- Keep `guidance_for_user.message_paragraphs` as exact text to print
