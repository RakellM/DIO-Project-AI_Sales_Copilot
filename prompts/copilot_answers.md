# Copilot Answers Prompt - How to Query the AI

## Purpose
This document shows sales reps how to query the AI copilot for ANY customer interaction.

## Query Format

Always query the AI copilot using this simple format:

```text
Customer: [paste what the customer said]
Context: [optional - delivery date, order history, location]
Help me respond.
```


## Examples

### Example 1 - Winter Delivery
Query:

```text
Customer: "I'm in Barrie. It's February. How do I know my food won't freeze on my porch?"
Context: First-time customer, no subscription yet.
Help me respond.
```


### Example 2 - GLP-1 Nausea
Query:

```text
Customer: "I started Ozempic 2 weeks ago and I'm so nauseous. Will your meals make it worse?"
Context: Hamilton location, heard about us from doctor.
Help me respond.
```


### Example 3 - Price Objection
Query:

```text
Customer: "$14 for lunch? No thanks. I can get Tim Hortons for $6."
Context: Downtown Toronto, professional, first time.
Help me respond.
```


### Example 4 - Quebec Launch
Query:

```text
Customer: "Bonjour! Je suis à Montréal. Quand lancez-vous?"
Context: Quebec customer, French preferred.
Help me respond.
```


### Example 5 - Existing Customer Issue
Query:

```text
Customer: "My delivery was supposed to come at 12pm. It's now 2pm. Snowstorm in Toronto."
Context: Existing subscriber, 10 meals/week, third delivery.
Help me respond.
```



## Expected Output Format

The AI will always respond with three sections:

**SUGGESTED RESPONSE** - Copy-paste this to the customer
**INTERNAL NOTES** - For you only (persona, strategy, next steps)
**FOLLOW-UP QUESTION** - Open-ended question to ask the customer

## Pro Tips

1. Always include location - Canadian context matters (Barrie vs Toronto vs Montreal)
2. Mention if it's winter (November-March) - triggers weather protocol
3. Note if customer mentioned GLP-1, Ozempic, or nausea - triggers medical sensitivity protocol
4. For Quebec customers, mention French language preference if known
5. Include order history if available (first time vs returning vs subscription)

## What NOT to Do

❌ Don't ask the AI "Should I give a refund?" - use the escalation triggers in [agents.md](../agents.md)
❌ Don't ask for medical advice beyond what's in the knowledge base
❌ Don't ask about legal issues - escalate to manager
❌ Don't ask about Quebec delivery boundaries before Sept 15, 2026 - use waitlist protocol

