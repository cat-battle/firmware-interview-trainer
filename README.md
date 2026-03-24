# 🔧 Firmware Interview Trainer

An open-source, interactive interview prep tool for firmware and embedded systems engineers. Practice real interview questions with a live C compiler in your browser.

**[Try it live →](https://cat-battle.github.io/firmware-interview-trainer/)**

![Screenshot](screenshot.png)

## Features

- 🎯 **33+ firmware-specific questions** across 8 categories
- 💻 **Live C compilation** — write, compile, and run C code in the browser
- ✅ **Test case validation** — automated pass/fail checking for coding questions
- ⏱️ **Timer mode** — simulate interview pressure with countdown timers
- 📊 **Progress tracking** — track which questions you've reviewed and your confidence level
- ⌨️ **Monaco editor** with vim keybindings (optional)
- 📱 **Responsive** — works on desktop and tablet
- 🌙 **Dark theme** — easy on the eyes during late-night prep sessions

## Categories

| Category | Questions | Description |
|----------|-----------|-------------|
| 🔤 C Language | 6 | volatile, const, static, struct packing, offsetof, memory pools |
| 🔧 Bit Manipulation | 3 | Set/clear/toggle bits, bit field extraction, ring buffers |
| 🔄 Concurrency & RTOS | 4 | Priority inversion, deadlocks, mutexes vs semaphores, state machines |
| ⚡ Interrupts & ISR | 3 | ISR best practices, ARM Cortex-M NVIC, watchdog timers |
| 💾 Memory & Storage | 3 | Memory layout, malloc alternatives, NOR vs NAND flash |
| 🏗️ System Design | 4 | Secure boot, OTA updates, safety-critical systems, low-power design |
| 🐛 Debugging | 2 | Field crash debugging, HardFault analysis |
| 🔌 Protocols | 8 | SPI/I2C, USB enumeration, UART, CAN bus, DMA, Ethernet |

## Quick Start

### Option 1: GitHub Pages (recommended)
Visit the [live site](https://cat-battle.github.io/firmware-interview-trainer/) — no setup required.

### Option 2: Run Locally
```bash
git clone https://github.com/cat-battle/firmware-interview-trainer.git
cd firmware-interview-trainer
# Any static file server works:
python3 -m http.server 8000
# Open http://localhost:8000
```

## How It Works

### C Compilation
Code is compiled and run using the [Wandbox API](https://wandbox.org/) — a free, open-source online compiler. No API key required. Your code is sent to the API, compiled with GCC, and the output is returned to your browser.

**Privacy note:** Your code is sent to the Wandbox API for compilation. If you need fully offline compilation, you can self-host a compiler API and update the URL in the source.

### Progress Tracking
All progress is stored in your browser's `localStorage`. Nothing leaves your machine. Clear your browser data to reset progress.

## Contributing Questions

We welcome community-contributed questions! Here's how:

### Submit via GitHub Issue
Use the [New Question template](.github/ISSUE_TEMPLATE/new-question.md) to propose a question. Maintainers will review and add approved questions.

### Submit via Pull Request
1. Fork the repo
2. Add your question to `questions.json` following the existing format
3. Open a PR with a description of the question and why it's useful

### Question Format
```json
{
  "id": "category-NNN",
  "category": "c-fundamentals",
  "difficulty": "easy|medium|hard",
  "type": "conceptual|coding",
  "companies": ["general"],
  "question": "Your question text here",
  "answer": "Detailed answer with code examples",
  "starterCode": "(for coding questions) Initial code template",
  "testCases": [
    { "description": "What this tests", "expected": "Expected output line" }
  ]
}
```

### Guidelines
- Questions should be relevant to firmware/embedded systems interviews
- Include detailed answers that teach, not just test
- Coding questions should have starter code and test cases
- Difficulty ratings: **easy** (junior), **medium** (mid-level), **hard** (senior/principal)

## Self-Hosting the Compiler

For offline use or if you want faster compilation, self-host the Piston API:

```bash
docker run -d --name wandbox -p 3500:3500 melpon/wandbox
```

Then update the Wandbox API URL in `index.html` to point to your instance.

## Tech Stack

- **Frontend:** Vanilla HTML/CSS/JS (single file, no build step)
- **Editor:** [Monaco Editor](https://microsoft.github.io/monaco-editor/) (VS Code's editor component)
- **Compilation:** [Wandbox API](https://wandbox.org/) (free, open-source)
- **Hosting:** GitHub Pages (static, zero cost)

## License

MIT — use it, share it, improve it.

## Acknowledgments

Built for firmware engineers, by firmware engineers. If this helped you land a job, let us know! ⭐
