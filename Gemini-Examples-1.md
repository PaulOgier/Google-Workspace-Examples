# Gemini Gmail prompts

## Simple Gemini Prompts (Drafting & Basic Refinement)
These focus on quick generation of an email draft or basic modification.

- New Draft	"Write a brief thank you email to Sarah for the product demo today."	Quick follow-up after a meeting or event.
- New Draft	"Draft a casual email asking my team for their availability for a project kickoff meeting next week."	Scheduling, asking for information.
- Reply	"Write a professional reply accepting the meeting invitation for Tuesday at 10 AM." (Use on a reply thread)	Simple confirmation/acceptance.
- Refine	[Write a rough, quick draft] then choose Formalize	Turning bullet points or casual notes into a polished, professional email.
- Refine	[Write a long draft] then choose Shorten	Condensing an email to be more scannable and respect the recipient's time.

## Advanced Gemini Prompts (Context & Tone)
These prompts leverage Gemini's ability to take on a persona, use specific context, and manage complex tone or constraints.

- Contextual Reply	"Reply to this client email. Acknowledge their frustration about the shipping delay, offer a 15% discount on their next order, and reassure them that the new delivery date of Friday is confirmed. Use an empathetic but professional tone."	Handles multiple, specific requirements and sets the tone. This is much faster than writing it yourself.
- Persona & Persuasion	"Draft a cold outreach email to a potential partner. Act as the VP of Business Development. Highlight our recent success with Company X and ask for a 15-minute call to discuss a similar partnership opportunity. Be direct and concise."	Gemini takes on a high-level persona and focuses on a specific persuasive goal (getting a short call).
- Synthesizing & Formatting	"Summarize the three key action items and their owners from the previous five emails in this thread into a bulleted list. The subject line should be 'Action Items: Project Alpha Next Steps'."	Synthesizes information from the entire thread and formats it for immediate clarity (bulleted list and specific subject line).

- "No" With Alternatives	"Write a polite but firm email declining the speaking invitation for the conference next month due to a scheduling conflict. Suggest my colleague, [Colleague Name], as a highly capable alternative, including a brief summary of their expertise in [Topic]."	A great way to say "no" while maintaining a positive relationship by providing a solution/alternative.
- Leveraging a Document	"Write an email to my manager outlining the budget changes for Q3, referencing the data points found in my 'Q3 Budget Spreadsheet' (tagging an @file from Drive). Focus on the increased marketing spend and the resulting projected ROI."	Uses data and context outside of Gmail (by tagging a Google Drive file) to write a data-rich, custom email.

### Tips for Writing the Best Prompts
Be Specific: Instead of "Write an email about the meeting," use "Write a follow-up email to the team confirming the details we discussed: Project A is now due Friday, and we need the report from Marketing by end of day Wednesday."
Set the Tone: Always specify the desired tone: Formal, Casual, Empathetic, Direct, Urgent but Polite, Enthusiastic, Professional.
Define the Output: Tell Gemini what you want the final email to look like: A brief paragraph, a bulleted list of 5 points, a two-sentence reply, etc.
