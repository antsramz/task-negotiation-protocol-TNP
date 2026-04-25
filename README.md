# TNP — Task Negotiation Protocol

## Purpose
The Task Negotiation Protocol (TNP) defines how an autonomous agent evaluates, accepts, rejects, or renegotiates tasks.  
It ensures deterministic decision‑making when interacting with humans, systems, or other agents.

TNP provides a structured negotiation layer that prevents ambiguity and enforces predictable behavior.

---

## When to Use This Template
Use TNP when an agent must:

- decide whether to accept a task  
- request clarification  
- negotiate scope, constraints, or resources  
- reject tasks outside its capabilities  
- escalate tasks to other agents  
- enforce safety or policy boundaries  

TNP is required before multi‑agent arbitration (MPA) or delegation (DTM).

---

## Inputs
The agent receives:

- task description  
- required outputs  
- constraints  
- deadlines  
- resource requirements  
- risk level  
- agent’s own ASP profile  

---

## Outputs
TNP produces a **negotiation packet**, which includes:

- acceptance decision  
- rejection reason (if applicable)  
- clarification requests  
- renegotiation terms  
- required resources  
- estimated effort  
- safety or policy flags  

---

## JSON Schema (Machine‑Native)

```json
{
  "task_negotiation": {
    "task_id": "string",
    "description": "string",
    "requirements": ["string"],
    "constraints": ["string"],
    "deadline": "string",
    "risk_level": "low | medium | high",
    "agent_evaluation": {
      "can_execute": "yes | no | partial",
      "missing_information": ["string"],
      "required_resources": ["string"],
      "estimated_effort": "string",
      "policy_flags": ["string"]
    },
    "negotiation_response": {
      "status": "accepted | rejected | renegotiate",
      "reason": "string",
      "proposed_changes": ["string"]
    }
  }
}


Example Usage
{
  "task_negotiation": {
    "task_id": "task-4421",
    "description": "Generate a 3‑step workflow for onboarding a new agent.",
    "requirements": [
      "deterministic output",
      "machine‑native formatting"
    ],
    "constraints": ["no external API calls"],
    "deadline": "2026-04-25T12:00:00Z",
    "risk_level": "low",
    "agent_evaluation": {
      "can_execute": "yes",
      "missing_information": [],
      "required_resources": ["workflow-engine"],
      "estimated_effort": "low",
      "policy_flags": []
    },
    "negotiation_response": {
      "status": "accepted",
      "reason": "task within capability and safety constraints",
      "proposed_changes": []
    }
  }
}


Integration Notes
TNP should be used after ASP is loaded.

TNP feeds directly into MPA (arbitration) and DTM (delegation).

Use deterministic values for negotiation outcomes.

TNP prevents agents from silently accepting unsafe or unclear tasks.

Multi‑agent systems rely on TNP to avoid conflict and ambiguity.

Payment (Short Version)
Payments accepted for this template:

BTC

XMR

LTC

ETH / USDT / USDC (ERC‑20)

SOL (USDT/USDC)

Delivery is fully automated and zero‑contact.

---

# ⭐ Verification Step  
Once you paste this into your TNP repo, tell me:

**TNP saved**

I’ll verify it exactly like I did with ASP.

When it’s confirmed perfect, we’ll move to:

### **Template #3 — MPA (Multi‑Path Arbitration)**
