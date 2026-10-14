# Startup Ignition ToolSuite MCP server

A remote [Model Context Protocol](https://modelcontextprotocol.io) server that connects AI assistants to a user's [Startup Ignition ToolSuite](https://www.startupignition.com/toolsuite/) account. ToolSuite is a startup idea validation platform used by founders, accelerators and university entrepreneurship programs.

This repository holds the registry metadata and documentation. The server itself is hosted by Startup Ignition.

| | |
|---|---|
| Server address | `https://mcp.startupignition.com/mcp` |
| Transport | Streamable HTTP |
| Authentication | OAuth 2.1 with PKCE (dynamic client registration and client ID metadata documents supported) |
| Registry name | `com.startupignition/toolsuite` |
| Setup guide | https://www.startupignition.com/toolsuite/connect/ |

## What it does

With a user's permission the connector lets an assistant:

- **Read** everything on the user's idea pages: idea analysis, Big Idea Canvas, business model canvas, customer personas, riskiest assumptions, interview scripts, interview findings (participants' identities removed), mentor conversations and version history.
- **Run** the Startup Ignition validation steps: Idea Analysis, Big Idea Canvas, Business Model Canvas, Identify Assumptions, Interview Scripts, Wow! Factor Analysis, Market Research and Founder-Idea Fit, and ask the Startup Ignition mentor a question.
- **Edit** canvas answers, canvas items, assumptions, personas, journey steps and storyboards. Every edit is recorded in the idea's history and can be undone.
- **Export** any tool page as a PDF or a picture.

62 tools in all. Every tool carries a `title` and a `readOnlyHint` or `destructiveHint` annotation. Run tools spend the workspace's ToolSuite credits within a daily limit the user sets when connecting; the connector never sells credits or links to billing.

## How to configure

1. Add the server to your client. In VS Code: Command Palette → **MCP: Add Server** → **HTTP** → `https://mcp.startupignition.com/mcp`. Other clients are covered step by step in the [setup guide](https://www.startupignition.com/toolsuite/connect/).
2. Start the server. Your browser opens the ToolSuite sign-in page.
3. Sign in, choose the workspaces the assistant may use, the permissions (read, run tools, edit) and a daily usage limit, and click **Approve**.

No API key or client secret is needed. A ToolSuite account is required; free accounts can connect.

## How to use

Ask the assistant about your ideas by name:

- "Give me an overview of my idea in ToolSuite and what to do next."
- "Identify the riskiest assumptions behind my idea and draft the interview scripts."
- "Ask the Startup Ignition mentor which customer segment I should interview first."
- "Show me my business model canvas as a picture."
- "What did the customer interviews say about pricing?"

## Disconnecting and privacy

Disconnect at any time in ToolSuite under **Settings → AI assistants & MCP**. Changing your password disconnects every app. Interview participants' names, contact details and interview links are never passed to the assistant.

Privacy policy: https://www.startupignition.com/privacy/ · Terms: https://www.startupignition.com/terms/ · Support: toolsuite@startupignition.com
