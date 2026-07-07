---
type: workflow
code: WF-011
tags: [workflow, whatsapp, teams, messaging, communication, meeting]
updated: 2026-05-18
---
# WF-011 — Generate Post-Meeting Instant Messaging Message

> **Typical invocation:** *"Make me a message for the WhatsApp group"* · *"Make me a message for the Teams channel"* · *"Draft the message with the agreements for Teams"* · *"Generate the summary to share on WhatsApp"*

---

## When to use this workflow

After any meeting where decisions, agreements, or actionables need to be communicated to a broader group or to participants via instant messaging. Especially applies when:

- The meeting made decisions that affect people who were not present.
- There are actionables with an owner and deadline that should be documented in a team channel.
- The PM wants to leave a quick record without waiting for everyone to read the minutes.

---

## Step 0 — Identify the target platform

**Ask or infer from context:** is the message going to WhatsApp or Teams?

| Signal | Inferred platform |
|---|---|
| "WhatsApp group", "the group", mentions WA group name | WhatsApp |
| "Teams channel", "the channel", "Teams", project managed in Teams | Teams |
| Not specified | Ask before drafting |

The platform determines the format (see Step 2). The content and structure are identical.

---

## Step 1 — Source of information

The message is generated from **one of these inputs** (in order of preference):

1. The already processed minutes from the vault (WF-001 completed).
2. The meeting transcription, if the minutes do not yet exist.
3. Verbal description from the PM in the Cowork chat.

If the minutes already exist, read them before drafting. Do not invent agreements.

---

## Step 2 — Identify key content

Extract from the source:

| Element | Inclusion criteria |
|---|---|
| **Main decision** | The most important resolution from the meeting — the one that changes something concrete |
| **Secondary agreements** | Conditions, limits, or exceptions agreed upon |
| **Actionables** | Only those with a clear owner and deadline; omit vague ones |
| **Next collective step** | Future meeting, start date, next milestone |

**Always omit:** internal debate, deep technical context, names of people not relevant to the receiving group, sensitive payroll or disciplinary information.

---

## Step 3 — Draft the message

### Fixed structure (same for both platforms)

```
👋 [Audience/context — e.g., "Team — summary of today's checkpoint:"]

✅ [Main agreement title:]  [One sentence. Concrete and unambiguous.]

📋 Agreements:
• [Agreement 1]
• [Agreement 2]
• [Agreement 3]

⚡ Immediate pending items:
• [Name] → [concrete action] [date if applicable]
• [Name] → [concrete action]

[One-line warm closing. Optional.]
```

### Format by platform

| Rule | WhatsApp | Teams |
|---|---|---|
| **Bold** | `*text*` (single asterisk) | No bold — plain text. Teams does not reliably render markdown in chat. |
| **Headers** | Do not use — emojis as separators | Do not use — emojis as separators |
| **Lists** | `•` with space | `•` with space |
| **Names in actionables** | `*Name*` (with asterisk) | `Name` (no formatting, just text) |
| **Length** | max 200–250 words | max 200–250 words |
| **Tone** | direct and warm, team language | direct and warm, team language |
| **Action date** | only if today or tomorrow; if far away, omit | only if today or tomorrow; if far away, omit |

> ⚠️ **Critical rule — Teams:** Teams does not reliably render Markdown in chat. If text with `*asterisks*` or `**double**` is pasted, they appear literally on screen. The Teams message must be **plain text + emojis**. No Markdown or WhatsApp-style formatting.

### Standard emojis (work on both platforms)

| Emoji | Use |
|---|---|
| 👋 | Opening / greeting |
| ✅ | Main decision made |
| 📋 | Agreements / context section |
| ⚡ | Pending / urgent actionables |
| 📅 | Date or next meeting |
| 🚀 | Positive closing / call to action |
| ⚠️ | Alert or risk the group should know |

---

## Step 4 — Adjust to the receiving group

The tone and detail level vary depending on the audience:

| Group | Adjustment |
|---|---|
| **Operational team** (managers, agents) | Focus on what changes for them, when, and what they must do. No project jargon. |
| **Technical team** (IT, development) | May include brief technical context. Actionables with technical specificity. |
| **Management / sponsors** | Only decision + impact + next step. Max 5 lines. |
| **Mixed group** | Use the simplest level. If there are differentiated actionables, group them by area. |

---

## Step 5 — Deliverable

Claude always produces the message **inside a code block** (triple backtick), never as inline text in the response.

> ⚠️ **Critical delivery rule:** The code block preserves the text exactly as it should be pasted — including asterisks for WhatsApp or clean text for Teams. If delivered outside the block, Claude may render the formatting and the user loses characters when copying. **Always use ` ``` ` as container.**

If the PM requests adjustments in tone, length, or recipient, apply them without redoing everything — and keep the code block in the adjusted delivery.

---

## Relationship with other workflows

- **WF-001** generates the minutes; WF-011 generates the informal communication of the same event.
- The instant messaging message **does not replace** the minutes — it is an additional communication layer.
- The actionables in the message must be consistent with those in the minutes. If there is a contradiction, the minutes are the source of truth.

---

## Reference examples

### WhatsApp example

> **Invocation:** *"Make me a message for the WhatsApp group with today's agreements"*

```
👋 *Team — summary of today's checkpoint:*

✅ *Decision made:* The pilot group starts remote work from home *tomorrow Tuesday, April 21.*

📋 *Agreements:*
• The cell structure remains the same until the end of April.
• The pilot manager team has technical support priority. Report any issues immediately.

⚡ *Immediate pending:*
• *Andres* → sends all program documentation to the team today before end of day.
• *Elena Torres* → coordinates with IT the support protocol for the remote team.
• *Everyone* → meeting today at 3:00 PM to finalize the operational procedure.

Any questions, let me know. Let's get to work! 🚀
```

### Teams example

> **Invocation:** *"Make me a message for the Teams channel with today's agreements"*

```
👋 Team — summary of today's checkpoint:

✅ Decision made: The pilot group starts remote work from home tomorrow Tuesday, April 21.

📋 Agreements:
• The cell structure remains the same until the end of April.
• The pilot manager team has technical support priority. Report any issues immediately.

⚡ Immediate pending:
• Andres → sends all program documentation to the team today before end of day.
• Elena Torres → coordinates with IT the support protocol for the remote team.
• Everyone → meeting today at 3:00 PM to finalize the operational procedure.

Any questions, let me know. Let's get to work! 🚀
```

---

*Meridian Group Vault · WF-011 updated 2026-05-18 — Expanded to instant messaging (WhatsApp + Teams)*
