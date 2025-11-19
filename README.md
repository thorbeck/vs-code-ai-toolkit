# VS Code AI Toolkit

This repository contains custom agents, prompt files, and configurations for GitHub Copilot in VS Code.

## Prompt Files

Reusable prompt templates for common TypeScript and web development tasks. Located in `.github/prompts/`.

### Available Prompts

- **api-endpoint.prompt.md** - Generate RESTful API endpoints with TypeScript types, validation, and error handling
- **fetch-client.prompt.md** - Create type-safe fetch API wrappers with proper error handling
- **code-review.prompt.md** - Comprehensive code review checklist covering types, security, performance, and best practices
- **typescript-types.prompt.md** - Generate TypeScript interfaces from JSON data or API responses
- **github-workflow.prompt.md** - Create GitHub Actions CI/CD workflow files

### How to Use Prompts

In VS Code Copilot Chat, reference a prompt file using `#file`:

```
#api-endpoint.prompt.md create a POST /api/users endpoint
```

Or use the file picker in chat:
1. Type `#` in the chat input
2. Select the prompt file
3. Add your specific request

Prompts provide consistent structure and ensure best practices are followed automatically.

## Custom Agents

### Plan Fast

A pragmatic planning agent that skips extensive research and gets straight to actionable implementation steps.

**Use this when:**
- You want to start coding quickly
- The requirements are relatively clear
- You prefer to iterate and refine as you go
- You're prototyping or exploring solutions

**Don't use this when:**
- The task is complex with many unknowns
- You need comprehensive analysis of trade-offs
- Multiple stakeholders need detailed documentation
- The project is mission-critical and requires thorough planning

#### How to Use

1. Open the Chat view in VS Code (`Ctrl+Alt+I`)
2. Select **Plan-Fast** from the agents dropdown
3. Enter your task or feature request
4. Review the quick plan
5. Use the "Start Implementation" handoff to begin coding

#### Key Differences from Default Plan Agent

| Feature | Plan Fast | Default Plan Agent |
|---------|-----------|-------------------|
| Research phase | Minimal | Comprehensive |
| Analysis depth | Quick assumptions | Thorough investigation |
| Plan length | Brief, actionable | Detailed, complete |
| Clarifying questions | Rare (only if blocking) | Frequent |
| Time to plan | ~1-2 minutes | ~5-10 minutes |
| Best for | Quick starts, prototypes | Complex features, team planning |

#### Example

**Input:** "Add dark mode toggle to the app"

**Plan Fast Output:**
```
Quick Summary: Add a dark mode toggle that switches between light and dark themes.

Implementation Steps:
1. Add theme state management (React context or Zustand store)
2. Create dark mode CSS variables in :root and [data-theme="dark"]
3. Build toggle component (moon/sun icon, stores preference)
4. Apply theme class to root element based on state
5. Persist theme preference to localStorage
6. Add tests for theme switching

Quick Notes:
- Use CSS custom properties for easy theme switching
- Default to system preference (prefers-color-scheme)
```

#### Customization

To customize the Plan Fast agent, edit `.github/agents/plan-fast.agent.md`:

- **Tools**: Add or remove tools like `fetch`, `githubRepo`, etc.
- **Model**: Change to a different language model
- **Instructions**: Modify the planning approach and output format
- **Handoffs**: Add custom handoff targets

## Installation

Custom agents and prompt files are automatically available in VS Code when you have this workspace open. VS Code detects:
- `.agent.md` files in the `.github/agents` folder
- `.prompt.md` files in the `.github/prompts` folder

## Contributing

Feel free to create additional prompts and agents for different workflows:

**Prompt Ideas:**
- Database migration generators
- React component scaffolding
- API documentation generation
- Security vulnerability scanning
- Performance optimization suggestions

**Agent Ideas:**
- Security review agents
- Documentation agents
- Testing agents
- Refactoring specialists

## Resources

- [VS Code Copilot Customization Overview](https://code.visualstudio.com/docs/copilot/copilot-customization)
- [VS Code Custom Agents Documentation](https://code.visualstudio.com/docs/copilot/customization/custom-agents)
- [VS Code Prompt Files Documentation](https://code.visualstudio.com/docs/copilot/customization/prompt-files)
- [VS Code Copilot Chat Documentation](https://code.visualstudio.com/docs/copilot/chat/copilot-chat)
- [GitHub Copilot Best Practices](https://github.blog/developer-skills/github/how-to-use-github-copilot-in-your-ide-tips-tricks-and-best-practices/)

