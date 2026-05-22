+++
title = "Privacy in the Modern Digital Landscape"
date = "2026-05-21T12:53:04+05:30"
author = "Bobby Smiles"
authorTwitter = "" #do not include @
cover = "https://ik.imagekit.io/LazyCSE/modern_privacy/privacy_meme_cover.png"
coverCaption = ""
tags = ["cybersecurity", "rambling", "privacy"]
keywords = ["security", "privacy", "ai", "data breach"]
description = "How do we maintain privacy in an increasingly surveilled digital age?"
showFullContent = false
readingTime = true
hideComments = false
color = "orange" #color from the theme settings
+++

# The Current Scenario

The modern internet feels like a mess. From the overly *enshittified* quality of products to AI being stuffed down our throat at every turn, the internet has, in many ways, lost its initial charm and simplicity. Lately a **LOT** of privacy violations have come our way too, from AI crawlers indiscriminately taking online content without consent, to sites like LinkedIn *literally* tracking user activity and selling it off to cybersecurity companies, the list just doesn't end.


In light of such situations, it becomes more crucial than ever to secure our own data and not let these companies have their way. In this article, I want to highlight the current landscape and talk about some of the things I personally do to ensure I am not being tracked through every step of my internet activity.

# The LinkedIn Debacle 

{{< figure src="https://ik.imagekit.io/LazyCSE/modern_privacy/meme1.png" alt=":(" position="center" style="border-radius: 8px;" caption="" captionPosition="left" >}}

I'll start this off with the recent LinkedIn controversy that was making the rounds on the internet. Basically, LinkedIn users found out that they are being tracked by the site, for the use of over 6000 common extensions, ranging from job-search extensions to productivity software. This was dubbed BrowserGate, and you can get a lot of the information I'm about to detail from [the official site](https://browsergate.eu/).


The thing is, its already a known fact that LinkedIn tracks browser extensions. So why is this causing so much outrage? It is the simple fact that LinkedIn actually never mentions **ANY OF THIS** in its privacy policy. They just run the embedded JS that does the tracking, and just *track*.


This is blatantly illegal under laws and regulations. To keep it brief, most laws and regulations state that it is fine to take data like the name, email and other basic information, but beyond that the company ***MUST*** ask for consent. This is absolutely not done by the site and worse, the data is transmitted to third-party companies, again without the consent of the user.


But which browsers are affected? It was reported that all chromium based engines were especially susceptible to this script but firefox and Firefox-based browsers weren't.


So just use Firefox :)

#  Telemetry and Data Collection in Big Tech

Data collection in major applications has existed for a long time. By now its a known fact that products like the Google Search Engine, Windows, Amazon, Instagram, and other popular services all collect user data either for advertising purposes or for monetization. What's worse is that many of these services are taking our data to train their proprietary AI models, which runs a very real risk of leaking said data through jailbreak or prompt-injection attacks. This is compounded by the use of AI agents like OpenClaw, which poses a major security risk to data privacy as AI models are just prone to leaking data under certain conditions, as observed in the [Vercel Data Breach](https://pushsecurity.com/blog/unpacking-the-vercel-breach).

But where am I going with all this?

# Privacy Focused Tooling

There are quite a few alternative services that we can make use of to improve our privacy. I'll be talking about some of the tools that I commonly use, for web browsing, emails, cloud storage and more. I want to mention beforehand that I am not going to be talking about self-hosting services here, just the already existing online services that you can use.

{{< figure src="https://ik.imagekit.io/LazyCSE/modern_privacy/meme2.png" alt=":(" position="center" style="border-radius: 8px;" caption="" captionPosition="left" >}}

# Web Browsing

This might be the easiest and most simple switch to make. Just yesterday, Google held [Google I/O](https://io.google/2026/), where they announced that Google Search will be pushing AI generated content higher on the search results. What brought them to cook-up this "amazing" idea I don't know, but I think it's all the more reason to start switching.


Personally, I recommend either [Brave Search](https://search.brave.com/) or [DuckDuckGo](http://duckduckgo.com/). Brave tends to deliver slightly better search results since it ranks pages based on popularity, but its index size is smaller than DuckDuckGo.

> Index Size here simply means the amount of pages the search engine indexes. It requires a lot of computing power so really only the Tech Giants actually have the entire internet indexed.

DuckDuckGo, on the other hand uses a combination of multiple indices. So its index size is *way* bigger and it delivers a pretty decent search result quality. But it is slightly worse than Brave at delivering results and sometimes you'll have to be a bit more specific with your search to get what you want. For absolute privacy though, DuckDuckGo search seems to be a bit better than Brave. I use DuckDuckGo a bit more frequently than Brave because of a couple of features it offers which you'll see as you read on :)

# Cloud Storage

{{< figure src="https://ik.imagekit.io/LazyCSE/modern_privacy/meme2.webp" alt=":(" position="center" style="border-radius: 8px;" caption="" captionPosition="left" >}}


[Proton Drive](https://proton.me/drive) and [Mega.nz](https://mega.nz/) are good options in this space. Proton drive is slightly better if you want an experience as close to google drive as possible, with its free tier offering 5GB of storage. Mega.nz offers 20GB of storage in its free tier and if you're willing to learn the slightly different interface, it's probably the better option, in terms of pure storage capacity.


However, Proton is much more generous when you hit the limits on the free tier account, while Mega is reported to just freeze your account with no warning. So if you're good at managing and tracking your storage well, use Mega otherwise I'd recommend Proton.

# Web Browsers

This is a popular topic in many mainstream forums so I'd imagine if you're reading this article, you'd be aware of the options I present here. [Brave Browser](https://brave.com/) is a very accessible, privacy-focused browser to use. It features a built-in adblocker and a TOR mode to browse the web using onion routing. 


[DuckDuckGo browser](https://duckduckgo.com/windows) is also one that I quite like though I personally feel features-wise it lags a little bit behind Brave. The real selling point for me with the DuckDuckGo browser is the fire button. It deletes all open tabs, sessions, web caches and other data the website or browser may store. This helps ensure that our digital footprint is erased with pretty much no ambiguity.

# Emails

This is the part I had the most fun setting up. I use a less well-known email called [cock.li](https://cock.li/) (hilarious name I know 😂) paired with [DuckDuckGo Email Protection](https://duckduckgo.com/email/) for forwarding emails. It is quite easy to setup and DuckDuckGo also allows you to reply through the `@duck.com` email address you setup for forwarding which is just crazy 😨. One thing I have observed from time-to-time though is that messages sent through the forwarding address can take an unusually long time to reach the recipient. It's not frequent whatsoever but it could happen.

{{< figure src="https://ik.imagekit.io/LazyCSE/modern_privacy/meme4.png" alt=":(" position="center" style="border-radius: 8px;" caption="" captionPosition="left" >}}

For the email client, you either have the option of self-hosting a webmail client like [RoundCube](https://roundcube.net/) (I know that I said I wouldn't talk about self hosting, but in this case it would be remiss of me not to mention it since this is a VERY popular option), or using a desktop client like [Eppie](https://eppie.io/). I personally use a terminal-based client that I built myself using Go. If you guys like, I could show you how to build one yourself :)


# Conclusion

At the end of the day, privacy is taking a backseat on the internet, especially in the hands of many of the major tech providers. It isn't in our hands to control the decisions that are taken at the very top, but what we can do is take preventative and mitigative steps to ensure that we, as users, stay in control of our data.  


Hope you enjoyed reading this article :)
