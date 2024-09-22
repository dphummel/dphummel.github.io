---
layout: post
audio_discussion: https://drive.google.com/file/d/1dXKWV2ByEhjrfbO8SZd58W44u6OidOwC
---
# Lessons Learned from Creating Code with Generative AI
Can AI really code as well as humans? I put ChatGPT to the test, challenging it to create a computer vision model for classifying images of dogs and cats. The results were both impressive and surprising!

For the purposes of this article, when I refer to AI, I’m specifically talking about Large Language Models (LLMs)- deep-learning models that are pre-trained on vast amounts of data-and tools like ChatGPT which assist in tasks ranging from idea generation to real-time coaching.

Disclaimer: This post dives a bit deeper into the technical aspects of AI and software development compared to my previous posts. While I aim to keep explanations as clear and approachable as possible, some parts may require a basic understanding of coding concepts.

### The Challenge: Creating a Computer Vision Model
I set out to see if ChatGPT could write a computer vision model to classify images as either a dog or a cat as effectively as I could. My goal was to compare the AI-generated code with a [model I had manually created](https://github.com/dphummel/AI/blob/main/computer-vision-is-it-a-dog.ipynb).

### First Attempt:  Code Within Seconds
I eagerly started by providing ChatGPT with the following prompt using the model's requirements:

- **Prompt**: `Can you write a Jupyter notebook which uses fastai to download cat and dogs images to train a model to identify dogs and cats?`

ChatGPT produced code based on this prompt within seconds! The code appeared to use the Fastai API correctly and even included comments to make it readable. Excited by the quick result, I copied the code into a [Jupyter Notebook](https://github.com/dphummel/AI/blob/main/computer-vision-is-it-a-dog-chatgpt.ipynb) on [Kaggle](https://kaggle.com) and ran it.

To my surprise, I immediately received a type error exception—an operation was being performed on an incorrect data type. Maybe Generative AI code creation wasn't as flawless as I initially thought!

The exception was caused by the function:
- `def is_cat(x): return x[0].isupper()`

This function is called to determine the classification of an image in the training and validation datasets (i.e., is the image a dog or a cat?). The parameter x is a PosixPath object (a type used to represent file paths) that does not support indexing, such as x[0]. I had encountered this error while building previous models, so I knew how to address it.

### Debugging with AI: Refining the Labels

Rather than modifying the code myself, I shared the error with ChatGPT and asked for a fix. 

- **Prompt**: `Can you write a Jupyter notebook which uses fastai to download cat and dog images to train a model to identify dogs and cats?  Please make sure the is_cat(x) function is defined correctly.  Last time, I received the following error trying to compile this function:  TypeError: 'PosixPath' object is not subscriptable caused by x[0].`

ChatGPT quickly acknowledged the problem and provided this solution:
- `def is_cat(x): return x.name[0].isupper()`

This version of the code worked, but it labeled the animals as either "true" for a cat or "false" for a dog. Based on my experience, I found it hard to remember which animal "true" and "false" represented. So, I went back to ChatGPT and asked for one more change.

- **Prompt**: `Thank you for correcting the issue with the is_cat(x) function.  However, the function is returning either true or false if the image is of a cat.  Can you have the function return "Cat" if the image is a cat or "Dog" if the image is a dog?`

ChatGPT responded with this:
- `def is_cat(x): return "Cat" if x.name[0].isupper() else "Dog"`

This revision worked perfectly! When I ran the final version of the code, it produced a model with higher accuracy than the one I had written manually. (In hindsight, this function probably should be called get_image_label to make it more descriptive of its purpose.)

### Key Differences: AI vs. Manual Coding
There were a couple of key differences between the code ChatGPT produced and what I wrote, with the latter point definitely contributing to the improved accuracy in the model:

1. ChatGPT used the Resnet-34 convolutional neural network as the pre-trained model (i.e., a model which has already been trained on a large dataset and can by used as starting point for developing new models) instead of Resnet-18. Resnet-34 and Resnet-18 are specialized AI models designed for image processing tasks.
2. ChatGPT used the Oxford-IIIT Pets Dataset, which provided a large and high-quality dataset for training.

### The Value of Generative AI in Coding
I was impressed by ChatGPT's ability to understand my requests and produce code that was almost spot-on. Here are my key takeaways:

1. ***Productivity Gains***: Writing the model manually took me about 5 hours (which included time to educate myself on creating models along with actual coding and debugging). ChatGPT produced code in seconds.
2. ***Human in the Loop***: The code was not perfect at first. It required checking and refinement by someone with experience focusing on things like accuracy, simplicity, and maintainability, aligning with one of Ethan Mollick's guiding principles—AI needs human oversight.
3. ***Prompt Design Matters***: Spending time refining your prompt yields better results. As a separate exercise, I found that [clearly articulating the mission, constraints, and expected outcomes](https://github.com/dphummel/Prompts/blob/main/Dog-or-Cat-Model-Prompt.md) led to code that more accurately matched my objective.
4. ***Generative AI for Non-developers***: While non-developers can use tools like ChatGPT, they must invest time in understanding the code to validate its accuracy. This may reduce immediate productivity gains, but it will improve over time.

### Conclusions and Best Practices
There are definite productivity benefits to using Generative AI for code creation. These benefits are best realized by individuals who:

- Have a clear understanding of what needs to be achieved and can articulate it clearly through prompt engineering.
- Have the knowledge to review and refine AI-generated code.
- Have the ability to test the code thoroughly to ensure high quality.

I see Generative AI as a tool allowing an experienced developer to focus on being the navigator who is defining the action (i.e., the prompt) and reviewing code while the AI is the driver who is writing the code- a variation on pair programming.

In conclusion, while generative AI shows promise in accelerating coding tasks, it's not a magic solution. The most effective use of this technology comes from combining AI's speed and vast knowledge base with human expertise, critical thinking, and attention to detail. As we continue to explore the possibilities of AI in software development, finding this balance will be key to unlocking its full potential.

