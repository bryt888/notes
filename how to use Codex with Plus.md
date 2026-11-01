A Beginner's Guide to OpenAI Codex

How to code effectively without wasting your usage allowance

Codex is an AI coding assistant included with your ChatGPT Plus subscription ($20/month). It can help you create applications, write Python programs, build websites, debug code, and work on existing projects.

The most important thing to understand is that different AI models consume your usage allowance at different rates. You should choose the right model for each task rather than always using the most powerful one.

1. Choosing the Right AI Model

Capability| GPT-6 Luna| GPT-6.1 Terra| GPT-6.1 Sol| GPT-6 Astra
Simple code changes| Excellent| Excellent| Excellent| Excellent
Python scripting| Good| Very good| Excellent| Excellent
Website development| Good| Very good| Excellent| Excellent
Multi-file projects| Basic| Good| Excellent| Excellent
Complex debugging| Moderate| Good| Excellent| Best
Large project architecture| Limited| Moderate| Very good| Best
GUI / computer automation| Good| Excellent| Excellent| Excellent
Relative API cost| 1×| 10×| 20×| 100×

Recommended usage:

- Luna: Simple scripts, explaining code, fixing small bugs, and repetitive tasks.
- Terra: Everyday development, small applications, UI changes, and computer automation.
- Sol: More complex programming, multi-file projects, difficult debugging, and application development.
- Astra: Very difficult problems, complex architecture, and tasks that other models cannot solve.

My recommendation: Start with Luna or Terra. Move to Sol when the task becomes more difficult. Reserve Astra for particularly challenging problems.

2. Understanding Usage Limits

Your Plus subscription includes Codex usage, but it is not unlimited.

Approximate local-message ranges within a five-hour usage window:

Model| Estimated messages
GPT-6 Luna| 350–3,000
GPT-6.1 Terra| 35–285
GPT-6.1 Sol| 15–160
GPT-6 Astra| 5–45

These are estimates, not guaranteed message counts or separate allowances. Actual consumption depends on task complexity, conversation length, model settings, and tools used. Weekly limits may also apply.

Important tips:

- Use simpler models for straightforward tasks.
- Start with Low or Medium reasoning. Use High only when necessary.
- Avoid repeatedly asking expensive models to perform simple changes.
- Long conversations consume more context and can increase usage.
- Check Settings → Usage regularly.
- Fast and Ultrafast modes can consume your allowance significantly faster.

API token prices are separate from the Plus subscription. You do not pay those API prices per message when using Codex through your included ChatGPT subscription, but expensive models generally use your allowance faster.

3. Where to Use Codex

Codex Windows Desktop App

Recommended for beginners who want to build applications locally. It can work with project files, modify code, execute commands, run tests, and help manage multiple development tasks.

VS Code + Codex Extension

Recommended when you want to edit code yourself while receiving AI assistance. It is especially useful for Python, JavaScript, and web development.

Codex CLI

A terminal-based interface for users comfortable with command-line tools.

Codex Web

Useful for cloud-based development and GitHub-connected projects.

For your first projects, I recommend starting with the Windows desktop app.

4. Managing Project Instructions with AGENTS.md

Codex uses a file called "AGENTS.md", similar to "CLAUDE.md" in Claude Code.

Place it in your project's root directory:

my-project/
├── AGENTS.md
├── src/
├── tests/
└── README.md

Example "AGENTS.md":

# Project Instructions

- Use Python 3.12.
- Keep the code simple and readable.
- Follow the existing project structure.
- Do not remove existing features.
- Run tests after making changes.
- Explain major modifications.
- Ask before installing dependencies.
- Prefer small, incremental changes.

Codex reads these instructions when working on the project, helping maintain consistency across different conversations.

You can also use "/init" to generate an initial "AGENTS.md" file.

5. Managing Conversation Context

Long conversations can consume more tokens and reduce efficiency.

Useful Codex commands include:

Command| Purpose
"/status"| Check session information and usage
"/compact"| Summarize conversation history to reduce context
"/clear"| Start a fresh conversation in supported CLI versions
"/model"| Change models in Codex CLI
"/init"| Generate project instructions

Commands and their availability vary between the desktop app, CLI, and VS Code extension.

Best practices:

- Start a new conversation when switching to a different task.
- Use context compaction when a conversation becomes too long.
- Keep important project rules in "AGENTS.md", not only in chat history.
- Remember that starting a new conversation does not reset your usage allowance.

6. A Simple Workflow

For example, suppose you want to build a small Python application.

Step 1 — Plan with Luna

Ask Codex to explain the project structure and propose a simple implementation.

Step 2 — Implement with Terra or Sol

Ask it to create the application, implement features, and run tests.

Step 3 — Make small changes with Luna

Use the cheaper model to change text, adjust layouts, add comments, or make minor improvements.

Step 4 — Debug with Sol

If the application has a difficult bug, switch to Sol and provide the error messages.

Step 5 — Use Astra only if necessary

For particularly difficult architectural problems or unresolved bugs, consider Astra.

Always review code changes and test the application before accepting major modifications.

---

Final Advice

Think of Codex as a team of AI developers with different skill levels and costs.

You don't need the most expensive developer for every task.

Start small, choose the appropriate model, keep your project instructions organized, and monitor your usage.

With good habits, your ChatGPT Plus subscription can support meaningful programming projects without unnecessarily exhausting your allowance.

Official Resources

- "Codex" (https://chatgpt.com/codex)
- "Codex Documentation" (https://developers.openai.com/codex/)
- "Models and Pricing" (https://developers.openai.com/api/docs/models)
- "ChatGPT and Codex Usage" (https://chatgpt.com/settings/usage)
