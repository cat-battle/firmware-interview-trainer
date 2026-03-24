# Contributing to Firmware Interview Trainer

Thanks for wanting to help firmware engineers prep for interviews! Here's how you can contribute.

## Adding Questions

### Via GitHub Issue (easiest)
1. Click **Issues → New Issue**
2. Select the **"New Question"** template
3. Fill in the details
4. A maintainer will review, format it, and add it to the question bank

### Via Pull Request
1. Fork the repo
2. Edit `questions.json` — add your question to the `questions` array
3. Follow the format below
4. Open a PR with a brief description

### Question Format

**Conceptual question (no code):**
```json
{
  "id": "category-NNN",
  "category": "c-fundamentals",
  "difficulty": "medium",
  "type": "conceptual",
  "companies": ["general"],
  "question": "Your question here",
  "answer": "Detailed answer with explanations and code examples"
}
```

**Coding question (with editor + tests):**
```json
{
  "id": "category-NNN",
  "category": "bit-manipulation",
  "difficulty": "hard",
  "type": "coding",
  "companies": ["general"],
  "question": "Your question here",
  "answer": "Reference solution with explanation",
  "starterCode": "#include <stdio.h>\n\nint main() {\n    // TODO\n    return 0;\n}",
  "testCases": [
    { "description": "Basic case", "expected": "Expected stdout line" }
  ]
}
```

### Categories
| ID | Label |
|----|-------|
| `c-fundamentals` | C Language Deep Cuts |
| `bit-manipulation` | Bit Manipulation & Registers |
| `concurrency` | Concurrency & RTOS |
| `interrupts` | Interrupts & ISR Design |
| `memory` | Memory & Storage |
| `system-design` | System Design |
| `debugging` | Debugging Scenarios |
| `protocols` | Protocols & Interfaces |

Want to propose a new category? Open an issue to discuss it.

### Quality Guidelines

- **Teach, don't just test.** Answers should explain the _why_, not just the _what_.
- **Be firmware-specific.** Generic CS questions belong elsewhere. Focus on embedded systems, hardware interaction, real-time constraints.
- **Include real-world context.** Why does this matter in production firmware? When would an engineer encounter this?
- **Code should compile.** Test your starter code and reference solution with GCC before submitting.
- **Difficulty ratings:**
  - **Easy:** Junior engineer should know this (0-3 years)
  - **Medium:** Mid-level, working knowledge expected (3-7 years)
  - **Hard:** Senior/Principal level, deep understanding required (7+ years)

## Bug Reports & Feature Requests

Open an issue with:
- What you expected
- What actually happened
- Browser/OS info if it's a UI bug

## Code Changes

The app is a single `index.html` file by design — keeps it simple and deployable anywhere. If you're proposing a feature that requires a build step or external dependencies, let's discuss it in an issue first.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
