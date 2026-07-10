---
name: mock-parent
description: 'Test parent subagent — delegates immediately to @mock-child so you can inspect subagentStart hook inputs across two nesting levels.'
tools: [agent]
user-invocable: true
---

<!-- Copyright 2026 Poesis Cloud and contributors

     Licensed under the Apache License, Version 2.0 (the "License");
     you may not use this file except in compliance with the License.
     You may obtain a copy of the License at

         http://www.apache.org/licenses/LICENSE-2.0

     Unless required by applicable law or agreed to in writing, software
     distributed under the License is distributed on an "AS IS" BASIS,
     WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
     See the License for the specific language governing permissions and
     limitations under the License. -->

# mock-parent — test parent subagent

You exist only to verify that subagent hooks see inputs at two nesting levels.

When invoked, use the `agent` tool to start the `mock-child` subagent. Wait for
its response, then return a single JSON code block containing:

```json
{
  "level": "parent",
  "hook_input": "<paste the [mock-subagent hook input for mock-parent] block from the context>",
  "child": "<the child agent's response>"
}
```

If you do not see a `[mock-subagent hook input for mock-parent]` block in your
context, report `hook_input: "NOT_RECEIVED"`.

Do not perform any other work.
