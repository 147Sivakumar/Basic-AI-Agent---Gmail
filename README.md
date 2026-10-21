# Basic AI Agent – Gmail

An AI-powered Gmail assistant built with **n8n**. This workflow lets a user interact with an AI Agent through the n8n chat trigger. The agent uses a chat model and memory, and can perform a Gmail action such as sending an email.

## Workflow Overview

The workflow shown in the attached screenshot contains these nodes:

- **When chat message received** — starts a run when a user submits a message in the chat.
- **Perception (AI Agent)** — interprets the user's request and coordinates the connected model, memory, and tool.
- **BRAIN (Chat Model)** — provides the language-model capability used by the agent.
- **Simple Memory** — supplies conversational context during the interaction.
- **Action (Gmail: send message)** — sends an email using the configured Gmail connection.

### Workflow Diagram

```text
When chat message received
          |
          v
   Perception (AI Agent)
      /      |       \
     v       v        v
   BRAIN   Simple    Action
 (Chat      Memory   (Gmail:
  Model)             Send Message)
```

## Example Demonstration

In the screenshot, the chat asks the agent to send a birthday email. The execution log shows a successful Gmail send action, with the subject **“Happy Birthday, Siva!”** and a message addressed to the configured recipient.

This is an example of an agent using a natural-language request to trigger an email action. The exact recipient and message depend on the prompt and the workflow's Gmail configuration.

## Requirements

- An n8n instance
- A compatible chat model and its required credentials
- Gmail credentials configured in n8n
- The Gmail action configured with the intended recipient/message fields

## Setup

1. Open n8n and create a workflow, or import the exported workflow JSON if available.
2. Configure the **When chat message received** trigger.
3. Connect the **Perception** AI Agent to the **BRAIN** chat model.
4. Connect **Simple Memory** to the agent if conversational context is required.
5. Configure the Gmail **Action** node to send a message.
6. Add credentials through n8n's credential manager.
7. Test with a safe recipient and verify the execution log and Gmail inbox/sent folder.

## Run the Workflow

1. Open the workflow in n8n.
2. Start a chat session using the chat trigger.
3. Enter a clear request, for example: `Send an email with the subject "Project Update" and message "The workflow test was successful." to my own email address.`
4. Review the intended recipient, subject, and message before testing any real send action.
5. Execute the workflow and confirm the Gmail action succeeded.

## Project Files

```text
Basic-AI-Agent-Gmail/
├── README.md
├── Basic AI Agent – Gmail.json   # Export from n8n and add here
└── screenshots/
    └── workflow-execution.png
```

> The workflow JSON should be exported from your actual n8n workflow. It is not generated from the screenshot. Before sharing it, check that it does not expose credentials, tokens, or private email content.

## Security Notes

- Use n8n's credential manager; do not hardcode passwords, OAuth tokens, or API keys.
- Keep personal email addresses and private email content out of public screenshots where possible.
- Test email-sending actions with an address you control before using them for important messages.

## Result

The screenshot documents a successful execution of the Gmail send action. This project demonstrates a basic AI Agent workflow with a chat trigger, language model, memory, and a Gmail tool.

## Author

**Project:** Basic AI Agent – Gmail  
**Platform:** n8n  
**Integrations:** Gmail and a compatible chat model
