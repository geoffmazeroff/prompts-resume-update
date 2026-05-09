# Description
This repository contains skills you can use with an LLM tool to refresh an existing resume.

Although this has practical uses (i.e., updating my own resume), I approached it from a context engineering viewpoint where I start with a plan and have separate prompts for implementing that plan in small, focused steps that feed into one another. 

The skills can be combined into an agent, however I prefer to be more hands-on because the inputs usually need massaging before I can hand them off to AI.

# How to use
## Fresh start
The `plan-resume-update` skill led to the creation of the other skills in this repo. Review, revise, and invoke that skill to build out other skills as needed. I recommend a higher-thinking model for this step.

## Follow my process
You can also use the skills I've provided here. I've had success using a higher-thinking model for defining objectives, and a slightly less capable model for writing copy based on the objective statement.

_Tip: Clear the context window before invoking the next skill._

1. `define-resume-objectives`
2. `collect-integrate-new-accomplishments`
3. `rewrite-experience-sections`
4. `revise-skills-section`
5. `revise-tagline-summary-key-strengths`
6. `recommend-resume-format`
7. `recommend-linkedin-content`

# Other considerations
- The prompts were specific to my use case (i.e., my resume and career goals); however, you should be able to modify them uit your needs.
- [https://word2md.com/](Word2MD) is a useful for taking a Word doc and converting it to Markdown for an LLM to consume.
- You can specify the formatting, tone, and style in any of the skills. I omitted those definitions because AI was able to understand the existing styles and use those when generating new content.
- The majority of the skills were written by me. However, there are times when I employed meta-prompting / reverse-prompting to ask AI what an LLM would need to be successful in completing a given task.
- Pro tip: Use a text-to-speech (TTS) program of your choice to read the content of your resume back to you. After staring at text outputs, you can confirm what you wrote sounds correct.

# Caveats
- There were only a few cases where I accepted the LLM's output without revision.
- With the "ask me questions one at a time" prompt, I steered AI toward a conversational nature instead of having it give me the result in one go and try to work ahead.
- AI makes mistakes. It makes things up that aren't true. It omits things that are important. It combines concepts that have nothing to do with one another. It fails to follow instructions.
- Even after multiple iterations, there were instances when I discarded AI's responses and wrote sections myself.
- There were times when I asked AI to review its results and it disagreed with previous outputs.
- You are always in the driver's seat when using AI. Carefully read its responses and edit or reprompt where needed.
- My intent was to accomplish the resume refresh task; however, through this process I now have a better understanding of how I'd do (or help others do) this task.