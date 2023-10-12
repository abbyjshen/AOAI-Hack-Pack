# Build your own Copilot
Reference this page at: [aka.ms/AOAI-Hack-build-copilot](https://aka.ms/AOAI-Hack-build-copilot)

## Check this out 👇
[This project contains resources and examples to help you as you build your own Co-Pilot applications that use modern AI to assist with complex tasks.
](https://github.com/rohit-lakhanpal/build-your-own-copilot)


## Considerations
### What is a Copilot
How much of the Copilot stack are you intending to cover in your own Copilot?

[The era of the AI Copilot | KEY02H - YouTube](https://www.youtube.com/watch?v=FyY0fEO5jVY)

AI-enabled app continuum
1. Reason over existing data
2. Automate actions
3. Act on users' behalf <-- Copilot

### Considerations
Have you thought about:

- APIs or programmatice access to functionality in your app in order to act on users' behalf?
  - If you are building and exposing actions in your app as a plugin, this is built on OpenAI's plugins specification (so can be invoked by ChatGPT, Bing Chat, M365 copilot, and others). You may want to build your plugin, then test it with M365 or other existing Copilots first https://aka.ms/AOAI-Hack-build-plugin
  - e.g., Microsoft has an existing automation framework VBA (Visual Basic for Applications), which is a programming language for automating tasks in Office applications

- UX - does user invoke it via a chatbot? text field? ...or a button? Do you pass user natural language input directly, or formulate a prompt based on restrained input? How do you expose what your Copilot does/doesn't do? 

- Safety and guardrails when acting on users' behalf? What if the detected intent based on user prompt is unclear or incorrect or unsupported?


## Learning Resources
- See [this session](https://build.microsoft.com/en-US/sessions/bb8f9d99-0c47-404f-8212-a85fffd3a59d?source=sessions) and [linked slides](https://github.com/abbyjshen/AOAI-Hack-Pack/blob/main/packs/copilot/KEY02H%20KevinScott_05232023_Build_POSTSHOW%20The%20era%20of%20the%20AI%20Copilot.pdf) from Microsoft Build
  - Learn what are the components of the Copilot stack
  - Example of a Copilot [PodcastSocialMediaCopilot.py](https://github.com/microsoft/PodcastCopilot/blob/main/PodcastSocialMediaCopilot.py)
  - Related announcements: [here](https://news.microsoft.com/source/features/ai/microsoft-outlines-framework-for-building-ai-apps-and-copilots-expands-ai-plugin-ecosystem/)

- Learn about the Orchestration layer
  - Semantic Kernel [kernel](https://learn.microsoft.com/en-us/semantic-kernel/create-chains/kernel), [planner](https://learn.microsoft.com/en-us/semantic-kernel/create-chains/planner), [plugins](https://learn.microsoft.com/en-us/semantic-kernel/create-plugins/), [memories](https://learn.microsoft.com/en-us/semantic-kernel/memories/)
  - Short video series explaining with a cooking analogy [here](https://devblogs.microsoft.com/semantic-kernel/recipes/)
  - Or other options

- Learn about safety and security in AI
- etc.


## Technical Setup
1. X
2. X
3. X
4. ... (redirect to Build AOAI Feature page for set up)


### Accelerators and samples
- Kevin Scott's Podcast Copilot
  - [The era of the AI Copilot](https://build.microsoft.com/en-US/sessions/bb8f9d99-0c47-404f-8212-a85fffd3a59d?source=sessions)
  - [PodcastCopilot: Build 2023 demo](https://github.com/microsoft/podcastcopilot)

- Semantic Kernel Chat Copilot
  - [Announcement blog](https://devblogs.microsoft.com/semantic-kernel/announcing-copilot-chat/)
  - [Documentation](https://learn.microsoft.com/en-us/semantic-kernel/chat-copilot/)
  - [Repo](https://github.com/microsoft/chat-copilot)

- Another accelerator / repo / lab
