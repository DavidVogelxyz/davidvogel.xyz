---
title: "Getting Better at Bash"
date: 2023-11-17T22:24:38-04:00
tags: ['home-lab','other']
---

{{< context >}}

![Bash banner](/images/bash-banner.png)

## Introduction

This article tells the story of my progress at learning how to work better in Bash. As I grew and learned, I created a Git repository called [Bash collection](https://github.com/DavidVogelxyz/bash-collection), which contains a bunch of scratch projects I've worked on -- this project can be found on my GitHub, and is directly accessible by following the link.

---

## My First Refactor

Starting at the beginning of 2023 August, I had spent a good amount of time learning the basics of how to code. In August, I took a [data structures and algorithms (DSA) course](/home-lab/other/theprimeagen-dsa-course), finished the first pass of the [`debian-dwm` project](/home-lab/other/debian-dwm), and wrote [my own Neovim configuration files in Lua](/home-lab/other/neovim). In September, I began playing around with [Python and Typescript](/home-lab/other/python), and made more progress on `debian-dwm` and my Neovim configs. I had even dipped my toes into [Rust](/home-lab/other/rust) by working through Rustlings. But, it was now 2023 November, and I was looking to do something concrete that would cement the learning I did over the past few months.

After reviewing the current state of my `debian-dwm` project through the lens of what I had learned, I saw some glaring problems with it. While I had implemented some basic "for loops" and variables in early 2023 September, which made the code a lot cleaner, I was having issues with variable expansion within some of my commands. While there were other ways to fix my mistakes, such as exporting variables so they would be accessible throughout the code, I realized that using functions would be another way to resolve the matter. As an aside, this was something that Luke Smith had done with his LARBS project; but, I was too novice at the time to implement functions correctly. Now, with what I had learned, I felt confident that I could make those improvements to my project.

Most of the major changes that I made during this refactor were to make the scripts easier to read. Examples of these changes include:

- I had some commands that were unnecessarily long, and would perform some of the same actions as other commands.
    - In these cases, I decided to write functions that could be called by other commands.
    - The added benefit of doing this was, when a change needed to be made, I only had to make the edit once, and it would be reflected in every invocation of that function.
    - This also made it much easier to write conditional statements that, if true, were able to do more complex functions, without impacting readability.
- I added sections to my scripts.
    - Specifically:
        - The first section would be the script-wide variables that I was setting.
        - The second section contained all the functions that I wrote.
        - The third section was the "actual script", which included all of the functions that were actually being invoked.
    - This made it really easy to read the script, especially in Vim.
        - I could easily jump to the bottom and read *exactly* what was being run and when.
        - If I had a question about a function's definition, I could use the keymap `gd` to jump directly to the function and see what it was doing.
- I wrote some functions to take in files as arguments.
    - This allowed me to break off the package list from the script that installed packages, and create a separate "package-list" file that was far easier to read and edit.

The product of this refactoring process was a set of scripts that were far easier to read and debug. While the project was far from perfect, I was able to massively improve the code I wrote only a few short months ago, and make it *that much better*, all because of the different things I had learned in the preceeding weeks. Content with the changes I had made, I committed the changes on 2023 November 12 and started reading through "The Book", a set of documentation that would teach me the foundations of writing code in Rust. But, that commit had a problem that I wouldn't notice until days later.

## Indirect Variable Assignment

A couple of days into beginning to read through "The Book", I needed to set up a new virtual machine (VM) with `debian-dwm`. So, I cloned the git repo I had been working on and ran the installer. However, I was met with a funny error: the `echo` commands that I would use to tell the end user that a package needed to be installed before continuing, were instead printing nothing in place of the `$pkg` variable. When I went to debug the scripts, I came across the problem: the variables weren't being expanded correctly. As I looked more into the issue, I found out that it had a name: "indirect variable assignment".

As I understand it, the problem had to do with my use of single quotes " ' " versus double quotes " " ". While I know more than I did at the time, and I could have used double quotes had I escaped them correctly (using " \ "), I instead went a different route. I solved the issue by abstracting out the `echo` command into a new `installcomment` function, which *could* correctly expand the variable, despite using single quotes. While I learned more since this incident, and I realize that a simple read of the `bash` man page would have averted this issue entirely, it was a great experience for me. It gave me an opportunity, and a reason, to troubleshoot a more complex issue in some code that I had written, and to figure out my own way of resolving the problem. In addition, it was an indirect way for me to learn to abstract out more of m repeating code into simpler functions that could be invoked by other commands, rather than having repeating commands that do the same thing. In either case, it was one more experience added to my journey that helped me to learn better the tools with which I was working.

## Conclusion

While I was working during 2023 November both on improving my Bash skills and learning Rust, I can safely say as of writing (2024 August) that I've used more Bash than I have Rust. That's simply a function of all the projects that I've worked on since this time, and there being more utility for Bash than there was for Rust, especially at my level of expertise with both. Even though I've made even more progress in Bash since this time period, this article highlights an important part of my journey and development. A few years ago, I couldn't even read a Bash script. Only a few months before, I was writing scripts that were essentially just a long list of commands, one after the other. But, by 2023 November, I was starting to get a good enough handle on Bash that I could write more complex scripts. These lessons would become foundational for all the progress I would make in the months to come.
