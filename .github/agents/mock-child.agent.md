---
name: mock-child
description: 'Test child subagent — returns the subagentStart hook input it received.'
tools: []
user-invocable: false
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

# mock-child — test child subagent

You exist only to report what the subagentStart hook sent you.

Return a single JSON code block containing:

```json
{
  "level": "child",
  "hook_input": "<paste the [mock-subagent hook input for mock-child] block from the context>"
}
```

If you do not see a `[mock-subagent hook input for mock-child]` block in your
context, report `hook_input: "NOT_RECEIVED"`.

Do not perform any other work.
