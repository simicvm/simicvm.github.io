---
layout: post
title: "Magic in the Age of Machines"
author: "Marko Simic"
categories: journal
tags: [documentation,sample]
image: magic-in-the-age-of-machines.png
---
Arthur C. Clarke's third law states that

> "any sufficiently advanced technology is indistinguishable from magic."

In my opinion, generative AI will be the closest thing to magic that we will have for a long time. Conjuring images, videos, sounds, worlds, and programs, simply through the power of our language.

This statement sound outlandish, so let's back up a bit, and I'll provide more context.


## Software Galore

Since the inception of modern computer programming, **Software 1.0** has been the primary paradigm for creating software. In this paradigm, engineers painstakingly write software line by line, defining every aspect of the program. As you can imagine, this process has several shortcomings: it requires a high level of technical skill, takes a long time to write, and it cannot capture certain functionalities. Yet, despite these shortcomings, it remains the dominant programming paradigm to this date.

In the mid-2010s, thanks to breakthroughs in deep learning, we saw the emergence of the **Software 2.0** paradigm. Software became a mixture of hand-written code (i.e., Software 1.0) and machine-learned sub-routines (e.g., neural networks). In most cases, the new machine-learned code didn't replace the hand-written code. Quite the contrary, it serves as a supplement to it. We use it to solve problems intractable by regular programming, ones for which it is extremely hard to write explicit rules and instructions (e.g., recognizing cats, determining text sentiment, generating speech, etc.).

With the proliferation of generative text-based AI models in the last two years, we started hearing about **Software 3.0** and **prompt engineering**. Prompt engineering is the process (and skill) of issuing appropriate natural language commands (i.e., prompts) to an AI model in order for it to generate desired outputs, such as software code, prose, or images. Therefore, Software 3.0 refers to software that is written by AI based on human prompts instead of being written by humans directly.

Like Software 2.0, Software 3.0 is not replacing the traditional Software 1.0 or human software engineers. Instead, **modern software is being written using all three techniques together: human-written code, machine-learned functions, and AI-generated code.**

However, we have only just begun to unlock the powers of large language models. By extrapolating current technological progress into the near future, we can see that both the terms "Software 3.0" and "prompt engineering" undersell the magnitude of the impact this paradigm shift will have.

Let me give you a silly but real example from my own life.


## Magic

For the past few days, I have been experimenting with [Matter.js](https://github.com/liabru/matter-js), a physics engine for the web. During one of my coding sessions, an idea occurred to me: it would be cool to have a VR reader for [arXiv](https://arxiv.org) papers with fluid gesture control and additional interactivity for diagrams and data. Something akin to the UI from [Minority Report](https://youtu.be/PJqbivkm0Ms). Putting aside the practicality of it, this idea is technically feasible, and I could build the basic version of this app in a few days (dependent on my familiarity with the necessary tech stack). However, we all have limited time and can't work on everything that comes to mind. Since I was already engaged with other work, I decided not to pursue this VR mini-project at the time.

But what if, in the future, we wouldn't need to compromise and choose one project over another? **Imagine a world in which a program like this, or any other that you want, could be built quickly, without deep technical knowledge, and just by using your natural language.** It wouldn't matter if you are unfamiliar with the required programming language or a particular library. It wouldn't matter that you are not a designer or an artist skilled in audio/visual asset creation. You could quickly generate all that you need, and will into existence any idea you have. A VR reader for research papers? Not a problem! A beautifully designed portfolio web page? Ready in no time! An AI-driven text adventure game using the OpenAI API? Sure thing!

The current generation of generative AI models has already shown us the incredible creativity and imagination that people are capable of. But, with the next-generation AI models that can also generate software on demand, the potential for innovation and creativity is **truly staggering**. We will see an explosion of software and apps for every imaginable thing and use case. If people can't find something that meets their needs, they will simply build it themselves.

In addition to their use for work and productivity, these AI models will also be used for entertainment. We will integrate them into virtual worlds like **Minecraft**, **Fortnite**, and **Horizon Worlds**. Your characters in the "metaverse" will wield the god-like powers to instantly spawn anything they desire. The possibilities are truly endless.


## Nightmares

I acknowledge that I may be presenting an overly optimistic view. One might even say unrealistic. In this section, let's look at the situation more critically and reflect on technological, legal, and social challenges lying ahead.


### Technological

Present-day generative models have **significant limitations**. Some even argue that they are dangerous. For example, these models often exhibit a profound lack of understanding of basic concepts like counting or spatial relationships. In addition, **they can't do any explicit logical reasoning, do not possess "common sense" like humans, and "don't know" how the world works.** Even more concerning is that their outputs can look very convincing but are, in fact, complete confabulation. All of these issues stem from the fact that these models are giant statistical pattern-matching machines that learn correlation from the data they are trained on. For large language models, this means they just predict the next most likely word based on the text that precedes it. As a result, these models also exhibit the same biases as contained in the data they were trained on, which can be problematic in certain situations.

<figure>
<img src="{{ site.github.url }}/assets/img/chatgpt-fails.png" style="width:100%">
<figcaption align = "center">ChatGPT Failures</figcaption>
</figure>

There is, actually, a more **profound question** on whether the current approach to building artificial intelligence is sufficient for achieving human-level reasoning and cognitive powers. Proponents say that all we need are stochastic gradient descent, bigger neural networks, and more data. In contrast, opponents say that scale is not enough and that in order to achieve human-like reasoning, we need to build neuro-symbolic models and develop better ways to train them. As you might imagine, this debate is quite fierce and far from settled, but also irrelevant to this post.

The good news is that many intelligent people are working on fixing these problems, and funding is certainly not lacking despite the current cool-down in VC financing. We are getting better at collecting and cleaning the data, developing novel models, loss functions, and regularization methods, and utilizing innovative training methods, like humans in the loop, that guide and instruct machine learning. Having that in mind, I am less worried about technical challenges than legal and social ones.


### Legal

On the legal side, both generative image models and large language models recently came under fire for utilizing data for training without the explicit consent of their authors. The crux of the issue is not the fact that specific data was used for training the AI, but that said AI (and its users) could then generate work in the style of the original author. In some cases of software code generation, AI was caught generating complete programs identical to the original data without giving any attribution to the authors.

To some extent, we humans do the same. We learn from prior work and our peers, which then guides our thinking and work. But the difference is in the ease of use and scale. Humans must put a lot of effort into learning, improving, and then manually producing output. And even then, their output quantity is usually very limited. On the other hand, with generative AI, anyone can instantly and with zero skill generate countless copies and mimics.

There are **potential legislative and technical solutions** for these copyright issues. For example, we could add explicit clauses in the license agreements that specify whether the data can be used to train the AI. On the technical side, we could train the AI models so that they cannot replicate the exact styles of certain creators. In fact, this was [already done](https://www.theverge.com/2022/11/24/23476622/ai-image-generator-stable-diffusion-version-2-nsfw-artists-data-changes) with Stable Diffusion 2.0 release.

These are all valid concerns, and we should work to solve them. However, I do wonder if the scribes in the 15th century had the same arguments and felt similarly about the invention of the printing press.

For me, far more concerning than the IP issues is the potential for generating hacking software automatically and using it for nefarious purposes. There are already [research examples](https://github.com/mazen160/shennina) of using machine learning in that context. And we can envision the near future in which bad actors use advanced AI to easily generate malicious software with the ability to continuously adapt in order to evade security measures it encounters. That would truly be a nightmare scenario for security researchers, and preventing or regulating such usage would be extremely hard.


### Social

Finally, social issues might be the biggest challenge to overcome. **We don't know the implications of the technology we are creating.** What happens when generating fake, but indistinguishable from reality, digital content becomes widely accessible? Will all forms of **deep fake** content flood the internet? We already know that it can cause significant emotional and financial harm to individuals, as well as have the potential to influence public opinion and cause social unrest.

To stop the spread of deep fake content, media and content platforms like YouTube and Twitter will have to implement detectors and safeguards. Even operating system (OS) providers like Apple, Google, and Microsoft may add such functionality on the OS level. However, such features come with their own controversy, with Apple recently [having to abandon](https://www.msn.com/en-us/news/technology/apple-abandons-controversial-plan-to-check-ios-devices-and-icloud-photos-for-child-abuse-imagery/ar-AA154e9D) its system for detecting child sexual abuse material. Navigating the minefields of user privacy, freedom of speech, and censorship will be a tall order for any company or government, and there will be no clear-cut solutions.

Technological solutions alone are not enough to address the social concerns and problems raised by the proliferation of artificial intelligence. We must also address public perception and educate people about the capabilities and potential misuse of AI. In today's digital age, where information is easily accessible and often unchecked, it is up to all of us to be more skeptical and critical of what we read, hear, and see online. By promoting a deeper understanding of AI and encouraging critical thinking, we can help prevent the spread of misinformation and bias, and work towards a more responsible and ethical use of this powerful technology.


## Famous Last Words

In his 1945 seminal essay "As We May Think," Vannevar Bush envisioned **"memex,"** a device that closely resembles in functionality a combination of a modern-day computer and the World Wide Web. It was a groundbreaking idea at the time. But even technical visionaries like him could not foresee the future in which we will have **the power of gods** in the digital realm. Such ideas have only been the domain of fiction and fantasy literature.

Yet, here we are, standing at the precipice of an exciting and terrifying era in which people will be able to conjure anything they want in the digital realm just with the power of their own voice. And despite all the challenges I outlined above, I remain hopeful and believe humanity will find the right solutions. The question in my mind is not "if" but "when."

In the end, I find it only fitting to close this essay with the words of Eric Weinstein:

> "We are gods but for the wisdom."
