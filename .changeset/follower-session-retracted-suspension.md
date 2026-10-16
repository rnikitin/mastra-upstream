---
'@mastra/core': patch
---

Fixed a Session that follows a thread keeping a parked tool call after the run was aborted on another instance, or after the resumed run ended with a non-success finish such as `content-filter`. The follower now retracts the call with `tool_suspension_cancelled`, so `suspensions.hasPending()` returns false ([#26997](https://github.com/mastra-ai/mastra/issues/26997)).
