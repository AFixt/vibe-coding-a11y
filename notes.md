# Notes

## My history with AI coding

* Early user of ChatGPT when v4 came out
* Early experiment with ChatGPT & remediation [https://karlgroves.com/chatgpt-is-not-ready-to-handle-web-accessibility-remediation/]
* Generally left unimpressed by AI-based testing, auditing, and remediation
* Started using ChatGPT for small one-off tasks, like generating code samples, help with debugging. Generally it proved itself very useful in these areas.
* Larger efforts with ChatGPT proved it to be frustratingly bad at larger tasks due to memory limitations.
* Met someone in the UK during a conference who showed me a game he developed with Claude Code. Claimed he just pointed Claude at a repo, told it what to do, and generated the game wholly unattended.  Decided to give it a try
* Generally impressed with Claude Code, which I use on a daily basis and have built a large number of things with it.
* I still do not believe that it is possible to leave an AI coding product unattended and come back to a high quality finished product ready to deploy. If anything, that strategy is doomed to fail.

## Coding tools used

| Name | URL |
| ----- | ----- |
| ChatGPT/ Codex | <https://chatgpt.com/codex> |
| Cursor | <https://cursor.com/> |
| Base44 | <https://base44.com/> |
| Claude Code | <https://claude.com/product/claude-code> |
| Github Co-Pilot | <https://github.com/copilot> |
| Gemini Code Assist | <https://codeassist.google/> |
| Windsurf | <https://windsurf.com/> |
| Devin | <https://devin.ai/> |
| Replit | <https://replit.com/> |
| Bolt | <https://bolt.new/> |
| Lovable | <https://lovable.dev/> |
| Amazon Nova | <https://nova.amazon.com/> |

## The task

* Use each major AI coding tool to create an online pizza ordering form
* Two prompts: 1 explicitly mentioning accessibility and one that doesn't.
* Run the "no accessibility prompt" first.
* Do the two prompts as separate sessions after clearing cookies, browser cache, etc.
* The output will be a "one shot" - no reprompting for clean-up. Follow-up questions presented by the chatbot will be answered honestly (none asked any follow-up questions)
* Each one will be subjected to automated and manual testing.

## Initial thoughts

* In general, the results are well known in advance: if you don't prompt for it, you won't get it.  In other words, a user that doesn't specify a requirement should not expect that the requirement will be fulfilled. So, while it would be nice to expect that a coding tool will generate perfectly accessible output, not specifying that it do so is akin to being willing to accept whatever it comes back with.
* Some may argue that the big AI companies already build in other guardrails (safety, ethics, etc.), so it is reasonable to expect that it build in accessibility. I agree with this completely. I'm merely saying that the current state of things is that, like dealing with human developers, we should not assume the AI will read our minds.
* Given the above, what we should be surprised by are two things: first, if the "no-a11y" prompt results are accessible and, second, if the a11y prompt is not.
* I am concerned that the results may be skewed by my personal profile contributing to the decisions made in ChatGPT and Claude

## The results

### Prompt 1

* [Amazon Nova](src/prompt1/amazon-nova/index.html)
* [ChatGPT/ Codex](src/prompt1/chatgpt-codex/index.html)
* [Cursor](src/prompt1/cursor/index.html)
* [Base44](https://quixotic-pizza-perfect-order.base44.app)
* [Claude Code](src/prompt1/claude-code/index.html)
* [Github Co-Pilot](src/prompt1/github-copilot/index.html)
* [Windsurf](src/prompt1/windsurf/index.html)
* [Devin](src/prompt1/devin/index.html)
* [Lovable](https://cheesy-dreams-form.lovable.app)

### Prompt 2

* [Amazon Nova](src/prompt2/amazon-nova/index.html)
* [ChatGPT/ Codex](src/prompt2/chatgpt-codex/index.html)
* [Cursor](src/prompt2/cursor/index.html)
* [Base44](https://utopian-pizza-palace-order.base44.app)
* [Claude Code](src/prompt2/claude-code/index.html)
* [Github Co-Pilot](src/prompt2/github-copilot/index.html)
* [Windsurf](src/prompt2/windsurf/index.html)
* [Devin](src/prompt2/devin/index.html)
* [Lovable](https://pizza-pie-maker.lovable.app)
