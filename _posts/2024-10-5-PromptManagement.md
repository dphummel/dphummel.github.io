---
layout: post
audio_discussion:  
image: 
tags: 
---
# Generative AI Prompt Management: Best Practices with GitHub
Generative AI is quickly growing in use across the United States as a general purpose technology.  This year 100.1 million people in the US will use generative AI at least once per month, up nearly 900% from 7.8 million in 2022.  (Source: EMARKETER)

![48884_original](https://github.com/user-attachments/assets/e7acdb92-7952-4f7a-83a3-afa00ebb20ec)

People are using Generative AI to conduct research, create written content, and summarize written text, for example, through the creation of prompts - natural language text that requests a Generative AI to perform a task.  I believe there is a need to be able to use prompts repeatedly, like the [Rashomond AI Prompt](https://github.com/dphummel/Prompts/blob/main/Rashomon-AI-Prompt.md).  However, the best way to achieve this reuse was not immediately apparent. 

My research led to people using many approaches, including databases and text files. When I thought of a prompt as an asset which I want to manage - organize, store, retrieve, and refine - I asked myself: why not manage a prompt like I manage code?

### Benefits of Managing Prompts Like Code
A prompt, similar to code, is an asset in which:

1. Changes are made over time to refine and improve it.
2. It can be shared with others to help them achieve the defined outcome.
3. It can be created and refined across multiple people.
4. It can be used as input to other programs.

### Using GitHub to Manage Prompts
GitHub, owned by Microsoft, is a web-based platform where you can store, share, and work together with others on code. GitHub supports text-based file formats and offers features that align with the benefits of managing prompts as assets:
- Showcase or share your files.
- Track and manage changes to your files over time.
- Let others review your files and make suggestions to improve them.
- Collaborate on shared projects without worrying about how changes will impact your work before you're ready to integrate them.

### My GitHub Prompt Repository
I have used GitHub to create a [repository](https://github.com/dphummel/Prompts) to manage my publically accesssible prompts.

#### Formatting in Markdown
Each prompt is documented in a file using [Markdown](https://www.markdownguide.org/) - a simple and easy-to-use markup language you can use to format virtually any document. I use Markdown to document prompts because:
- It helps me structure prompts into sections which make them easier for others to understand.
- It makes the prompt easier to read.
- ChatGPT and Claude are able to parse prompts in Markdown, and having a defined structure in your prompt can help these tools understand your content better.

#### Prompt Template
I also use a [prompt template](https://github.com/dphummel/Prompts/blob/main/Prompt-Template.md) to document prompts.  The template contains the following sections:
1. Mission: goal you want to achieve.
2. Context: background information including why you need to achieve the goal.
3. Rules: boundaries and constraints.
4. Instructions: step-by-step instructions on how to achieve the goal.
5. Expected Input: what is the input.
6. Expected Output: type, format, length.
7. Example Output: demonstration of the output.

I found this template very helpful when I created the [refined version of the prompt](https://github.com/dphummel/Prompts/blob/main/Dog-or-Cat-Model-Prompt.md) used to create code for the computer vision model.  While documenting the prompt in this structure, I realized I was documenting the thought process I went through in determining how to achieve the desired outcome with the model.

The template can be overkill if you want to manage a prompt which is a simple query. You have the ability to remove sections as you see fit to ensure the right outcome will be achieved.

#### Executing a Prompt in a Chatbot
To execute a prompt from the repository in a chatbot like ChatGPT, I view the prompt's "Code" in GitHub, then copy and paste the Markdown into ChatGPT and execute.

#### Access A Prompt Systematically
A prompt can also be accessed systematically using the URL format:
- https://raw.githubusercontent.com/{owner}/{repo}/{branch}/{path}.

For example, here is the URL to access the content in the Rashomond AI Prompt file:
- https://raw.githubusercontent.com/dphummel/Prompts/main/Rashomon-AI-Prompt.md.

A developer might take this approach in developing an interactive application like a negotiation tutor which is based off the [negotiation prompt](https://github.com/dphummel/Prompts/blob/main/Negotiation-Prompt.md) from Ethan Mollick's book *Co-Intelligence*.

### Considerations
Unlike code, the jurory is still out on if prompts are considered intellectual property.  From one angle, a prompt can be thought of as an idea, the content we seek to find in the final output.  However, intellectual property does not protect ideas.  From another angle, if we focused on the usefullness or functinoality of a prompt (versus the artistic or creative value), a decision could be made to include them under the umbrella of copyright protection. 

This is a debate we will have to closely watch.  In the meantime, I have made sure to acknowledge the original sources of the prompts in my repository.

### Conclusions
Treating prompts like code has helped me leverage a proven code management process using GitHub to manage them. My prompts are version controlled and accessible to others to seek feedback and collaborate on changes. And I can easily access them to gain their benefits when I need them.

As Generative AI continues to grow and evolve, effective prompt management will become increasingly crucial. By adopting code management practices for prompts, we can enhance collaboration, improve prompt quality, and accelerate AI-driven innovation.

If you are interested in using GitHub to manage your prompts but you have not used this tool, you can start your learning journey [here]( https://docs.github.com/en/get-started/start-your-journey). Start organizing your prompts on GitHub today and join the community in shaping the future of prompt management!
