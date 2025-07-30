---
title: "How to use AI Automation and GitHub to Automate Your Blog"
description: "Learn how to automate your blog with AI and GitHub to save time and improve your content."
date: "2025-07-24"
image: "/images/blog/toffu-github.jpg"
slug: "how-to-use-ai-automation-and-github-to-automate-your-blog"
---

Creating high-quality content is hard enough, but another annoying part of maintaining a lively blog is to copy paste the metadata and content from the creation stage to the publishing stage.

In this blog post, I'll show you how to automate this process using AI and GitHub, while still having you in the loop.

The human in the loop is important because it allows you to review the content and make sure it's accurate and on-brand. But the cool part is that the whole process, from keyword research to publishing, is done in the same place - Toffu's chat interface.

The tools I'll be using are:

- [Toffu AI](https://toffu.ai)
- [GitHub](https://github.com)
- [Static Site Generators](https://www.staticgen.com/)

## Prerequisites

### Create a new GitHub repository

Create a new GitHub repository for your blog.

1. Go to [GitHub](https://github.com) and create a new repository for your blog.
2. That's it you can leave it empty for now.
3. Remember the name of the repository, you'll need it for the next step.

> If you want to be cool you can make the repository public. The content will appear in your blog anyway, so you might as well make it public and accessible from GitHub as Open Source.

![Toffu GitHub Repository](/images/blog/github-repo.png)

### Connect Toffu to GitHub

Toffu can connect to your GitHub repositories and push the content to there. That includes both text and images.

1. Connect Toffu to GitHub by going to the [Toffu AI Integrations](https://toffu.ai/integrations) and clicking on the "GitHub" connect button.
2. You'll be asked to authorize Toffu to access your GitHub repository. 
3. Select the repository you created in the previous step.
4. Click on the "Authorize" button.

![Toffu GitHub Integration](/images/blog/toffu-github-connect.png)

This setup is only needed once.

## Step 1: Create a new blog post

I'll start by creating a new blog post in Toffu AI.

Toffu is an AI agent that can help you create blog posts (amongst other marketing tasks).

What I like to do in order to create a high-quality blog post is to use an interactive prompt. By using an interactive prompt, I don't just ask Toffu to generate AI slop. I review each step of the process and make sure it's up to my standards.

Another thing I do with Toffu is to ask it to fetch actual data from places where my target audience is. For example, if I compare two products, I'll ask Toffu to fetch the data from G2, Capterra, or TrustPilot.

I'll also ask Toffu to scour reddit for real opinions of real people.

In the end, this is what separates a good blog post from generic AI slop which only uses pre-trained generic data.

Check out this [playbook](https://toffu.ai/playbooks?id=create-comparison-blog-post) for an example of how I use Toffu to create a blog post.

I used is to generate this blog post: https://toffu.ai/blog/n8n-vs-clay, and it reached number 1 on Google for the keyword "n8n vs clay" in a couple of days.

Here's the part of the prompt I use to create the blog post (the publish part is not included):
```
I want to write a blog post for the keyword "[INSERT KEYWORD]".

**Step 1: Research & Topic Selection**
First check my blog (toffu.ai/blog) to make sure you don't pick a subject that I already wrote about.

Then, pick a hot topic for my keyword by researching using reddit.

**Step 2: Keyword Research & Outline**
When you find a topic:

1. Research high volume/low difficulty keywords for this blog post in order to embed them naturally in the content.
2. Write an outline with the keywords in the H2 headlines
3. Make sure the title and H2s are shorter and don't use colons ":"
4. Wait for my approval for the outline

**Step 3: Content Creation**
Once I approve the outline, write the content with these guidelines:

1. Research the topic in reddit, linkedin, and google.
2. Embed the data you find in the blog post
3. Do not use the usual AI-generated structure of text->bullet points->text, mix things up.
4. Include notable quotes and hyperlink the sources as blockquotes.
5. Do not make up people or companies, only use real world examples, people, and companies.
6. Every data point needs to hyperlink to its source
7. Each external link should only appear once throughout the blog post
8. Add quotes from reddit using markdown quoteblocks and link to source comment
9. Never say "A big telecom company" - always use company names or don't include at all
10. Write in a conversational tone that sounds like a reddit user would like to read - not too scientific
11. Add relevant internal links from toffu.ai/blog, toffu.ai/tools, or toffu.ai/use-cases where they naturally fit

**Step 4: Humanization**
Once I approve the blog post, humanize the content by using the humanizer tool while preserving all links.
```

## Step 2: Push the content to GitHub

And now for the publishing part (a very annoying part when you're doing it manually):

In this part, I ask Toffu to generate a cover image and push the blog post to GitHub.

The GitHub repo acts as a CMS which has many benefits:

1. It's free.
2. It has collaboration features built in.
3. Everyone can see the content and suggest changes, both teammates and avid readers. (They can even suggest fixes for typos and grammar mistakes)

I ask Toffu to push the blog post to GitHub as [markdown](https://www.markdownguide.org/basic-syntax/), with [frontmatter](https://jekyllrb.com/docs/front-matter/) in the following format:

```
---
title: "..."
description: "..."
date: "2025-07-24"
image: "<insert the image url from step 1>"
slug: "blog-post-slug-here"
---

[This is the markdown for the blog post]
```

And here's the prompt for the publishing part:

```
**Step 5: Publishing**
When the blog post is completed and ready:

1. Generate a cover image
2. Push the blog post to github as a markdown file, named "blog-post-slug.md" with frontmatter in the following format:

---
title: "..."
description: "..."
date: "2025-07-24"
image: "<insert the image url from step 1>"
slug: "blog-post-slug-here"
---

[This is the markdown for the blog post]
```

Here is how it looks like in Toffu's chat interface:

![Toffu GitHub Publishing](/images/blog/toffu-blog-chat.jpg)

## The full playbook

Notice how I'm using an interactive prompt to create the blog post. I review each step of the process and make sure it's up to my standards.

```
I want to write a blog post for the keyword "AI Automation".

First check my blog to make sure you don't pick a subject that I already wrote about (toffu.ai/blog)

Then, pick a hot topic for my keyword by researching using reddit.

When you find a topic:

1. Research high volume/low difficulty keywords for this blog post in order to embed them naturally in the content.
2. Write an outline with the keywords in the H2 headlines
3. Wait for my approval for the outline

Once I approve the outline, write the content with these guidelines:

1. Research the topic in reddit, linkedin, and google.
2. Embed the data you find in the blog post
3. Do not use the usual AI-generated structure of text->bullet points->text , mix things up.
4. Include notable quotes and hyperlink the sources as blockquotes.
5. Do not make up people or companies, only use real world examples, people, and companies. 

Once I approve the blog post, humanize the content by using the humanizer tool.

When the blog post is completed and ready:

1. Generate a cover image
2. Push the cover image to the github repo "blog-posts", "images" folder.
3. Push the blog post to github as a markdown file, names "blog-post-slug.md" with frontmatter in the following format:

---
title: "..."
description: "..."
date: "2025-07-24"
image: "<insert the image url from step 2>"
slug: "how-to-use-ai-automation-and-github-to-automate-your-blog"
---

This is the markdown for the blog post
```

## Step 3: Deploy the blog post

There are many Static Site Generators (SSGs) that can use GitHub as a CMS. However, this is outside the scope of this blog post.

I'm using [Next.js](https://nextjs.org) with [Vercel](https://vercel.com) to host Toffu's blog.

I recommend visiting [StaticGen](https://www.staticgen.com/) to find the best looking blog template for you.

You only need to set up your statically generated blog once.

After that, you'll need to redeploy the blog when you want to publish a new blog post that was created with Toffu.
