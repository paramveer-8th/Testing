Setup changes

Add the repo secret GEMINI_API_KEY. You can create the key in Google AI Studio.
Optionally add the repo variable GEMINI_MODEL. If you don’t set it, the workflow uses gemini-2.5-flash. Change it if you want a different or newer model.
ANTHROPIC_API_KEY and ANTHROPIC_MODEL are no longer used. JIRA_BASE_URL is still optional.

What changed in the call

The request goes to Gemini’s generateContent endpoint, with the key sent in the x-goog-api-key header.
The prompt rules go in system_instruction, and the diff and template go in the user message.
maxOutputTokens is 4096 because Gemini 2.5 models can count their internal “thinking” tokens against the limit. A lower value can cut the description short.
The text is read from candidates[0].content.parts. If Gemini returns no text, the step fails and leaves the PR description untouched.

The free tier of the Gemini API may use submitted prompts to improve Google’s products. If your code is private, check your key’s tier and your company policy before sending diffs.

Pr description
YML 

i can still see anthoripic key please check and give me latest fie

The saved file has no Anthropic references. A search for “anthropic” and “claude” in it returns nothing, so you were probably looking at the earlier download. The updated copy is in the chat sidebar and has the same path as before: .github/workflows/pr-description.yml.
