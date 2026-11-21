# Contract

## Purpose
Prompt edits silently break output contracts because teams compare examples by eye.

## Input
JSON test suite containing cases with output, required_terms, forbidden_terms, max_words and required_sections.

## Output
Pass/fail report per case with exact regression reasons and aggregate score.

## Failure behavior
Reject malformed JSON. Report missing or unsafe fields explicitly. Never invent evidence or authorization.
