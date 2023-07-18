
# Getting started with Vertex AI Generative AI Studio's User Interface

This guide provides instructions on how to use Generative AI Studio through the Google Cloud console, without using the API or Python SDK.

## Vertex AI Generative AI Studio on Google Cloud

[Vertex AI Generative AI Studio](https://cloud.google.com/generative-ai-studio) is a cloud-based platform that allows users to create and experiment with generative AI models. The platform provides a variety of tools and resources that make it easy to get started with generative AI, even if you don't have a background in machine learning.

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/overview.jpg)

---

## Language
There are two ways to access the Language offerings from Generative AI Studio on Google Cloud:

- Click the **OPEN** button at the bottom of the **Language** box on the Generative AI Studio Overview page.
- Click **Language** from the menu on the left under Generative AI Studio tab.

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/open-language.jpg)

Upon clicking, the following page will be presented.

![Language page of Generative AI](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/landing.jpg)

---

## Get Started

### What is prompt design?
Prompt design is the process of creating prompts that elicit the desired response from language models. Writing well structured prompts is an essential part of ensuring accurate, high quality responses from a language model.

### What is a prompt?
A prompt is a natural language request submitted to a language model to receive a response back. Prompts can contain questions, instructions, contextual information, examples, and partial input for the model to complete or continue. After the model receives a prompt, depending on the type of model being used, it can generate text, embeddings, code, images, videos, music, and more.


### Create Prompt using UI

*Create Prompt* lets you designs prompts for tasks relevant to your business use case including code generation. To get started, click on the **+ TEXT PROMPT** button as shown in the image below

![Create Prompt](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/click-create-prompt.jpg)

Upon clicking, you will be redirected to the following page. You can hover or click on **?** buttons to find out more about each field and parameter. Also, the following image has been annotated to provide a quick overview of the interface.

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/new-prompt-annotated.jpg)

You can feed your desired input text, e.g. a question, to the model. The model will then provide a response based on how you structured your prompt. The process of figuring out and designing the best input text (prompt) to get the desired response back from the model is called **Prompt Design**.

Currently, there is no best way to design the prompts yet. Generally, there are 3 methods that you can use to shape the model's response in a way that you desired.
- **Zero-shot prompting** - This is a method where the LLM is given no additional data on the specific task that it is being asked to perform. Instead, it is only given a prompt that describes the task. Try the following prompt out and see what kind of response you get back

```
Decide whether a Tweet's sentiment is positive, neutral, or negative.
Tweet: I loved the new YouTube video you made!
Sentiment:
```

- **One-shot prompting** - This is a method where the LLM is given a single example of the task that it is being asked to perform. Try the following prompt out and see what kind of response you get back.

Decide whether a Tweet's sentiment is positive, neutral, or negative.
Tweet: I loved the new YouTube video you made!
Sentiment: positive
Tweet: That was awful. Super boring 😠
Sentiment:

- **Few-shot prompting** - In a few-shot prompt you provide few examples to the LLM within the prompt to give some guidance on what type of response you want. Try the following prompt out and see what kind of response you get back.

Decide whether a Tweet's sentiment is positive, neutral, or negative.
Tweet: I loved the new YouTube video you made!
Sentiment: positive
Tweet: That was awful. Super boring 😠
Sentiment: negative
Tweet: Something surprised me about this video - it was actually original. It was not the same old recycled stuff that I always see. Watch it - you will not regret it.
Sentiment:

You may also notice the **FREE-FORM** and **STRUCTURED** tabs in the image below. Those are the two modes that you can use while designing your prompt.

- **FREE-FORM** - This mode provides a free and easy approach to design your prompt. It is suitable for small and experimental prompts with no additional examples. You will be using this to explore zero-shot prompting.
- **STRUCTURED** - This mode provides an easy-to-use template approach to prompt design. Context and multiple examples can be added to the prompt in this mode. This is especially useful for one-shot and few-shot prompting methods which you will be exploring later.

---

### FREE-FORM mode

You will try zero-shot prompting in **FREE-FORM** mode. To start,

- Copy the following prompt into the input field
```
What is a prompt gallery?
```
- Click on the **SUBMIT** button on the right side of the page

The model will respond a comprehensive definition of the term prompt gallery.

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/new-prompt-freeform.jpg)

Here are a few exploratory exercises for you to explore.
- adjust the `Token limit` parameter to `1` and click the **SUBMIT** button
- adjust the `Token limit` parameter to `1024` and click the **SUBMIT** button
- adjust the `Temperature` parameter to `0.5` and click the **SUBMIT** button
- adjust the `Temperature` parameter to `1.0` and click the **SUBMIT** button

Inspect how the responses change with changes to the parameters?

---

### STRUCTURED mode

With **STRUCTURED** mode, you can design prompts in more organized ways. You can also provide **Context** and **Examples** in their respective input fields. This is a good opportunity to learn one-shot and few-shot prompting.

In this section, you will ask the model to complete a sentence. Go back to the **Text Prompt** window and
- Click on the **STRUCTURED** tab
- Copy "the colour of the sky is" in **INPUT** field
- Click on the **SUBMIT** button on the right side of the page

You would see a similar result as shown in the image below.

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/new-prompt-structured-zero-shot.jpg)

Instead of completing the sentence, the model gave a full sentence as a response which is not what we wanted. You can try to influence the model's response with one-shot prompting. This time around you will add an example for the model to based its output from.

Under **Examples** field,
- Copy `the colour of the grass is` into the **INPUT** field
- Copy `green` into the **OUTPUT** field

Under **Test** field,
- Copy `the colour of the sky is` into the **INPUT** field
- Leave the **OUTPUT** field blank

- Click on the **SUBMIT** button on the right side of the page.

Now the model will respond to complete the sentence instead.
The response should be something similar to this.

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/new-prompt-structured-one-shot.jpg)

Congrats! You have successfully influenced the way the model produces response.

---

For the next task, you will use the model to perform sentiment analysis on a sentence, such as determining whether a movie review is positive or negative. Go back to the **Text Prompt** window and
- Copy the prompt `It was a time well spent!` over into the **INPUT** field
- Click on the **SUBMIT** button on the right side of the page

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/new-prompt-structured-sentiment-zero-shot.jpg)

As you can see, the model did not have enough information to know whether you were asking it to do sentiment analysis. This can be improved by providing the model with a few examples of what you are looking for.

Try adding these examples as shown in the image below:

| **INPUT**                         | **OUTPUT** |
|-----------------------------------|------------|
| A well-made and entertaining film | positive   |
| I fell asleep after 10 minutes    | negative   |
| The movie was ok                  | neutral    |

and click on the **SUBMIT** button on the right side of the page

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/new-prompt-structured-sentiment-few-shot.jpg)

The model will now responds the way you wanted. It should respond as **positive**.

You can also save the newly designed prompt. To save the prompt, click on **SAVE** button and name it anyway you like.

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/new-prompt-save-prompt.jpg)

The saved prompt will appear at the **MY PROMPTS** tab.

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/my-prompts-saved.jpg)

---

### Create Chat Prompt
Go back to the **Language** page and click on the **+ TEXT CHAT** button to create a new chat prompt.

![Text Prompt](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/click-create-chat-prompt.jpg)

You will see the new chat prompt page. It's relatively similar to the [new prompt page](#new-prompt) that you went through earlier.

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/new-chat-prompt.jpg)

For this section, you will add context to the chat and let the model respond based on the context provided. Let's add these contexts to the **Context** field.

- copy these context to **Context** field
>> Your name is Roy. <br/>
>> You are a support technician for an IT department. <br/>
>> You only respond with "Have you tried turning it off and on again?" to any queries.

- copy "my computer is so slow" to the chatbox and
- press **Enter** key or click the send message button (the right arrow-head button)

![image](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/prompt-gallery/new-chat-prompt-with-context.jpg)

The model would consider the provided additional context and answer the questions within the constraints.

## Prompt Gallery

Prompt Gallery lets you explore how generative AI models can work for a variety of use cases. There are a variety of topics: Summarization, Classification, Extraction, Writing, and Ideation for you to explore. Head back to the **Get Started** page and explore them at your own pace.

![Language page of Generative AI](https://storage.googleapis.com/github-repo/img/gen-ai-studio/language/landing.jpg)


### Congratulations!
In this lab, you learnt
- How to navigate the Vertex AI Generative AI Studio user interface
- Design prompts using the Generative AI Studio's user interface
