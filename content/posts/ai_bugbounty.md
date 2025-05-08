+++
title = "The Rising use of AI in Cybersecurity"
date = "2025-05-08T16:31:48+05:30"
author = "LazyCSE"
authorTwitter = "" #do not include @
cover = "https://64.media.tumblr.com/3b2f12610931c334e38d95bb45667cbb/tumblr_pjpld8CiXj1qgros1_1280.jpg"
coverCaption = "Random meme I found because I'm too braindead to find an ACTUAL cover image :("
tags = ["cybersecurity", "bugbounty", "rambling"]
keywords = ["Bug Bounty", "HackerOne", "curl", "bug report", "AI", "Generative AI"]
description = "My thoughts on the recent curl bug report debacle on HackerOne"
showFullContent = false
readingTime = true
hideComments = false
color = "" #color from the theme settings
+++

# AI in Cybersecurity
Ever since the ChatGPT was released on the 30th of November 2022, it was inevitable that AI would become a crucial part of our lives. Nowadays (even though its been only 3 years since it came out), we see AI used everywhere. We write code with AI, generate images and videos with AI, summarize our meetings with AI, and with the recent introduction of tools like `Ghidra MCP`, we are seeing its increased use in Cybersecurity. But is this entirely as evil as the recent situation on HackerOne makes it out to be? I wouldn't be too quick to judge.

# The HackerOne Bug Report
Before I continue, I recommend checking out the actual bug report [here](https://hackerone.com/reports/3125832). To quickly summarize, there is a critical bug in HTTP/3 capabilities of curl, which can be leveraged to corrupt the memory, hence leading to **Remote Code Execution**, or **RCE** in short. 

In the initial stages of reading this report, all seems normal and it seems like a standard report for a high severity bug. But reading further, it begins to seem more and more suspicious (to say the least). Firstly the curl staff member mentions that the patch is not applicable here and asks a question, to which the reply looks ***SUSPICIOUSLY*** like it's AI generated markdown. The user provides the steps to ***APPLY*** a patch, without actually providing the patch in question.

Some more discourse later, one of the other curl staff members drops a banger about this part of the report:
```
Analysis shows:
	- Return address overwritten
	- Stack recursion at ngtcp2_http3_handle_priority_frame
```

Staff comments:
```
There is no function named like this in current ngtcp2 or nghttp3. 
Please clarify what you talk about. Which versions of ngtcp2 and nghttp3 
did you find the problem in?
```

The function he was talking about, `ngtcp2_http3_handle_priority_frame` does not exist. This, reveals the fundamental problem with relying completely on AI to do the heavy lifting on a high-skill job.

# So What's the Issue?
AI generated reports are nothing new. There have been many reports, made using AI over the years and so far, according to the founder of the curl project, Daniel Stenberg, no valid bugs have been reported by these so-called `AI generated slop` reports (read his full linkedin post [here](https://www.linkedin.com/posts/danielstenberg_hackerone-curl-activity-7324820893862363136-glb1?utm_source=share&utm_medium=member_desktop&rcm=ACoAAFdg9CQBp_M-Tja0o8oTrYihjhutFcn-XHw)). It is not uncommon to run into situations where the AI hallucinates things that do not exist in order to fulfill the task given to it by a user.

{{< figure src="https://assets.aboutamazon.com/dims4/default/e73bc85/2147483647/strip/true/crop/4093x2304+7+0/resize/1240x698!/quality/90/?url=https%3A%2F%2Famazon-blogs-brightspot.s3.amazonaws.com%2F36%2F59%2Feba4adcc4f88a972b5639ed1dde0%2Fadobestock-712831308.jpeg" alt=":(" position="center" style="border-radius: 8px;" caption="Generic AI concept art I randomly found online" captionPosition="right" >}}

This is a worrying trend as in the recent years, the number of these reports have only been increasing. The problem is that the people behind triaging and validating a submission are human, and, it takes time. Triaging a submission is no simple task and people put a lot of time into this. Simply spamming AI-generated reports on these platforms only makes this job harder, as:

- The report cannot be ignored in the off-chance that it reports an actual exploit.
- Producing these kinds of reports takes very little time and the staff will not be able to keep up with the speed of incoming reports, resulting in lesser security.

The curl founder called it a `DDoS Attack` against curl due to this. And, he's not wrong.

# What Causes this Issue?
I think the major problem with all this, is rooted in the fact that many people, beginners and professionals alike, have begun to **SUBSTITUTE** their workflow with AI, as opposed to **AUGMENTING** their workflow with AI. 

AI is not 100% accurate, it never has been nor will it ever be, as it stands. AI is trained to give answers that **SEEM** correct. Obviously, this is not intentional, rather it is a consequence of how the current methods of training these AI models work. At the end of the day, the AI is only doing it's job. It is us, as humans, whose job it is to validate this before making a submission.

# But is AI completely Evil?
No, absolutely not. I am not going to pretend that I never use AI for my tasks. I do, and I think the benefits to having something like an LLM enhancing your workflow shouldn't be slept on. However, the key distinction is that AI **ENHANCES** my workflow, it is not my **ENTIRE** workflow. What I mean is that say, for example, in a project, I won't be *vibe coding* that whole project using some random LLM, I would rather be using it to write boilerplate code, find resources online, or as a last resort, suggest fixes to bugs in the code. 

And I feel that a similar approach must be adopted by the wider community at large. I am not saying my approach to this is perfect, not at all, but rather the knowledge of **Enhancement** vs **Substitution** must be more widespread.

{{< figure src="https://i.redd.it/lets-face-it-we-all-thought-auto-had-cared-about-wall-e-v0-bq3furftnb7e1.png?width=1600&format=png&auto=webp&s=710e4cbdf355ff8e96da8e07b1c80db3d9ef691d" alt=":(" position="center" style="border-radius: 8px;" caption="The classic AI villain, AUTO from WALL-E" captionPosition="right" >}}

It is due to this same pitfall, that vibe coding (a term which I *absolutely* hate by the way), is gaining more and more traction, when in reality, you can simply learn to code, put in the hours, and write **FAR** better applications than an AI ever could. Even better, you could double that productivity, by *then* finally using AI to enhance your already existing workflow, making this endeavour all the more worth it.

# Closing Thoughts
This situation on HackerOne clearly demonstrates the flawed mindset that many people have started to adopt with regards to the usage of AI and a shift in this mindset is necessary if the usage of AI in high-skill fields is to be a net-positive. However, not all of this is bad, and if anything, we should learn from the pitfalls clearly demonstrated by this incident and continue to improve in our respective disciplines. 

Have a nice day! :)