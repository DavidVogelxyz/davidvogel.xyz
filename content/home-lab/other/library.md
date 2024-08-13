---
title: "Building a Library of Documentation"
date: 2023-08-23T21:24:38-04:00
tags: ['home-lab','other']
---

{{< context >}}

## Introduction

This article tells the story of how I wrote my own [Git repository for guides](https://github.com/davidvogelxyz/library) -- this project can be accessed by following the link to my GitHub.

---

## Documenting my progress

The more I've made progress in my IT and home lab journey, the more I've noticed a certain trend regarding documentation. Often, for whatever project I'm working on, there is a common breakdown with resources I use:

- There is a primary resource (official documentation, etc) that gets me about 90% of the way through the project.
- There is a secondary resource that gets me another 8% of my progression.
- Finally, there's a third resource that resolves some issue I'm having, and that resource gets me the last 2% of the way through.

The percentages may vary, but there are almost always primaries I use, with some other resources assisting me with issues along the way. I usually make a point of bookmarking all those resources, though I'll also bookmark other resources I used throughout the process. Once I've deployed whatever service it is, I won't touch the project, or its resources, for about 3-6 months.

Eventually, I'll come back to the project, and this is where I began to notice problems. I can almost always find the primary resource, and I can usually find the secondary resource. However, I often have immense trouble finding that obscure post buried deep on some message board. Even despite having the bookmarks saved, I'll have to repeat the process of digging through the bookmarks to find that post. And, if I don't have the post bookmarked, then I have to try and remember what search query I used to find that page, etc. It can be a real hassle, and it's especially irritating when it's regarding a problem for which I already found a solution.

So, I decided in 2023 August to take it upon myself to document the steps I was taking. I was absolutely tired of struggling to find the resources I used in the past, and I knew that keeping records of the process would allow me to more rapidly deploy projects I had already completed. I imagined it would be helpful to have a single resource that, if I followed the outlined steps, would get me 100% completion every time. I also thought that reading documentation written by me, for me, would be far easier to read and parse than some article written by someone else. This initiative became my Library git repository.

## The "Library" repository

While it started out pretty basic, with some guides on installing Arch Linux and Debian (as well as some other troubleshooting tips), my Library repository has developed in an ever growing assortment of documentation on many of the projects I've completed. While it's a time-consuming process to document the working steps, and it's meant that I complete projects slower than I would if I skipped the write-ups, it has paid dividends in excess of the effort I've put in to maintain it.

Maintaining the documentation on GitHub has had extraordinary benefits. While I didn't know much about `git` when I first started, having version control on my guides since the beginning has enabled me to easily view past versions of the guides. Whether it be looking back at the original versions of guides and seeing how much they've changed, or making an adjustment that didn't work out as intended and reverting the change, using `git` to manage a large store of documents has made it really easy to work with a constantly developing set of materials. Also, while this was never the expectation, I have since had co-workers ask me how I set up certain services and servers, and it's been really awesome to be able to direct them to guides I wrote. Mostly, my guides have been complete enough to get them to the point where they were able to set those same services up, without having to debug the issues I ran into. On occasion, something I added to the guides wasn't as clear as it could have been. While the guides were originally written for me, and I could usually understand my own shorthand, learning to write documentation more clearly has benefitted everyone involved. It's definitely inspired me to continue maintaining the "Library" as I learn more.

As of 2024 August, almost an entire year later, I now have guides on so many different projects I've worked on. I have writeups on 9 different server projects, how to set up default server configurations for both Debian and Alpine Linux, as well as troubleshooting docs on various issues I've encountered. I have also improved a bunch of the content that I've posted throughout the year, and made the guides more readable and useable; not just for me, but for anyone who uses the documentation.
