# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Mentor Generator is a **meta-prompt engineering project** that creates personalized AI learning mentors. The core artifact is `mentor_generator.json` - a sophisticated prompt that guides an LLM through an interactive questionnaire to generate customized learning system prompts.

This is **not a traditional software project** - there is no build system, no package manager, no automated tests. The JSON file itself is the product.

## Architecture

### Core File: `mentor_generator.json`

The JSON contains these key sections:

- **meta_prompt_logic** - Instructions for the AI to conduct the 9-question interactive collection process
- **mentor_system_prompt_template** - Template for the generated personalized mentor prompt
- **validation** - Pedagogical self-validation checks (factual integrity, persona consistency, progression gates)
- **interaction_flow** - Two modes: Teaching Mode (primary) and State Update Mode (administrative)
- **learning_framework** - Rules for mastery-gated progression, turn-taking, emergency brake protocols
- **state_update_protocols** - JSON regeneration triggers and session continuity

### Key Design Patterns

1. **Dual Interaction Modes**: Teaching mode for learning, state update mode for progress tracking
2. **Mastery-Gated Progression**: Students cannot advance without demonstrating understanding
3. **Session Continuity**: `additional_context` field preserves learning state across sessions
4. **Persona Mapping Protocol**: Translates user persona preferences (e.g., "Ringo Starr") into actionable instructions
5. **Pre-Response Peer Review**: Built-in validation before generating answers

### Learning Strategies

- **DEPTH-FIRST**: Mastery-gated, time is variable, knowledge quality guaranteed
- **TIME-BOXED**: Deadline-driven, content depth may be reduced to meet timeline

## Usage Workflow

1. Copy entire `mentor_generator.json` content
2. Paste into chat with powerful LLM (Gemini 2.5 Pro, DeepSeek, Claude Opus 4.5)
3. Answer 9 interactive questions (language, topic, level, goals, constraints, depth, subtopics, strategy, tone)
4. AI performs pedagogical validation
5. AI generates personalized JSON mentor prompt
6. Use generated JSON in future learning sessions
7. When mentor announces state update, save new JSON and continue in fresh chat

## Recommended Models

- Gemini 2.5 Pro (starts immediately)
- DeepSeek (starts immediately)
- Claude Opus 4.5
- NOT ChatGPT-5 (reads verbatim and asks what to do)

## JSON Structure Conventions

- `_notes` fields contain human instructions for AI and should never be overwritten
- `prompt` section contains AI mentor instructions not shown to users
- Top-level fields are human-readable and machine-usable
- Version tracked in `metadata.version`

## When Editing

- Preserve all `_notes` fields exactly as-is
- Maintain JSON validity (the file must parse correctly)
- Follow existing naming conventions (snake_case for keys)
- Version bumps go in `metadata.version` and `metadata.modified`
- Update `changelog` file for significant changes
- Update `RELEASE_NOTES.md` for releases
