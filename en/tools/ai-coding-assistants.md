# AI coding assistants

AI coding assistants are programs that use large language models to
help you write, explain, and review code. Used well, they speed up
learning and reduce boilerplate; used blindly, they can produce
confident-looking mistakes. Treat them as a pair programmer, not an
oracle — read what they write and make sure you understand it.

## Claude

[**Claude**](https://claude.ai/) is Anthropic's assistant. You can
talk to it in the web app, through editor integrations, or via the
**Claude Code** CLI, which can read and edit files in your project
directory. It is a strong choice for step-by-step explanations and
for working through unfamiliar code.

## Codex

**Codex** is OpenAI's coding agent, available through tools like
ChatGPT, the OpenAI Codex CLI, and the GitHub Copilot family. It is
widely integrated into editors — the Copilot extension in VS Code
and the JetBrains plugin both ship with Codex-based completions and
chat.

## Gemini

[**Gemini**](https://gemini.google.com/) is Google's assistant.
**Gemini Code Assist** brings it into VS Code and JetBrains IDEs
with completions and chat, and the **Gemini CLI** runs in your
terminal for repo-aware tasks.

## How to use them while learning

- **Ask for explanations**, not just answers. "Why does this work?"
  and "What would break this?" teach more than a copied snippet.
- **Run the code yourself.** If an assistant writes code you do not
  understand, do not ship it.
- **Keep secrets out.** Do not paste passwords, API keys, or private
  data into a chat.
- **Cross-check.** When an assistant asserts a Django API exists,
  confirm in the
  [Django docs](https://docs.djangoproject.com/) before relying on
  it.
