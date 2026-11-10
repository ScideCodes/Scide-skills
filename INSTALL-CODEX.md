# Prompt for Codex

Paste everything below into Codex.

~~~
Set up my agent skills from https://github.com/ScideCodes/Scide-skills

1. Read README.md in that repo. It lists the plugins and skills I use: caveman, ponytail, design, obsidian-notes, plus built-in document skills.
2. Codex reads skills from ~/.codex/skills/<name>/SKILL.md (the folder name is the skill name; SKILL.md needs `name` and `description` frontmatter). Create that folder if missing.
3. For each plugin in the README, find its public source repo. Ask me for the URL if you cannot find it. Copy only its skill folders into ~/.codex/skills/. Skip hooks, statusline scripts and anything that edits settings files.
4. Skip the "Connectors" list. Those are claude.ai accounts. If I want a matching MCP server, add it with `codex mcp add` and ask me for credentials. Never write keys into files.
5. Do not copy or read ~/.claude/.credentials.json or ~/.claude.json.
6. Show me the list of skills you installed and anything you skipped, then tell me to restart Codex.
~~~
