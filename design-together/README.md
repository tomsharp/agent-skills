# Design Together

Work through consequential software design decisions with a coding agent, one at a time. The agent explains its recommendation and the tradeoff, waits for your input, and keeps track of what you've agreed to. Those decisions can then carry into the implementation spec and tickets.

## Get started

1. [Download the skill ZIP](design-together.zip?raw=1) and extract it.
2. Add the extracted `design-together` folder to your coding agent's skills directory. If your agent doesn't support skills, give it [SKILL.md](SKILL.md) as context.
3. Start with a prompt like this:

   > Use $design-together to work through this system design with me, one decision at a time.

Give the agent the problem you're solving, any decisions you've already made, and relevant design docs or code. For example, if you're designing a background job, ask it to work through what the user sees while the job runs and what happens if it fails.
