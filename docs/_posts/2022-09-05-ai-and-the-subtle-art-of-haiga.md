---
layout: post
title: "AI and The Subtle Art of Haiga"
author: "Marko Simic"
categories: journal
tags: [documentation,sample]
image: ai-and-the-subtle-art-of-haiga.png
---

## Background

The pace of progress with generative art is truly astonishing these days. Only several months ago did the OpenAI release their DALL-E 2 model to the public, and it was shortly followed by Midjourney. Nowadays, we also have Stable Diffusion, which is, unlike the former two, free to use. Besides these three models, Google and Facebook have their own behind closed doors, and of course, there are older generation models too.

However, this post will not be about the technical underpinnings of these text-to-image generative models. For that, I would highly recommend: [What are Diffusion Models?](https://lilianweng.github.io/posts/2021-07-11-diffusion-models/) and [Introduction to Diffusion Models for Machine Learning](https://www.assemblyai.com/blog/diffusion-models-for-machine-learning-introduction/).

This post is about using three AI models mentioned above to visualize something deeply human, Haiku poetry, and qualitatively compare their results.

But connecting Haiku and painting is not new. It is an old art form, a style of Japanese painting, called **Haiga**. They are typically painted by Haiku poets and are usually accompanied by a Haiku poem. Unlike other schools of painting, Haiga did not have a standard style, and it varied from artist to artist. Today, Haiga artists combine Haiku with different art mediums like photography, and now we can add AI art to that collection.

The idea for this comparison was born after seeing a Haiku by **Richard Wright** printed on a facade of a building in Brooklyn. It said:

>The creeping shadow<br>
>Of a gigantic oak tree<br>
>Jumps over the wall.

Try to think about it and imagine the scene… One of the defining characteristics of Haiku is that it juxtaposes two images, which results in unusual and surprising depictions. That effect can also result in some fun and interesting AI art.

In this exploration, I'll stick to the Haiku of Richard Wright. American writer who lived between 1908 and 1960, Richard is considered the first noteworthy American minority writer to produce Haiku. However, he is more known for his work involving racial themes, and his writing helped change racial relations in the US. Interestingly, he only started writing Haiku poems one year before his death, and his work was not published until 1998.

Haiku in English are often printed on three lines, while in Japanese, Haiku are traditionally printed as a single line. That means we won't break any rules if we "flatten" the original text and feed the whole poem in a single line, just like AI likes it. Additionally, I didn't use any modifiers or style prompts, just the exact poem text.

While looking at the results, please keep in mind that AI models are trained on human-generated data freely available on the internet. As such, they exhibit all the biases that internet data has.

## Haiku and Haiga

>In a red sunset<br>
>A frog commands the night wind<br>
>To roll out a moon.

![alt text]({{ site.github.url }}/assets/img/haiga-frog.png)

>The creeping shadow of<br>
>a gigantic oak tree<br>
>jumps over the wall.

![alt text]({{ site.github.url }}/assets/img/haiga-oak.png)

>I give permission<br>
>For this slow spring rain to soak<br>
>The violet beds.

![alt text]({{ site.github.url }}/assets/img/haiga-violet.png)

>With a twitching nose<br>
>A dog reads a telegram<br>
>On a wet tree trunk.

![alt text]({{ site.github.url }}/assets/img/haiga-dog.png)

>A sleepless spring night:<br>
>Yearning for what I never had<br>
>And for what never was.

![alt text]({{ site.github.url }}/assets/img/haiga-spring.png)

>In a misty rain<br>
>A butterfly is riding<br>
>The tail of a cow.

![alt text]({{ site.github.url }}/assets/img/haiga-cow.png)

>In a dank basement<br>
>A rotting sack of barley<br>
>Swells with sprouting grain.

![alt text]({{ site.github.url }}/assets/img/haiga-barley.png)

>In a drizzling rain,<br>
>In a flower shop’s doorway,<br>
>A girl sells herself.

![alt text]({{ site.github.url }}/assets/img/haiga-girl.png)

>From the cherry tree<br>
>To the roof of the red barn,<br>
>A cloud of sparrows flew.

![alt text]({{ site.github.url }}/assets/img/haiga-barn.png)

>In the setting sun,<br>
>Red leaves upon yellow sand<br>
>And a silent sea.

![alt text]({{ site.github.url }}/assets/img/haiga-sun.png)

>The barking of dogs<br>
>Is deepening the yellow<br>
>Of the sunflowers.

![alt text]({{ site.github.url }}/assets/img/haiga-sunflower.png)

>In the falling snow<br>
>A laughing boy holds out his palms<br>
>Until they are white.

![alt text]({{ site.github.url }}/assets/img/haiga-boy.png)

>Lonelier than dew<br>
>On shriveled magnolias<br>
>Burnt black by the sun.

![alt text]({{ site.github.url }}/assets/img/haiga-magnolia.png)

## Conclusion

Based on the generated images above, I can spot a few patterns.

DALL-E and Stable Diffusion, by default, aim for photorealism, while Midjourney is heavily biased towards style. Unfortunately, the company behind Midjourney did not release details on their AI model and data used for training, so I am not sure how they achieved their stylized output. But, both DALL-E and Stable Diffusion can be "nudged" to produce more stylized results by using appropriate prompts.

DALL-E exhibits a better "understanding" of the concepts than the other two models, and its depictions align more with the words it was given.

All three models fall into an uncanny valley when it comes to the human faces, with Stable Diffusion being the worst offender. And all human figures depicted have white skin, which is definitely an artifact of the data used for training.

All three models produce satisfactory outputs, and most, if not all, images are aesthetically pleasing.

These AI models are very powerful and are already impacting the art and design world on many levels. But as Uncle Ben and many others before him noted, "with great power comes great responsibility." Some people are vocal about issues these models bring, namely the job displacement and unauthorized use of large amounts of human-generated data. These concerns have some merit, but they are a consequence of technological advancements, and we will have to find a way to live with them. Personally, I do see this technology as a net positive contribution to society, a valuable tool for work, and an augmentation for our minds.

If you like AI art, you can also check [my older project](https://youtu.be/73RpZxjey-g) in which we used AI to create a video for another poem.
