# Git Commit Messaging Skill

This repository provides a standardized `SKILL.md` file designed to help AI coding assistants generate universally accepted, high-quality English Git commit messages. It is built to work seamlessly with cutting-edge 2026 AI coding platforms like **Antigravity**, **Cursor**, and **Claude Code**.

## What is this Skill?

The `SKILL.md` file acts as a structured prompt/instruction manual for AI agents. It teaches the AI to:
1. Extract your current Git branch name.
2. Analyze your staged/unstaged changes.
3. Classify the change type (`feat`, `fix`, `refactor`, etc.).
4. Formulate a concise, imperative description in English.
5. Output the result strictly as: `[branch-name] - [type] - [description]`.

---

## Integration & Usage Guide (2026)

Depending on which AI assistant you use, the way you integrate and trigger the `SKILL.md` file slightly differs.

### 1. Antigravity
Antigravity natively understands "Skills" as specialized folders of instructions that extend its baseline capabilities.

**How to Install:**
1. Create a `skills` directory under your project's agent folder (e.g., `_agents/skills/` or `.agents/skills/`).
2. Create a subfolder named `git-commit-messaging`.
3. Place the `SKILL.md` file inside so the path looks like this: `_agents/skills/git-commit-messaging/SKILL.md`.

**How to Use:**
When pair-programming with Antigravity, simply ask:
> *"Use the git-commit-messaging skill to write my commit message."*

Antigravity will automatically locate the skill file, read its YAML frontmatter, execute the necessary shell commands (`git branch`, `git diff`), and provide you the exact string to copy or commit immediately.

### 2. Cursor
Cursor relies heavily on project context and rules. By 2026, the standard for managing agentic rules in Cursor is the `.cursor/rules/` directory via `.mdc` file formats, but mentioning local files directly via `@` is equally effective.

**How to Install:**
*   **Option A (Recommended):** Copy the contents of `SKILL.md` into a new file located at `.cursor/rules/git-commit-messaging.mdc` in your project root. Cursor will automatically apply these rules whenever committing is discussed.
*   **Option B (File Reference):** Keep `SKILL.md` in your project root or a `docs/` folder. Add a line to your `.cursorrules` file pointing to it: `For git commits, always follow the rules in SKILL.md`.

**How to Use:**
Open Cursor Chat (`Cmd+L`) or Composer (`Cmd+I`) and type:
> *"@SKILL.md generate a commit message for my staged changes"*

Cursor will absorb the rules inside the file and output a perfectly formatted result.

### 3. Claude Code
Claude Code (Anthropic's terminal-based AI assistant) uniquely supports custom skills and slash commands, allowing you to invoke specific workflows effortlessly directly from your CLI.

**How to Install:**
1. In your project's root directory, create a `.claude` folder if it doesn't already exist.
2. Inside `.claude`, create a `skills` folder.
3. Create a folder for this skill named `git_commit_messaging` inside `skills`.
4. Place the `SKILL.md` file into this specific folder so the final path is: `.claude/skills/git_commit_messaging/SKILL.md`.

**How to Use:**
Open Claude Code in your terminal. You can now execute the skill directly by typing its slash command:
> `/git_commit_messaging`

Claude Code will automatically detect the skill, read its instructions, check your staged changes, and seamlessly generate an appropriate commit message.

---

## Example Expected Output

Regardless of the platform used, the AI will consistently give you an output like this:
`feature/user-profile - feat - add avatar upload functionality`

You can then copy this string, or if the AI is running in an autonomous terminal mode, you can allow it to execute the commit command directly: `git commit -m "..."`.
