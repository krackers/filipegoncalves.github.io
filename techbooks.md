---
layout: page
title: Technical Books
---

## Technical Books

This is where you can learn about what I am currently reading and what I read in the past. It is also a placeholder for my reviews and thoughts on each book I have on my shelf. I am usually very picky about the books I buy, so you'll find most of my reviews to be mostly positive, except on very rare occasions.

### Currently reading

* *Advanced Programming in the Unix Environment* - The UNIX / Linux bibble. System calls, libraries and other interfaces that work together to bring the power of Linux to a machine are all listed here. The book is about programming in C, but it's also a great resource to learn about the UNIX philosophy and system administration. What is a filesystem? How is it organized? How does it work? How is I/O implemented? What exactly happens from the moment you press the power button until bash is running and accepting commands? This book has evolved over the years and gained a lot of attention; it is a great reference manual for experienced programmers.

### In the past

If you're deciding whether you should buy a specific book, you can check this list of books that I read in the past and learn from my experience. For each book, I provide a quick review. The listing is in chronological order; books on the top of the list are the most recent reads.

<del>So far, I loved every technical book that I've read</del>. Oops - that's not true anymore. I've had my first bad experience. I have been stumped by a crappy technical book. Well, that's life!

* **Data Structures and Algorithms Made Easy** [Narasimha Karumanchi] - **DO NOT READ THIS CRAP**. It's a waste of money. Don't buy it. This book shouldn't exist and everyone who has ever bought it should get a refund. I haven't even read the whole book, I was afraid to - it has a lot of wrong information, so I completely lost confidence to learn about other topics. Common misconceptions are all over the place. I'll give you some examples: the very first page on Chapter 1 says this: *For example, `int` may take 2 bytes or 4 bytes. If it takes 2 bytes (16 bits) then the total possible values are -32768 to +32767 (-2^15 to 2^15-1)*. The first mistake is an unfortunate typographical glitch: the line breaks between the `-` in 32768 and the "3" - what a terrible place to insert a line break! But more important than that, this is plain wrong. The author makes it look like 16 bit signed integers always span that range, but that only happens if we assume 2s complement representation. Sure, it's very common, but there are other possible representations. A programming book must be precise. But that's a minor issue. This is about to get serious. A few pages ahead, the author shows a diagram where he shows that \\(\mathcal{O}(n)\\) is worse than \\(\mathcal{O}(2^{log(n)})\\), and that's **wrong**, because \\(2^{log(n)} = n\\). Later in the book, when the master theorem is discussed, he solves an exercise with \\(f(n) = n!\\), and that is illegal, because the master theorem says that \\(f(n)\\) must be \\(\mathcal{O}(n^k log(n)^p)\\). In the chapter about recursion, he says that *[...] generally, loops are turned into recursive functions when they are compiled or interpreted*. **WHAT THE HELL?!?!?!** Ironically, one page later, he goes on and writes *[...] iterative solutions are more efficient than recursive solutions*, so **the author is basically saying that compilers will deliberately generate slower code by turning iteration into recursion**. Cool... By the way, that chapter about recursion consists of 3 pages - [my article about mastering recursion]({% post_url 2013-09-14-mastering-recursion %}) is a much more complete resource - and it's free. The linked lists chapter provides wrong solutions for the exercises (the code for problem 5 is wrong, it doesn't work - the right solution is showed in Cracking the Coding Interview). Another thing that bothers me is that problems and solutions are tied together, making it really hard for you not to look at the solution. It's stamped there *immediately after the problem description*. It sucks. The typeset is ugly and the code is not even written on a proper font - he uses the same typeface to write the text and the code (and it looks like the whole book was written using Microsoft Word? Seriously?!). There are grammar errors (and I'm not even a native English speaker), and the book itself is tremendously huge when compared to others. In short: problems have wrong solutions, information is wrong and / or misleading, and chapters are superficial and short. **I do NOT recommend this book**. I was astonished at the amount of 5-star ratings in amazon, and I still cannot understand why. This is a terrible resource. Instead, I will try *Data structures with abstract data types*, by Daniel F. Stubbs and Neil W. Webr, which at least was recommended by Peter Van Der Linden - and you should do the same. Forget that this book exists.

* **C - A Reference Manual** [Harbison & Steele] - This is *the* C book. Harbison and Steele really hit the spot with this one. Recommended by Peter Van Der Linden in *Expert C Programming - Deep C Secrets*, I got my copy of *C - A Reference Manual* and was amazed at how detailed and rich this book is. C compilers writers have been using this as a reference manual for a very long time. It's a shame that there isn't an edition for C11 (the 5th edition covers C99), but hopefully, this will soon be sorted out. This book is not for beginners, it assumes you already have a pretty decent knowledge of the language, it is in no way an introductory tutorial. Some very neat C issues are presented, and dark topics like trigraphs, compilation stages, preprocessor functionality and how macros are expanded, sequence points, switch usage (an extremely bizarre example of switch usage is shown), what exactly is `volatile`, and other things, are discussed. The book includes several code examples, and one of the most interesting Set implementation using bitwise operations that I have ever seen. If you have a chance, give a look at the function `next_set_of_n_elements(SET x)` on page 241, which can be used to solve very elegantly a bit manipulation question I saw in Cracking the Coding Interview. I was delighted. Extremely useful book. Kind of long, but most of the final chapters are reference manual for the standard library, which is nice to have around. I absolutely recommend this to other developers!

* **Computer Organization And Design - The Hardware/Software Interface** [Patterson & Hennessy] - I've read this as part of an Embedded Systems course. The book is widely known and used in the most renowned universities across the world on computer architecture courses. It contains very detailed information on how a processor works, how it is implemented, how it communicates with other components across a computer, how I/O is managed, virtual memory, and other similar topics. You really go down to the bit level. By reading this book, you will learn about cached memory hierarchies (what is an L1, L2 and L3 cache), different types of processors (superscalar, vectorial instruction sets, ...), how a multi-core processor ensures cache coherence and consistency, how instruction pipelining works and the issues that arise with it, what *really* means pipelined instructions and how it affects performance, why increasing the pipeline stages can be bad, how to measure program performance, how to improve performance... I could stay here all day long. Oh, and let me say this, because it's important: you will finally understand how to appreciate a CPU. No, it's not just the clock frequency that matters. The general belief that the higher the clock frequency, the better, can be misleading, and lots of people fall for that, even CS students. Boy, there are so many things to compare. To name a few: cache size - really important, and no one knows what exactly is that, and it is often hard to find; cache associativity - important because of collisions; cache block size; instruction set; number of cores; number of threads per core; pipeline stages; power consumption; branch prediction policy - is it static or dynamic? If dynamic, how many state bits?; RISC / CISC; TLB size, well, you see, lots of stuff. You're being naive if you rely solely on CPU frequency, not to mention that it sounds totally noobish. Now, if you go out to a store and try and ask such information to a seller, he will stare at you and wonder if you're crazy. You see, it's all about marketing, people will only care for CPU frequency, so, that's what they sell. With this book, you will learn fascinating and valuable information that make you a better professional. You will learn common falacies and pitfalls. Anyone claiming to be a computer's professional should read this book, it contains extremely important core concepts for those working in this field. I absolutely look at computers with another perspective after reading this, and I finally know how to choose a CPU.

* **Programming Pearls (2nd edition)** [Jon Bentley] - As the book suggests, just as natural pearls grow from grains of sand that irritate oysters, programming pearls have grown from real problems that have irritated real programmers. This is a general book on data structures, algorithms and efficiency. Trust me, everything you *want* to know! The book is divided in 3 major parts: *Preliminaries*, *Performance* and *The product*. Several important topics are covered in the field of algorithm design techniques, program verification, performance issues and back-of-the-envelope calculations. I would recommend this book to any programmer willing to master algorithms. This is a relatively short book (240 pages), but take it easy, don't try to read it quickly. Columns are brief but dense, it might take a while to assimilate the concepts. You might need to read a column more than once, and if you're commited to exploring this book, you will take a lot of time doing the exercises (each column holds about 10 to 15 medium / hard exercises). My advice? Don't read the next column without solving every exercise from the previous one. It's a tough rule to follow, and that's why it took me almost 2 months to read this book from cover to cover. You can see some comments on a few exercises in my github repository. See the Code Snippets section. I have also published some articles in here about exercises that I found hard. This is not just "another book on data structures and algorithms". Steve McConnell recommends this book.

* **More Joel On Software - Further Thoughs on Diverse and Occasionally Related Matters That Will Prove Of Interest To Software Developers, Designers, And Managers, And To Those Who, Whether By Good Fortune Or Ill Luck, Work With Them In Some Capacity** [Joel Spolsky] - The story continues. This book is the continuation of the traditional Joel On Software series. There's some pretty good material in there! Joel did a great job with this book where you learn a vast majority of topics: coding-related stuff, economics, management, how to start a software company, how much should you charge, the importance of the workplace, the importance of user interfaces, and much, much more. With this book, you will learn lots of useful facts about software industry that go way beyond coding, and you get to understand why everything works the way it works.

* **Expert C Programming - Deep C Secrets** [Peter Van Der Linden] - C, the powerful, simple to learn language where you can create hard-to-read programs or unexpected, hard-to-track, weird bugs. This book shows all the nitty gritty details of C, and provides examples of code with hidden bugs and techniques to find them. This book is very good. Peter worked for Sun as a compiler an kernel developer, and his book is full of scary stories about the most obfuscated bugs. It has some great programming challenges, like writing a more powerful dcl implementation (dcl is a program to interpret C declarations and translate them into English). His refined and constant sense of humour make this book a must-have in any programmer's personal library. You will learn stuff that you don't in K&R. It's a nice complement. For example, you will finally understand why arrays and pointers are not the same thing, and why defining a `char a[100]` in `file1` and declaring `extern char a[]` in `file2` is different from declaring `extern char *a`. The former will work, the latter will be the cause of an ugly segfault. And did you notice how I wrote *define* in `file1` and *declare* in `file2`? It was intentional, these are the correct words. Want to know more? Read the book! Seriously, read it! *I read this twice*. I love it.

* **The C programming language** [Brian W. Kernighan, Dennis M. Ritchie] - The good old, classical C bibble. I thought I knew C, until I started reading this and solving the exercises. If you consider that you know C but never read K&R, you really don't know C, you just have a vague idea about it. The trick is not just to read the book. You have to solve the exercises. And I mean *really* solve and test *all* of them. You will learn twice as much if you do this than if you only read the book. Solving the exercises will force you to think about small implementation details that you would have never thought of, and it improves your skill. It will make you another person. And don't just solve the exercises "on air", I mean, don't just think about how you would implement it in a high-level way. No. You have to *Write Teh CodeZ* and test it. That's the only way you will learn something useful. Implementing it in your head will always work!

* **The Google Résumé** [Gayle Laakman McDowell] - This book is all about dream jobs and how to get one. The complete title is *The Google Résumé - How to Prepare for a Career and Land a Job at Apple, Microsoft, Google, or Any Top Tech Company*. It teaches how to make a résumé, a cover letter, how to prepare for technical interviews, well, it talks about every aspect of jog seeking and application. Think of it as a kind of guide to help you find a job that will make you happy, because life is too short not to love every day of your job! The book author has interviewed over 120 candidates and has worked for Microsoft, Google and Apple. She knows what they're looking for, and we, the candidates, can take advantage of that by reading this book. Of course that there is no "cheat" key to success, and that's not what the book is about. It's about knowing how to behave and how to make the right moves.

* **Mastering Regular Expressions** (3rd edition) [Jeffrey Friedl] - Regular expressions are one of those things that everyone claims to know a little bit, but no one really knows it good enough. This book is THE place to learn regular expressions. And not only you learn regular expressions, you are also introduced to the world of Perl, a scripting language with unique, magical and powerful builtin regex support that other languages started to copy. The book covers regular expressions features and implementations down to a very deep level. You will see what features are available in which tools. You will learn how to "think" regexes. Even if you are halfway familiar with the regex world, you should start from scratch and read eveerything starting on chapter 1, because there are some ways of thinking about regex components that are tremendously revolutionary and will brainwash you to look at regexes with different eyes. With this book, you learn how to build custom regexes for your own needs, and how to make them more efficient by exploiting some of the implementation details that are often underlooked. The final chapters are devoted to specific languages: Perl, Java, PHP and VB.Net. It's a very useful book, and what you learn from it can have huge impacts in your productivity. Mastering regular expressions will get you rid of tedious, mechanical tasks that you never thought you could automate so easily with the power of regular expressions.


* **Joel on Software, and on diverse and occasionally related matters that will prove of interest to software developers, designers and managers, and to those who, whether by good fortune or ill luck, work with them in some capacity** [Joel Spolsky] - This book is basically an organized compilation of Joel Spolsky's articles. This book is full of funny stories in the world of software development with very good content and lessons taken from it. It is not a code-oriented book, it's more like a general book on software projects and teams, though you have some chapters with low level stuff. For example, you are introduced to the concept of a Shlemiel the Painter's algorithm in one of my favorite Joel's articles. I even made [a post about it]({% post_url 2013-06-08-shlemiel-the-painter %}). Reading Joel's book is both fun and instructive.

* **Smart & Gets Things Done** [Joel Spolsky] - Yet another great book from Joel. I read this in less than 2 days. It's a very compact, 169 pages book where Joel reveals his techniques to find the best technical talent. This is not, in any way, a technical book about coding, but it covers very important issues that arise in the world of tech companies and how they recruit. It's got valuable information for us, programmers. You will find this book an excellent resource to learn about recruiting processes, and you can use it for your own benefit when the time to submit your application comes. You see, you can have a brilliant mind and be a very good programmer, but sometimes it takes a little more than that to get your dream job. Knowing and learning about how they operate on the other side of the fence can help you understanding how to raise your chances of being chosen and land a job at a good company. I recommend this book to anyone who is looking for a career on software development.

* **Code Complete** (2nd Edition) [Steve McConnell] - This is a nice book about high level aspects of software engineering. It's not as code-oriented as traditional programming books like K&R, but a significant part of the book is about good coding practices and styles (where you get to see actual code examples of good and bad programming techniques), how to coordinate coding templates among a team, how to debug properly, and how to be more productive by using the right tools. From a high level perspective, it's a great book that approaches the world of software development focused on teams coordination and management and the life cycle of a product (like design, architecture, construction, testing, quality assurance). Although I read quite some interesting advice from this book (like, for example, understanding why `#define cube(a) a*a*a` can create hidden, very hard to track bugs, and instead should be written as `#define cube(a) ((a)*(a)*(a))`), I think that I read it too early for my age. I feel that this book is of great help to someone who has been working on software development for some years and is building a complex product with a big team. From my perspective as a CS student, I think that a great load of what I read in this book about non-technical issues will be forgotten because I simply don't fully understand the importance of these factors yet, and I do not give the appropriate value to this kind of advice because I never actually left college for more than 3 months for summer internships. Would I recommend this book? Sure! It's a must-have in your shelf if you want to be a great programmer.