# Web App Tests Writer

| Skill | When to use it |
| --- | --- |
| [`browser-e2e-testing`](skills/browser-e2e-testing/SKILL.md) | Add end-to-end browser tests for a feature, audit coverage across routes and user journeys, or diagnose a failing or flaky browser test. |

The skill guides an agent through inspecting a web app, mapping and prioritizing coverage, writing resilient tests, maintaining existing coverage, and reporting what it verified. It uses the project's test framework and commands. The skill follows the [Agent Skills format](https://agentskills.io/specification) and has no runtime dependencies. Running browser tests requires the target project's usual dependencies and test environment.

## Install and invoke

Download and extract the repository from GitHub with **Code → Download ZIP**, or clone it with Git.

```text
git clone https://github.com/haopeng-wu/web-app-tests-writer.git
```

### Native skill discovery

Copy the entire `skills/browser-e2e-testing` folder into the location for your agent. Project paths below are relative to the **web app's repository root**. Create the destination parent directory if needed. These paths work on macOS, Linux, and Windows in the filesystem where the agent runs. For a WSL or remote session, copy into that session's project checkout.

| Agent | Copy into | Invoke in the agent | Verification status |
| --- | --- | --- | --- |
| Codex CLI | `.agents/skills/` | Open `/skills` or type `$` in a prompt and select `browser-e2e-testing`. | Tested for project discovery with Codex CLI 0.155.1 on macOS. [OpenAI skill guidance](https://learn.chatgpt.com/docs/build-skills) |
| Claude Code | `.claude/skills/` | Type `/browser-e2e-testing` followed by your task. | Documented by Anthropic. Hands-on verification pending. [Claude Code skill guidance](https://code.claude.com/docs/en/skills) |
| GitHub Copilot in VS Code | `.github/skills/` | Open Copilot Chat, type `/`, and select `browser-e2e-testing`. | Documented by Microsoft. Hands-on verification pending. [VS Code skill guidance](https://code.visualstudio.com/docs/agent-customization/agent-skills) |

After copying, the path in the app repository should end in `skills/browser-e2e-testing/SKILL.md`. Keep a single installed copy for each agent to make updates predictable. To update, replace that copy with the newer skill folder.

The Codex check verified local discovery. Invocation and the Linux and Windows setups are documented paths.

### Manual Markdown fallback

Give your agent access to [`SKILL.md`](skills/browser-e2e-testing/SKILL.md) and ask it to read and follow the file for the current task. Attach the file or paste its contents if the agent cannot read the checkout. This is a manual setup that relies on the agent's ability to read supplied Markdown.

### Quick check

Open a fresh session in your web app's checkout. Confirm the skill appears in the native picker or slash menu, then select it and give it this read-only task. For the manual fallback, provide the file and explicitly ask the agent to follow it before giving the same task.

> Review browser coverage for one critical journey. Point to the relevant routes and existing specs, distinguish page smoke checks from complete journey coverage, and identify the highest-priority gap. Keep this review read-only.

Confirm that the agent refers to actual project files, explains what the existing tests assert, and reports any checks it could not run.

## Contribute

Open an issue with a reproducible workflow gap or a pull request that updates the shared [`SKILL.md`](skills/browser-e2e-testing/SKILL.md). Include the request you tested, the expected behavior, what happened, and the agent and operating system used. Check changes against the [Agent Skills specification](https://agentskills.io/specification). Verify installation changes against the tool's official docs and distinguish documentation checks from hands-on tests. Keep tool-specific metadata beside the skill and keep workflow instructions in the shared file.

## License

The [MIT License](LICENSE) permits commercial use and requires retaining the copyright and license notices in copies or substantial portions of the work.
