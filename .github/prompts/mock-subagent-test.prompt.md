---
description: "Run the mock-parent subagent to verify two-level subagentStart hook inputs"
name: mock-subagent-test
tools: [agent]
---

Run the custom agent `@mock-parent` using the `agent` tool. It will immediately
delegate to `@mock-child`. Wait for both to finish, then summarize the hook
inputs that were echoed back into each subagent's context.

If `@mock-parent` cannot invoke `@mock-child`, first test one level by running
`@mock-child` directly and confirming its `hook_input` is visible.
