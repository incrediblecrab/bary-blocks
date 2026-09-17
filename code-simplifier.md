# Code simplifier

**For LLM:** Use after writing or modifying code, to simplify what you just touched without altering what it does. Prioritize readable, explicit code over compact code; clarity is the goal, not fewer lines. Refine only recently modified code unless asked for a broader scope.

## Preserve functionality

Never change what the code does, only how it does it. All original features, outputs, and behaviors must remain intact.

## Apply the project's standards

Follow the standards the project already states, in its own standards file such as `CLAUDE.md`, `AGENTS.md`, or a style guide, and in the surrounding code. Where a project states no preference, match the conventions of its language and the surrounding files. The defaults this block was written against are specific to JavaScript and TypeScript:

- Use ES modules with proper import sorting and extensions.
- Prefer the `function` keyword over arrow functions.
- Use explicit return type annotations for top-level functions.
- Follow proper React component patterns with explicit Props types.
- Use proper error handling patterns, avoiding try/catch where possible.
- Maintain consistent naming conventions.

## Enhance clarity

- Reduce unnecessary complexity and nesting.
- Eliminate redundant code and abstractions.
- Improve readability through clear variable and function names.
- Consolidate related logic.
- Remove comments that only describe what the code already says.
- Avoid nested ternary operators; prefer a switch statement or an if/else chain for multiple conditions.
- Choose clarity over brevity, because explicit code is often better than overly compact code.

## Maintain balance

Avoid over-simplification that would reduce clarity or maintainability, produce clever solutions that are hard to follow, combine too many concerns into one function or component, remove a helpful abstraction, prioritize fewer lines over readability, or make the code harder to debug or extend.

## Focus the scope

Refine only code modified or touched in the current session, unless explicitly instructed to review a broader scope.

## Process

1. Identify the recently modified sections.
2. Analyze them for opportunities to improve elegance and consistency.
3. Apply the project's standards.
4. Ensure all functionality remains unchanged.
5. Verify the result is simpler and more maintainable.
6. Document only the changes significant enough to affect understanding.

Work proactively: refine code immediately after it is written or modified, without waiting for an explicit request.
