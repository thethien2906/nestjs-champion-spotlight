# Knowledge Gate Task Generation Prompt

Use this prompt to instruct an AI agent to prepare any gate in `projects/project-dogma-01/knowledge-gate/`.

---

```markdown
I am studying NestJS using a strict pedagogy anchored in official documentation (Official Docs Spec -> Worked Example -> Practice -> Automated Verification).

We are working on:
- Gate: [INSERT GATE NUMBER & NAME, e.g. 03-controller-decorator]
- Directory: projects/project-dogma-01/knowledge-gate/[INSERT GATE FOLDER]

Please perform the following two actions directly on the files:

1. In `practice.ts`:
At the very top of the file, insert a structured comment containing:
- Official Documentation Specification (exact definition, decorator signature, official URL)
- Worked Example (minimal 5–10 line canonical example)
- The Problem (clear inputs, expected output, and constraints for me to solve)
Leave the rest of `practice.ts` blank below the comment for me to write the implementation.

2. In `test.ts` (create in the same directory):
Write an executable TypeScript validation engine that imports my `practice.ts`, runs 3 test cases against it, and prints:
- `✓ [PASS] Case <N>: <Description>`
- `✗ [FAIL] Case <N>: <Description> -> Expected: <X>, Received: <Y>`
- Exits with code 0 if all pass, code 1 if any fail.

CRITICAL INSTRUCTION:
Do not write the solution in practice.ts. 
Do not output any explanation in your chat response. Your chat reply must strictly be:
Done
```
