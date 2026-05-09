# Description
This repository contains prompts that you can use with an LLM tool to refresh an existing resume.

Although this has practical uses (i.e., updating my own resume), I approached it from an agentic viewpoint where I start with a plan and have separate prompts for implementing that plan in small, focused steps that feed into one another.

# How to use
The `plan-resume-update` skill led to the creation of the other skills in this repo. Review, revise, and invoke that skill to build out other skills as needed.

You can also use the skills I've provided here. Tip: Clear the context window before invoking the next skill.
1. `define-resume-objectives`
2. `collect-integrate-new-accomplishments`
3. `rewrite-experience-sections`
4. `revise-skills-section`
5. `revise-tagline-summary-key-strengths`
6. `recommend-resume-format`
7. `recommend-linkedin-content`

# Other considerations
- The prompts were specific to my use case (i.e., my resume and career goals); however, you should be able to modify them to suit your needs.
- [https://word2md.com/](Word2MD) is a useful tool for taking Microsoft Word content and converting it to Markdown for an LLM to consume.
- The majority of the prompts were written by a human (i.e., me). However, there are times when I employed meta-prompting / reverse-prompting to ask AI what an LLM would need to be successful in completing a given task.
- Pro tip: Use a text-to-speech (TTS) program of your choice to read the content of your resume back to you. After several hours of staring at text, you can confirm what you wrote sounds correct.

# Caveats
- There were only a few cases where I accepted the LLM's output without revision.
- With the "ask me questions one at a time" prompt, I steered AI toward a conversational nature instead of having it give me the result in one go and try to work ahead.
- AI makes mistakes. It makes things up that aren't true. It omits things that are important. It combines concepts that have nothing to do with one another. It fails to follow instructions.
- Even after multiple iterations, there were instances when I discarded AI's responses and wrote sections myself.
- There were times when I asked AI to review its results and it disagreed with previous outputs.
- You are always in the driver's seat when using AI. Carefully read its responses and edit or reprompt where needed.
- My intent was to accomplish the resume refresh task; however, through this process I now have a better understanding of how I'd do (or help others do) this task.