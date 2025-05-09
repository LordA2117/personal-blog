+++
title = "Bellingcat Open Source Challenge: Back In Time - Walkthrough"
date = "2025-05-09T22:23:16+05:30"
author = "LazyCSE"
authorTwitter = "" #do not include @
cover = "https://i.imgflip.com/xtpsi.jpg?a484872"
coverCaption = "Random cat meme cuz why not :)"
tags = ["osint", "walkthrough"]
keywords = ["osint", "gralhix", "bellingcat", "geolocation", "open source"]
description = "My walkthrough to the new back in time series of challenges by bellingcat"
showFullContent = false
readingTime = true
hideComments = false
color = "" #color from the theme settings
+++

# Bellingcat - Back In Time walkthroughs

Bellingcat recently released their `Back In Time` series of challenges authored by [Sofia Santos](https://gralhix.com/list-of-osint-exercises/). I had a lot of fun solving these and I hope you did too. Here's a walkthrough of how I tackled each of these challenges.

Hope you learn through these walkthroughs as much as I did solving these challenges.

## Fresh Faced: Finding the Founder

{{< figure src="https://challenge.bellingcat.com/assets/Sofia_Santos_1-BplhodW_.png" alt=":(" position="center" style="border-radius: 8px;" caption="Problem Image" captionPosition="right" >}}

So the question tells us that the founder of Bellingcat, Eliot Higgins, was featured on many news outlets for his groundbreaking discoveries in the year 2013. We need to find the YouTube video from which the newspaper clipping was taken.

The first and most obvious lead we have is the caption in the image. Let's put this into [Google Translate](https://translate.google.com/?sl=auto&tl=en&op=translate) to see what language it is.

{{< figure src="https://ik.imagekit.io/LazyCSE/back_in_time_cbc/cbc_back_in_time/ss1.png" alt=":(" position="center" style="border-radius: 8px;" caption="Google translate for the caption in the image" captionPosition="right" >}}

We can see that the language was detected as **Croatian**. Now from here, I didn't find any leads, so I looked into the [Wikipedia page on Eliot Higgins](https://en.wikipedia.org/wiki/Eliot_Higgins). Reading this page, we can see that Wikipedia mentions some [non-English sources](https://brown-moses.blogspot.com/2013/04/the-brown-moses-blog-fundraiser-launches.html). Let's check this page out and see what's in it

{{< figure src="https://ik.imagekit.io/LazyCSE/back_in_time_cbc/cbc_back_in_time/ss2.png" alt=":(" position="center" style="border-radius: 8px;" caption="Non-English sources listed in brown-moses" captionPosition="right" >}}

Over here, we can see a [Croatian news article](https://www.vecernji.hr/vijesti/kako-sam-otkrio-da-hrvati-salju-oruzje-u-siriju-532428), which aligns with our earlier finding of the language on the news clipping. The site didn't contain any sort of link to a YouTube video, just the same picture as we were given in the question.

So the next thing I did was to check the journalist who interviewed Eliot Higgins. His name was **Tomislav Krasnec**. So I just searched `Tomislav Krasnec Eliot Higgins` in the Google videos section and got the interview.

The answer is simply the video code.

{{< figure src="https://ik.imagekit.io/LazyCSE/back_in_time_cbc/cbc_back_in_time/ss3.png" alt=":(" position="center" style="border-radius: 8px;" caption="Search result for Tomislav Krasnec's interview with Higgins" captionPosition="right" >}}

---

## Training Time: There's a lot to learn.

{{< figure src="https://challenge.bellingcat.com/assets/Sofia_Santos_2-BWtvTpYQ.jpeg" alt=":(" position="center" style="border-radius: 8px;" caption="Problem Image" captionPosition="right" >}}

So we're asked to do some cool indoor geolocation on this image. We have to find the room in which this picture was taken. Another hint is that the image is credited to **ARIJ network**. We are also told that this workshop was conducted in 2017 so that's gonna be a cool lead as well.

So just googling, `Christiaan Triebert Workshop 2017` yielded this [post](https://x.com/trbrtc/status/928688231549423616) on X.

{{< figure src="https://ik.imagekit.io/LazyCSE/back_in_time_cbc/cbc_back_in_time/ss4.png" alt=":(" position="center" style="border-radius: 8px;" caption="Searching for Christiaan Higgins workshop in 2017" captionPosition="right" >}}

This didn't give much information. So instead I tried using Google Dorks to find the workshop.

By Google dorking this `intext:"December" intext:"2017" intext:"Christiaan Triebert" intext:"workshop"` I found that the event was *ARIJ 10th Annual Forum* and in their website we had an address of **Mövenpick Resort & Spa Dead Sea | Dead Sea Road, 11180**

{{< figure src="https://ik.imagekit.io/LazyCSE/back_in_time_cbc/cbc_back_in_time/ss5.png" alt=":(" position="center" style="border-radius: 8px;" caption="https://arij10thannualforum2017.sched.com/list/simple" captionPosition="right" >}}

So from finding this I looked at the rooms available in the hotel in this [part](https://movenpick.accor.com/en/middle-east/jordan/dead-sea/resort-dead-sea/meeting-rooms.html) of their website. Through that I found the answer to be `The Grand Ball room`.

---

## Creating Community: A new place to connect.

{{< figure src="https://challenge.bellingcat.com/assets/Sofia_Santos_3-B0DbysB3.png" alt=":(" position="center" style="border-radius: 8px;" caption="Problem Image" captionPosition="right" >}}

Ok, so here we will have to do a ***little*** bit of scripting, nothing too complicated, just some copying and pasting.

By just using this Google dork `intext:'We finally got around to creating a bellingcat Discord server"` we can find the [post](https://x.com/bellingcat/status/1260211332437213184?lang=en) on X. get this time: `7:42 PM · May 12, 2020`. Note that this time will be displayed differently based on what timezone you fall under.

{{< figure src="https://ik.imagekit.io/LazyCSE/back_in_time_cbc/cbc_back_in_time/ss6.png" alt=":(" position="center" style="border-radius: 8px;" caption="Twitter post containing the bellingcat server announcement" captionPosition="right" >}}

So once I found the post, I joined the Discord and used this [method](https://www.reddit.com/r/discordapp/comments/5wl8ny/how_to_find_the_age_of_your_server/) to get the age of the server.

So, this method has the following steps:
- Enable developer mode on your Discord.
- Open Discord in your browser and open the Inspector tab on your browser.
- Paste the following code snippet in your browser.

```javascript
new Date("709752884257882135"/4194304) + 1420070400000
```

{{< figure src="https://ik.imagekit.io/LazyCSE/back_in_time_cbc/cbc_back_in_time/ss7.png" alt=":(" position="center" style="border-radius: 8px;" caption="Result of the js code" captionPosition="right" >}}

This gives us this timestamp: `Tue May 13 1975 18:34:34 GMT+0530 (India Standard Time)1420070400000`
Now, this will be different according to your timezone, but on doing the math we get the time to be 68.

---

## Future Plans: A timely document.

So we're told that Bellingcat published a document nearly 2 years after they registered.


So I found the pdf by using this Google Dork: `intext:"bellingcat" intext:"future plans"`. Since bellingcat was registered in 2018, it tracks that this [result](https://www.bellingcat.com/app/uploads/2020/06/Bellingcat-Policy-Plan-2019-2021.pdf) was the right one.

Now there is no author explicitly listed in the pdf, neither do I wanna read the whole pdf. So, I decided to take a look at the [pdf metadata](https://www.pdfyeah.com/view-pdf-metadata/), which revealed that the author was **Aric Toler**.

Great, so we have one part of the challenge solved. Now let's see if we can get all the articles he published around 2019-2020.

So on searching `bellingcat.com aric toler` I found this [link](https://www.bellingcat.com/author/arictoler/). I scoured every article until I got [this one](https://www.bellingcat.com/resources/how-tos/2020/04/15/how-not-to-report-on-russian-disinformation/). The last word of this article is the answer.

---

## Toolkit Tracing: Tool tips new and old.

This was the easiest question of this release. We are asked to find a missing document in an older edition of the Bellingcat Online Investigations toolkit released in the year 2020.

I used this Google dork to search it up: `intext:"Guides & Handbooks" intext:"2020" intext:"Bellingcat"`

{{< figure src="https://ik.imagekit.io/LazyCSE/back_in_time_cbc/cbc_back_in_time/ss8.png" alt=":(" position="center" style="border-radius: 8px;" caption="Result of the Google dork" captionPosition="right" >}}

You can find the actual document mentioned in the question [here](https://p.avmedianow.com/b/e/bellingcat-s-online-investigation-toolkit-242.pdf). 

In this document, in the `Guides & Handbooks` section, you can find this [document](https://docs.unocha.org/sites/dms/Documents/FEAT_Version_1.1.pdf). As it turns out, it is inaccessible. So the obvious first step was to simply check for a snapshot of this document in the [WayBack Machine](https://web.archive.org/).

{{< figure src="https://ik.imagekit.io/LazyCSE/back_in_time_cbc/cbc_back_in_time/ss9.png" alt=":(" position="center" style="border-radius: 8px;" caption="Result of the wayback machine search" captionPosition="right" >}}

Once I got to the wayback machine, I simply entered the URL and voila! there it was. So we'll simply navigate to page 39 of the document and get the first hazard listed.

---

Hope you found this as useful as I did. 

Have a nice day! :)