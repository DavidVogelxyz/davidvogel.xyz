---
title: "Getting Rusty"
date: 2023-11-30T22:24:38-05:00
tags: ['home-lab','other']
---

{{< context >}}

![Rust banner](/images/rust-banner.png)

## Introduction

This article tells the story of how I found Rust, the true "first programming language" that I chose to learn. As I made progress reading through "The Book", I created a Git project called [fibonacci](https://github.com/DavidVogelxyz/fibonacci), a CLI program that calculates the "nth" position of the Fibonacci sequence. I also created a Git repository called [Rust collection](https://github.com/DavidVogelxyz/rust-collection), which contains a bunch of scratch projects I worked on during this time. Both projects can be found on my GitHub, and are directly accessible by following the links.

---

## Time to Get Rusty

By the end of 2023 October, I was still in the process of choosing the "first programming language" that I would dedicate a solid amount of time to learn. After trying out [Python and TypeScript](/home-lab/other/python) for a time, and not really feeling like either was right for me, I went back to my Bash projects, working to [improve my `debian-dwm` installer](/home-lab/other/debian-dwm). But, even as I made more progress with Bash, I still felt that it would be good to start learning "a real programming language". As I mentioned in a previous article, I "wanted a language that would punish my lack of understanding, and would force me to better appreciate what I was trying to tell the computer to do". Put another way, I wanted a language that would make me use all the knowledge I had gained from [thePrimeagen's Data Structures and Algorithms course](/home-lab/other/theprimeagen-dsa-course). I forget exactly how I stumbled upon it; but, by the end of 2023 October, I finally found a language that would give me all of that: Rust.

One of the benefits of learning Rust at any stage of a programmer's journey is that there are a ***TON*** of resources available. There's "[The Book](https://doc.rust-lang.org/book/)", which is an online collection of documentation put out by the Rust Foundation, explaining exactly how to get started. There's "[Rust by Example](https://doc.rust-lang.org/rust-by-example/)", which was also created by the Rust Foundation, and is almost a different version of "The Book" that requires less reading, and has more examples. There's also "[Rustlings](https://github.com/rust-lang/rustlings/)", which is a compilation of practice examples, essentially in the form of a game. Despite knowing no Rust at the time, I decided to start with "Rustlings".

## Rustlings

I started to learn Rust by working through Rustlings. Because of my lack of Rust knowledge, and lack of coding experience in general, I decided to do Rustlings in a (likely) unorthodox way -- I had a YouTube video walkthrough playing at the same time. I attempted every problem by myself at first; but, I quickly allowed myself to view "the answer". In retrospect, I think this was the perfect way (at least, for me) to get introduced to the language. It provided a very fun way to get started, and it allowed me to get a wide view of how Rust worked and what it had to offer, without getting too bogged down in understanding what I was doing. This allowed me to confirm my major suspicion: yes, this was going to be a language where having a solid foundation of data structures would be extremely useful.

While my first go-around with Rustlings came with a large amount of hand-holding, it was my intention that it would serve only as an introduction, and nothing more. Once I got that introduction, my plan was to read through "The Book" in its entirety, and get a much deeper understanding of Structs and Enum and all the rest. After I completed "The Book", I would return to Rustlings, and I would do it again from scratch. But, that next time, there would be no hand-holding. If I needed help, the solutions would be found in "The Book". I would have to read documentation, and read my own code, to figure out what was wrong.

[![Rustlings completion](/images/rustlings-completion.png "Rustlings completion")](/images/rustlings-completion.png)

With my first completion of Rustlings under my belt, it was time to start reading "The Book". However, I did take a short break from Rust to work on my `debian-dwm` project. While what I learned from Rust wasn't *directly* applicable, I now had a far better understanding of functions, and how to write them. This *was* directly relatable, and I used that understanding to perform a [major refactoring of the `debian-dwm` project](/home-lab/other/debian-dwm).

## The Book, and `fibonacci`

After completing the `debian-dwm` refactor, I was more enthusiastic than ever about learning Rust and becoming a better programmer. So, I started at the beginning of "The Book", and began to work through the chapters.

I was only a few sections before I was presented with a stopping point, where I was told that I knew "enough to make a small program". One of the suggestions for a project was to write a program that calculated the Fibonacci sequence. I immediately got excited by the prospect, as I began to think about all the different ways I could tackle writing the code. Specifically, I was pumped to write the algorithm that would calculate the Fibonacci. I was already envisioning a number line that would be looped over. The loop would take two numbers (call them "l" and "r", for left and right), add them together, and then "step up" to the next set of numbers. The loop would continue this process until it reached the given index, and then spit out the sum. I took a crack at it, and after a bit, I had a piece of code that worked!

The `fibonacci` project was great for so many reasons. One of the primary reasons was that it gave me something to continually return to as I made more progress in "The Book". When I learned how to write a "for loop", I swapped it in for the "while loop" I had been using. When I learned how to write module files, I moved the code from "main.rs" to a "fibonacci.rs" file. Then, when I learned about library files, I moved the code over to a "lib.rs" file. The process continued:

- I learned how to write tests, so I added some to the "lib.rs" file.
- I was taught how to accept command line arguments as inputs, so I updated my program to accept arguments.
- As I learned how to write better code, I began to abstract out functions to create simpler functions.

One thing that's worth shouting out is the following: I noticed that there were insufficient logic regarding ordinal numbers ("1st", "2nd", "3rd", etc). Specifically, "1st, 2nd, 3rd" worked correctly, and everything else received "th". Unfortunately, this didn't cover "21st, 22nd, 23rd, 31st, 32nd, 33rd, etc". I thought the simple solution was to have the program read the last digit and output based on that. But, that logic would fail at "111th, 112th, 113th". In addition, I found out that grabbing the last numeral in my integer was more complicated than originally assumed. So, I thought about it, and brought together everything I learned in order to come up with a solution. And then it came to me -- I can use modulo (specifically, mod 10), and that would return the last digit! I used the modulo operation, in combination with some clever logical operators, to write a solution that would encompass all cases.

I'm not sure that it was "The Book"'s intention that I keep returning to an introductory project and keep refining it. However, the `fibonacci` project began a home for my development, and one of the best indications of my progression in learning the fundamentals of Rust. While it's honestly nothing special, it serves as a demonstration of the improvements in my understanding as I worked through all of the chapters, almost more so than the other practice problems I worked on in the other chapters.

## Conclusions

I'm honestly not sure that I ever finished "The Book". I worked through it until the end of 2023 November, when I became distracted by Advent of Code, which I saw as another opportunity to take what I had learned and practice more Rust. Soon after, I started a new job as a System Administrator in the middle of 2023 December, and that took my focus away from learning to code. But, I came back to Rust on occasion throughout 2024 -- the "modulo" story only happened at the end of 2024 May. Despite my attention being split between more projects than ever before, I was happy that I began to deep dive Rust for the time that I did. As compared to my experience with Python and TypeScript, it felt like the right language for me to start with. It gave me everything that I was looking for:

- I wrote command line programs that I could easily run on a Linux computer.
- I made use of a good amount of the data strucutres and algorithms that I had learned with thePrimeagen in 2023 August.
- It was a fair level of "difficult", in that I felt rewarded for taking breaks to "learn how things worked underneath the hood".

In conclusion, after many months of working to find a coding language that I would be happy to learn and make progress in, I found that reality in Rust.
