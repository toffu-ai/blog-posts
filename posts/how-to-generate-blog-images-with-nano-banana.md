---
title: "How to generate on-brand blog images with Nano Banana"
description: "Learn how to generate blog image with Nano Banana and Toffu AI"
date: "2025-09-03"
image: "https://cdn-uw2.toffu.ai/68594b73894454f695c17c39/images/bc2fddaf-4bff-453a-9258-0ac77a296152.jpg"
slug: "how-to-generate-blog-images-with-nano-banana"
---

Google announced [Nano Banana](https://blog.google/products/gemini/updated-image-editing-model/) which is a new image editing model that is considered to be the best image editing model available (at least up until as of this writing).

The problem with generating blog images is that it's not easy to generate on-brand images that are relevant to the blog post and that are also high quality.

In this blog post, I'll show you how to generate on-brand blog images with Nano Banana and Toffu AI.

Since Toffu AI already uses Nano Banana behind the scenes, we don't need any other tools.

## Step 1: Create a base image (done once)

The setup is very simple.

We need to give Toffu stand-in insturctions on how we want blog images to be generated. Since Toffu has memory, it will remember these instructions and use them for future blog images.

That's right, you don't have to remind it every time.

### The base image

We need to give Toffu a base image that it will use as a reference for the blog image.

I recommend taking an existing image from your blog that looks like a good candidate for a base image, and then using ChatGPT to either remove the background or give it the brand color, depending on how your blog images look like.

The next step is to resize the image to the size you want the blog images to be. So when you ask Toffu to generate a blog image, it will use this base image as a reference and the size of the final image will be the same as the base image.

Here is an example of what I use for base image: 

![Toffu's Base image](https://toffu-assets.s3.amazonaws.com/email/toffu-ref.png)

### The instructions

Here is the prompt I use to give Toffu instructions on how to generate the blog image:

```
Blog Image Guidelines

Technical Requirements: 
- Must use edit_image tool (not generate_image)
- Always rectangular size 1536x1024
- Always start from base image: https://toffu-assets.s3.amazonaws.com/email/toffu-ref.png

Content Rules: 
- No text - purely visual content only
- Avoid AI-related themes or keywords (e.g., 'futuristic', 'AI brain')
- No AI motifs in imagery

Visual Style: 
- Focus on clean, professional designs 
- Maintain brand consistency with your reference image 
- Create compelling visual hierarchy
```

I only tell this once and forget about it. From now on, when I ask Toffu to generate a blog image, it will use these instructions and the base image to generate the blog image.

## Step 2: Generate the blog image (done every time)

Now, when I ask Toffu to generate a blog image, it will use the base image and the instructions to generate the blog image.

So now, let's say I'm writing a blog post titled "Mailchimp vs ConvertKit", I simply ask Toffu to generate a blog image for me.

```
Generate a blog image for the blog post "Mailchimp vs ConvertKit"
```

This is the result I got:

![Toffu's Blog image](https://toffu.ai/_next/image?url=https%3A%2F%2Fraw.githubusercontent.com%2Ftoffu-ai%2Fblog-posts%2Fmain%2Fimages%2Fmailchimp-vs-convertkit-blog-header.png&w=828&q=75)

I only had to ask it once and now it's done.

Want to see how I generated the image for this blog post? See this [Toffu session](https://toffu.ai?public=true&session_id=c22e9960-93d8-4ef9-8b31-a059a80ddb94)

![](https://toffu-assets.s3.amazonaws.com/email/nano-chat.png)
