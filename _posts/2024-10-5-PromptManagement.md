---
layout: post
audio_discussion: https://drive.google.com/file/d/1I5C16VVgladem8zUIMqfQXj8ue_ihO9f
image: /images/PromptManagement.png
tags: 
---
# Generative AI Prompt Management: Best Practices with GitHub
Have you ever created the perfect AI prompt, only to lose it in a sea of chat logs or notes? As Generative AI usage skyrockets, effective prompt management is becoming important. Let's explore how treating prompts like code can revolutionize your AI workflow.

### Generative AI Growth
Generative AI is rapidly evolving into a general-purpose technology across the United States. The growth is staggering: according to EMARKETER, 100.1 million people in the US will use Generative AI at least once per month in 2024, a nearly 900% increase from 7.8 million in 2022.

<p align="center">
  <img src="https://github.com/user-attachments/assets/e7acdb92-7952-4f7a-83a3-afa00ebb20ec"/>
</p>

People are leveraging Generative AI for research, content creation, and text summarization, primarily through crafting prompts - natural language instructions that guide AI models to perform specific tasks. As the frequency and value of Generative AI use increases, so does the need to reuse effective prompts, such as the [Rashomond AI Prompt](https://github.com/dphummel/Prompts/blob/main/Rashomon-AI-Prompt.md). However, finding the optimal method for achieving this reuse wasn't immediately apparent to me.

My research revealed various approaches, including databases and text files. But when I began to view prompts as assets to be managed - organized, stored, retrieved, and refined - I asked myself: why not manage prompts like we manage code?

### Benefits of Managing Prompts Like Code
A prompt, similar to code, is an asset in which:

1. Changes are made over time to refine and improve it.
2. It can be shared with others to help them achieve the defined outcome.
3. It can be created and refined collaboratively.
4. It can serve as input to other programs.

Now that we understand the benefits of managing prompts like code, let's explore how GitHub can help us achieve this.

### Using GitHub to Manage Prompts
[GitHub](https://github.com), owned by Microsoft, is a popular platform for version control and collaboration, primarily used by software developers to manage code. However, its features make it equally valuable for managing text-based assets like AI prompts. GitHub supports text-based file formats and offers features that align with the benefits of managing prompts as assets:

- Showcase or share your files.
- Track and manage changes to your files over time.
- Allow others to review your files and make suggestions for improvement.
- Collaborate on shared projects without worrying about how changes will impact your work before you're ready to integrate them.

### My GitHub Prompt Repository
I have created a [GitHub repository](https://github.com/dphummel/Prompts) to manage my publicly accessible prompts.

#### Formatting in Markdown
Each prompt is documented in a file using [Markdown](https://www.markdownguide.org/) - a simple and easy-to-use markup language you can use to format virtually any document. I use Markdown to document prompts because:
- It helps structure prompts into sections, making them easier for others to understand.
- It enhances readability.
- ChatGPT and Claude can parse prompts in Markdown, and a defined structure can help these tools better understand your content.

For instance, you can create headers using '#' symbols, emphasize text with asterisks like *this*, and create lists with dashes or numbers.

#### Prompt Template
I also use a [prompt template](https://github.com/dphummel/Prompts/blob/main/Prompt-Template.md) to document prompts.  The template contains the following sections:
1. Mission: goal you want to achieve.
2. Context: background information including why you need to achieve the goal.
3. Rules: boundaries and constraints.
4. Instructions: step-by-step instructions on how to achieve the goal.
5. Expected Input: what is the input.
6. Expected Output: type, format, length.
7. Example Output: demonstration of the output.

This template proved invaluable when [refining the prompt](https://github.com/dphummel/Prompts/blob/main/Dog-or-Cat-Model-Prompt.md) used to create code for the computer vision model. While documenting the prompt in this structure, I realized I was capturing the thought process behind determining how to achieve the desired outcome with the model.

The template can be simplified for managing simpler query prompts. You have the flexibility to remove sections as needed to ensure the right outcome.

#### Executing a Prompt in a Chatbot
To execute a prompt from the repository in a chatbot like ChatGPT, view the prompt's "Code" in GitHub, then copy and paste the Markdown into ChatGPT and execute.

#### Access A Prompt Systematically
A prompt can also be accessed systematically using the URL format:
`https://raw.githubusercontent.com/{owner}/{repo}/{branch}/{path}`

For example, here is the URL to access the content in the Rashomond AI Prompt file:
`https://raw.githubusercontent.com/dphummel/Prompts/main/Rashomon-AI-Prompt.md`

A developer can use this URL to access a prompt in the development an interactive application using an API like [OpenAI's API](https://platform.openai.com/docs/api-reference/introduction).

### Considerations
The legal status of prompts as intellectual property is still under debate. From one perspective, a prompt could be seen as an idea, which is not protected by intellectual property laws. From another angle, focusing on the usefulness or functionality of a prompt (rather than its artistic or creative value) might lead to their inclusion under copyright protection.

This is a debate we will have to closely watch.  In the meantime, I have made sure to acknowledge the original sources of the prompts in my repository.

### Conclusions
As Generative AI continues to reshape our world, mastering prompt management will be a key skill. Treating prompts like code will allow you to leverage GitHub's proven code management process -  prompts are version-controlled, accessible for feedback and collaboration, and easily retrievable when needed.

By adopting GitHub for prompt management, you're not just organizing text—you're standarizing your AI workflow. Start your GitHub prompt repository today, and join a growing community of AI enthusiasts who are redefining how we interact with artificial intelligence.

If you're new to GitHub but interested in using it to manage your prompts, you can start your [learning journey]( https://docs.github.com/en/get-started/start-your-journey) now. Begin organizing your prompts on GitHub today and contribute to shaping the future of prompt management!
