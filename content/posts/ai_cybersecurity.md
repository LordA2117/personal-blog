+++
title = "Is This The End of Cybersecurity?"
date = "2026-07-18T07:41:05+05:30"
author = "Bobby Smiles"
authorTwitter = "" #do not include @
cover = "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fi.kym-cdn.com%2Fphotos%2Fimages%2Fnewsfeed%2F002%2F557%2F974%2F421&f=1&nofb=1&ipt=0a85439e63f86c6e8a7c29288fb79aea87a2f95476fe597d280a3001686679a4"
coverCaption = ""
tags = ["cybersecurity", "rambling"]
keywords = ["cybersecurity", "ai", "bug bounty"]
description = "Do humans really need to be doing cybersecurity anymore?"
showFullContent = false
readingTime = true
hideComments = false
color = "" #color from the theme settings
+++


# Background

Ever since the promotion of Claude Mythos and Opus before it (if my memory serves me right), AI has been hyped up to be able to compete with cybersecurity researchers and even surpassing them in some areas. Exploits like the copy-fail exploit were discovered through the AI and recently DirtyFrag exploit are all discovered with the help of AI. But what does this really mean? Does it mean that manual vulnerability analysis, and cybersecurity at large is finally obsolete? Do we even need humans in this field anymore? I think the picture isn't all that it seems.


# CTFs and Automation

One of the major areas in cybersecurity that has seen a drastic shift due to the rise of AI are CTFs. AI has completely changed the game, by allowing players and researchers to find exploits easier and faster than ever. CTF creators and the wider cybersecurity community at large is quite split on how exactly one should be handling this sudden shift in the game.

In my time playing CTFs this year, I've seen 3 common approaches. The first one is a more extremist one, with AI being almost completely banned from the competition. Frankly, I think this is a pretty impractical approach because people are going to use AI whether you like it or not. It is, in many ways **VERY** convenient. Which leads me to the second approach.

{{< figure src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQK1vCfo5GrIk34Mqx3eXVIfipqZXBG8GzieuaRnYULLHn_lASdZ_SLipc&s=10" alt=":(" position="center" style="border-radius: 8px;" caption="" captionPosition="right" >}}

The second approach, allows AI to be used, but by segregating those who use AI from those who do not use AI. This is done in many ways, for example in DEFCON Quals 2026, I saw a pledge system, where you brand yourself as a team who uses AI or not. I think this is a balanced approach compared to the first one considering that we're leaving it up to the historically good nature of the CTFers to clarify whether they're using AI or not. However people also tend to have 2 separate divisions for the non-AI users and the AI users, which I think is quite a faithful leap to take, considering that I can just use AI in the human division and win big 😂.

The third approach, and one that is gaining widespread traction is to just *use* AI as you please. HackTheBox had conducted a [CTF](https://www.hackthebox.com/blog/ai-vs-human-ctf-hack-the-box-results) where AI agent teams were pitted against human teams to compete for the top spot. What they found is that AI tends to be a more general type of problem solver, whereas humans tend to achieve high levels of skill in specialized domains. The AI teams started by taking the lead but soon, were just short of top 20 due to them not solving 1 question out of the 20 that were presented. What this study did find out is that, AI is just as competent as humans when it comes to problem solving, and definitely quite faster (initially at least).

# Bug Bounty and Vulnerability Assessment

I had previously made a [post](/posts/ai_bugbounty) around one year back, speaking of AI and its usage in finding bugs and other cybersecurity related activies. Since then however, AI has evolved to the point where it can find bugs in modern software that were otherwise not uncovered by cybersecurity engineers. As I had already mentioned above, 2 popular bugs are the [Copy-Fail bug](https://copy.fail/) and the [DirtyFrag exploit](https://github.com/V4bel/dirtyfrag). 

The reason these gained so much traction is that they are not recently added bugs, but rather bugs that were overlooked for many years that were hidden in the Linux Kernel. Other bugs in many other popular pieces of software have been discovered and this number only continues to rise. It's even getting to the point where large companies like Microsoft are using AI to fix bugs in their own code. 

{{< figure src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQHR4bOBhcFpeBD1FZk5OrhsKfCoYyj13cmi4CGNN04lw46sw_JguJnL_Aa&s=10" alt=":(" position="center" style="border-radius: 8px;" caption="" captionPosition="right" >}}

There are, however, statements put out about these being able to hack stuff like the pentagon or break out of its own servers and things. I'd take those with a **MASSIVE** grain of salt considering that they are unverified claims coming from companies that stand to gain **A LOT** of benefits from people believing these things.

Bug Bounty has seen a similar situation as described in [this article](https://cybernews.com/ai-news/ai-break-bug-bounty-programs/) where AI is finding a lot of valid bugs and reporting them at a very high rate, to the point where it's getting very difficult for maintainers to keep up. 

However tempting it might seem to assign this to the so-called *smartness* of AI, I think there's a more technical reason for this.


# AI and its Strengths

I recently came across [this video](https://www.youtube.com/watch?v=ty1IGU9U8_o) by [Low Level](https://www.youtube.com/@LowLevelTV) that explains the increased proficiency of AI quite well. Essentially he boils the strengths of AI down to three things:

1. Static Analysis
2. Vulnerability Research
3. General Automation

## Static Analysis

Static Analysis simply refers to analysing a piece of software to find a bug, without actually running it. This can be done via code reviews, data flow analysis, etc. At its core, AI is a text predictor. This means that it has the ability to take a piece of text and output some data with respect to it. It also can ingest **MASSIVE** amounts of code as opposed to a human being. This allows it to be way *faster* than a human when it comes to understanding an underlying codebase.

{{< figure src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fsubstackcdn.com%2Fimage%2Ffetch%2Ff_auto%2Cq_auto%3Agood%2Cfl_progressive%3Asteep%2Fhttps%253A%252F%252Fsubstack-post-media.s3.amazonaws.com%252Fpublic%252Fimages%252F74672ad2-9703-42ac-acbe-8e0cd409d5f1_551x453.jpeg&f=1&nofb=1&ipt=f3c6ba93adf4a7ce1b1120adcf563da38133c05ee2a4b9009406061a1c7466a1" alt=":(" position="center" style="border-radius: 8px;" caption="" captionPosition="right" >}}

Another thing that has to be factored in here, is the training data of the AI. This data contains countless codebases and its associated issues or vulnerabilities, which allows AI to also easily detect these patterns. Combined with the fact that it already ingests large amounts of code and understands it at a very high speed, it stands to reason that it'll be able to detect bugs quicker than humans can.


## Vulnerability Research

This is pretty much an off-shoot of the capabilities of AI in static analysis. When people write code, they focus on getting the task done with a reasonable amount of efficiency. In this process, a common thing that can occur is that a few edge-cases are not accounted for. This results in bugs popping up, which the AI is very good at detecting, because of the data it is trained on, as I mentioned in the **Static Analysis** section.


## General Automation

AI agents are also capable of automating tasks through the use of internal tools and MCP servers, as seen with the rise of Agentic AI. This allows the AI to automatically analyse code, decide the best course of action, and proceed to test further. This has resulted in massive increases in productivity and the ability to test and analyse code. This increased security capability became apparent with the release of tools like [Ghidra MCP](https://github.com/LaurieWired/GhidraMCP), Snyk Code, etc.


# Do We Need Humans Then?

Yes. Yes humans are still required for cybersecurity, and if anything, now more than ever. Humans still possess the ability to discover novel types of bugs and very convoluted zero-days. While AI is *very* good at cybersecurity, it is still not the pinnacle of what it can be. As different studies have shown, AI does things faster, but humans still are better at the job. 

{{< figure src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fpleated-jeans.com%2Fwp-content%2Fuploads%2F2024%2F05%2Ffunny-ai-memes-11.webp&f=1&nofb=1&ipt=b07ff7381a82dd5c0fd3563d5761e7f53659310b0ff0d19761be5382e9814faa" alt=":(" position="center" style="border-radius: 8px;" caption="" captionPosition="right" >}}

With all this said, it would be insensible to pretend that AI is not going to be stealing jobs or anything. In fact, it already has automated most of the low level jobs in the industry. But this is not a "**loss-of-jobs**" issue, rather it is that the skill ceiling has increased, and now more than ever, companies are asking the question, "Can I automate what this person is offering to a good degree of effectiveness?". This is what we must focus on, upskilling and using the tools at hand.


# Closing Thoughts

So, we do require humans in cybersecurity and humans still do play an integral role, not just in cybersecurity, but also tech jobs in general. So the point from my [previous post on ai in cybersecurity](/posts/ai_bugbounty) still stands. If we don't update our skillset with respect to the current market, or if we rely too much on tools that are ultimately meant to *enhance* our workflow (like AI), we will be left behind.
