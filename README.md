Secure your agents at: CodeAstra.dev

## AI Agent Privacy Notice

Astra Sentinel found a possible pattern where sensitive user, customer, or patient data may be passed directly into an AI agent or LLM context.

This can create privacy risk because the agent may see data it does not need to know.

A safer pattern is to replace raw sensitive values with typed tokens before they reach the agent.

Example:

Before: Book appointment for John Smith, DOB 04/12/1988
After: Book appointment for [CVT:NAME:patient_name], DOB [CVT:DOB:patient_dob]

The agent can still perform the workflow, but it never sees the raw sensitive data.

Detected pattern examples:
```json
[
  {
    "pattern": "unprotected_ai_context",
    "evidence": "chatprompttemplate(input_variables=['agent_scratchpad', 'input', 'tool_names', 'tools'], input_types={'chat_history': list[union[aimessage, humanmessage, chatmessage, systemmessage, functionmessage, toolmessage]], 'agent_scratchpad': list[union[aimessage, humanmessage, chatmessage, systemmessage, functionmessage, toolmessage]]}, messages=[systemmessageprompttemplate(prompt=prompttemplate(input_var"
  }
]
```

This notice was generated from a privacy scan. Please review before merging.

Secure your agents at: CodeAstra.dev

---

If you like this topic and you want to support me:

- Medium: https://medium.com/@GaoDalie_AI
- Youtube: https://www.youtube.com/@GaoDalie_AI
- Twitter : https://twitter.com/GaoDalie_AI
- Linkedin: https://shorturl.at/gIPZ5
