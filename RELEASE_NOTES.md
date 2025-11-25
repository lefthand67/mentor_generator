# Release Notes

## Version 0.29.1 - November 25, 2025

### Enhancements and New Features

- **Version Update**: Bumped version from 0.28.0 to 0.29.1.

- **Question Updates**:
  - Updated question_8 to include learning strategy options (DEPTH-FIRST and TIME-BOXED) along with detailed descriptions.
  - Removed the previous question_8 about time constraints.

- **Additional Context Changes**:
  - Moved `user_profile` from a separate section into `additional_context`.
  - Added `constraints_and_strategy` within `additional_context`, including details like hardware limits, software stack, efficiency principles, study constraints, and system constraints.
  - Updated the structure of `learning_changelog` to include `next_focus`.

- **Interaction Flow Enhancements**:
  - Added a new rule `pre_content_save_check` under `strict_turn_taking`. This rule ensures that before starting any new concept explanation, the mentor checks if a state update is required due to context depth. If so, it announces the need for a state update, requests user confirmation, and handles both confirmation and rejection scenarios.

- **JSON Update Protocol Enhancements**:
  - Added `context_limit_approaching` as a trigger condition under `json_update_protocol`. This sets an internal flag when the current token count exceeds the system constraints threshold.
  - Updated the rules to include specific instructions for handling context limit approaching, ensuring that state updates occur only at the next available pedagogical break point.

- **Learning Framework Adjustments**:
  - Clarified and expanded the `pacing_policy` under `constraints_and_strategy`.

### Bug Fixes

- None identified in this release.

### Documentation Updates

- Updated README.md to include projects examples.
- Added a real example section in README_ru.md for Deep Learning with PyTorch.
- Expanded warnings and best practices in both READMEs.
