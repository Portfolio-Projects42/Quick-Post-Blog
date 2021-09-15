---
title: How to Convert A Folder Of Notes Into A Documentation Website
tags:
  - react
  - vscode
published: true
date: '2019-03-20'
---


# **Preparing for a Coding Interview**

### **Picking a Programming Language**

Before anything else, you need to pick a programming language to do your interviews in. Most companies will let you code in any language you want, the only exception I know being Google, where they only allow candidates to pick from Java, C++ or Python for their algorithmic coding interviews. Most of the time, I would recommend that you use a language that you are extremely familiar with rather than picking up a new language just for doing interviews because the company uses that language heavily.

There are some languages which are more suitable than others for coding interviews and some languages you absolutely want to avoid. From my experience interviewing as an interviewer, most candidates pick Python or Java. Other commonly seen languages include JavaScript, Ruby and C++. I would absolutely avoid lower level languages like C or Go, simply because they lack in many standard library functions and data structures.

Personally, Python is my de facto choice for coding algorithms during interviews because it is succinct and has a pretty huge library of functions and data structures available. One of my top reasons for recommending Python is that it uses consistent APIs that operate on different data structures, such as len(), for ... in ... and slicing notation on sequences (strings/lists/tuples). Getting the last element in a sequence is arr\[-1] and reversing it is simply arr\[::-1]. You can achieve a lot with minimal syntax in Python.

Java is a decent choice too but having to constantly declare types in your code means extra keystrokes which results in slower coding/typing speed. This issue will be more apparent when you have to write on a whiteboard during on-site interviews. The reasons for choosing/not choosing C++ are similar to Java. Ultimately, Python, Java and C++ are decent choices of languages. If you have been using Java at work for a while now and do not have time to be comfortably familiar with another language, I would recommend just sticking to Java instead of picking up Python from scratch just for interviews to avoid having to context switch between languages during work vs interviews. Most of the time, the bottleneck is in the thinking and not the writing.

One exception to the convention of allowing you to "pick any programming language you want" is when you are interviewing for a domain-specific position, such as Front End/iOS/Android Engineer roles, in which you would need to be familiar with coding algorithms in JavaScript, Objective-C/Swift and Java respectively. If you need to use a data structure that the language does not support, such as a Queue or Heap in JavaScript, perhaps try asking the interviewer whether you can assume that you have a data structure that implements certain methods with specified time complexities. If the implementation of that data structure is not crucial to solving the problem, the interviewer will usually allow it. In reality, being aware of existing data structures and selecting the appropriate ones to tackle the problem at hand is more important than knowing the intricate implementation details.

### **Review your CS101**

If you have been out of college for a while, it is highly advisable to review CS fundamentals — Algorithms and Data Structures. Personally, I prefer to review as I practice, so I scan through my college notes and review the various algorithms as I work on algorithm problems from LeetCode and Cracking the Coding Interview.

This [interviews repository](https://github.com/kdn251/interviews) by Kevin Naughton Jr. served as a quick refresher for me.

The Medium publication [basecs](https://medium.com/basecs) by [Vaidehi Joshi](https://medium.com/@vaidehijoshi) is also a great and light-hearted resource to recap on the various data structures and algorithms.

If you are interested in how data structures are implemented, check out [Lago](https://github.com/yangshun/lago), a Data Structures and Algorithms library for JavaScript. It is pretty much still WIP but I intend to make it into a library that is able to be used in production and also a reference resource for revising Data Structures and Algorithms.

### **Mastery through Practice**

Next, gain familiarity and mastery of the algorithms and data structures in your chosen programming language:

1.  Practice coding algorithms using your chosen language. While [Cracking the Coding Interview](http://www.crackingthecodinginterview.com/) is a good resource for practice, I prefer being able to type code, run it and get instant feedback. There are various Online Judges such as [LeetCode](https://leetcode.com/), [HackerRank](https://www.hackerrank.com/) and [CodeForces](http://codeforces.com/) for you to practice questions online and get used to the language. From experience, LeetCode questions are the most similar to the kind of questions being asked in interviews whereas HackerRank and CodeForces questions are more similar to competitive programming questions. If you practice enough LeetCode questions, there is a good chance that you would have seen/done your actual interview question (or some variant) on LeetCode before. If you are more of a visual person, [Coderust](https://www.educative.io/collection/5642554087309312/5679846214598656) explains the common algorithm questions through step-by-step visualizations which makes understanding the solutions much easier.

2.  Learn and understand the time and space complexities of the common operations in your chosen language. For Python, this [page](https://wiki.python.org/moin/TimeComplexity) will come in handy. Also find out the underlying sorting algorithm that is being used in the language's sort() function and its time and space complexity (in Python its Timsort which is a hybrid sort). After completing a question on LeetCode, I usually add the time and space complexities of the written code as comments above the function body to remind myself to analyze the algorithm after I am done with the implementation.

3.  Read up on the recommended coding style for your language and stick to it. If you have chosen Python, refer to the PEP 8 Style Guide. If you have chosen Java, refer to Google's Java Style Guide.

4.  Find out and be familiar with the common pitfalls and caveats of the language. If you point out them out during the interview and intelligently avoid falling into them, you will usually impress the interviewer and that results in bonus points in your feedback, regardless of whether the interviewer is familiar with the language or not.

5.  Gain a broad exposure to questions from various topics. In the second half of the article I mention algorithm topics and practice questions for each topic. Do around 100–200 LeetCode questions and you should be good.

Practice, practice and more practice!

### **Phases of a Coding Interview**

Congratulations, you are ready to put your skills into practice! In a real coding interview, you will be given a technical question by the interviewer, write code in a real-time collaborative editor (phone screen) or on a whiteboard (on-site) to solve the problem within 30–45 minutes. This is where the real fun begins!

Your interviewer will be looking out for signals that you fit the requirements of the role and it is up to you to display those signals to them. Initially it may feel weird to be talking while you are coding as most programmers do not have the habit of explaining out loud as they are typing code. However, it is hard for the interviewer to know what you are thinking just by looking at the code that you type. If you communicate your approach to the interviewer before you start coding, you can validate your approach with them and the both of you can agree upon an acceptable approach.

**Before the Interview (Remote)**

For phone screens/remote interviews, prepare paper and pen/pencil to jot down and visualize stuff. If you are given a question on trees and graphs, it usually helps if you draw out some examples of the data structure given in the question.

Use earphones and make sure you are in a quiet environment. You definitely do not want to be holding a phone in one hand and only be able to type with the other. Try avoiding using speakers because if the echo is bad, communication is harder and repeating of words will just result in loss of valuable time.

**Self Introduction**

TODO

**Upon Getting the Question**

Many candidates jump into coding the moment they hear the question. That is usually a big mistake. Take a moment to repeat the question back at the interviewer and make sure that you understand exactly what they are asking. If you misunderstood and when you repeat back the question, they will clarify.

Always seek clarification about the question upon hearing it even if it you think it is clear to you. You might discover something that you have missed out and it also sends a signal to the interviewer that you are a careful person who pays attention to details. Some interviewers deliberately omit important details to see if you ask the right questions. Consider asking the following questions:

*   How big is the size of the input?

*   How big is the range of values?

*   What kind of values are there? Are there negative numbers? Floating points? Will there be empty inputs?

*   Are there duplicates within the input?

*   What are some extreme cases of the input?

*   How is the input stored? If you are given a dictionary of words, is it a list of strings or a Trie?

After you have sufficiently clarified the scope and intention of the problem, explain your high level approach to the interviewer even if it is a naive solution. If you are stuck, consider various approaches and explain out loud why it will/will not work. Sometimes your interviewer might drop hints and lead you towards the right path.

Start with a brute force approach, communicate it to the interviewer, explain the time and space complexity and why it is bad. It is unlikely that the brute force approach will be one that you will be coding. At this point, the interviewer will usually pop the dreaded "Can we do better?" question, meaning that they are looking for a more optimal approach. In my opinion, this is usually the hardest part of the interview. In general, look for repeated work and try to optimize them by potentially caching the calculated result somewhere and reference it later, rather than having to compute it all over again. There are some tips on tackling topic-specific questions that I dive into details below.

Only start coding after you and your interviewer have agreed on an approach and has given you the green light.

**Starting to Code**

Write your code with good coding style. Reading code written by others is usually not an enjoyable task. Reading horribly-formatted code by others makes it worse. Your goal is to make your interviewer understand the code you have written so that they can quickly evaluate if your code does what you say it does and whether it solves the given problem. Use clear variable names, avoid single letter names unless they are for iteration. However, if you are coding on a whiteboard, you might not want to use extremely verbose variable names for the sake of reducing the amount you have to write.

Always be explaining what you are currently writing/typing to the interviewer. This is not about literally reading out what you are typing to the interviewer. Talk about the section of the code you are currently implementing at a higher level, explain why it is written as such and what it is trying to achieve.

When you copy and paste code, consider whether it is necessary. Sometimes it is, sometimes it is not. If you find yourself copying and pasting one large chunk of code spanning multiple lines, it is probably an indicator that you can refactor by containing those lines into a function. If it is just a single line you copied, usually it is fine. Do remember to change the respective variables in your copied line of code where relevant. Copy-paste errors are a common source of bugs even in day-to-day coding!

**After Coding**

After you have finished coding, do not immediately announce to the interviewer that you are done. In most cases, your code is usually not perfect and contains some bugs or syntax errors. What you need to do now is to review your code.

Firstly, look through your code from start to finish as if it is the first time you are seeing it, as if it was written by someone else and you are trying to spot bugs in it. That's exactly what your interviewer will be doing. Look through and fix any minor issues you may find.

Next, come up with small test cases and step through the code (not your algorithm!) with those sample input. Interviewers like it when you read their mind and what they usually do after you have finished coding would be to get you to write tests. It is a huge plus if you write tests for your code even before prompts from them. You should be emulating a debugger when stepping through and jot down or say out the values of certain variables as you step through the lines of code.

If there are huge duplicated chunks of code in your solution, it would be a good chance to refactor it and demonstrate to the interviewer that you are one who values code quality. Also look out for places where you can do [short-circuit evaluation](https://en.wikipedia.org/wiki/Short-circuit_evaluation).

Lastly, give the time/space complexity of your code and explain why it is such. You can even annotate certain chunks of your code with the various time/space complexities to demonstrate your understanding of your code and the APIs of your chosen programming language. Explain any trade-offs in your current approach vs alternative approaches, possibly in terms of time/space.

If your interviewer is happy with the solution, the interview usually ends here. It is also not uncommon that the interviewer asks you extension questions, such as how you would handle the problem if the whole input is too large to fit into memory, or if the input arrives as a stream. This is a common follow-up question at Google where they care a lot about scale. The answer is usually a divide-and-conquer approach — perform distributed processing of the data and only read certain chunks of the input from disk into memory, write the output back to disk and combine them later on.

### **Practicing via Mock Interviews**

Interviewing is a skill that you can get better at. The steps mentioned above can be rehearsed over and over again until you have fully internalized them and following those steps become second nature to you. A good way to practice is to find a friend to partner with and the both of you can take turns to interview each other.

A great resource for practicing mock coding interviews would be [interviewing.io](https://interviewing.io/). interviewing.io provides free, anonymous practice technical interviews with Google and Facebook engineers, which can lead to real jobs and internships. By virtue of being anonymous during the interview, the inclusive interview process is de-biased and low risk. At the end of the interview, both interviewer and interviewees can provide feedback to each other for the purpose of improvement. Doing well in your mock interviews will unlock the jobs page and allow candidates to book interviews (also anonymously) with top companies like Uber, Lyft, Quora, Asana and more. For those who are totally new to technical interviews, you can even view a [demo interview](https://start.interviewing.io/interview/9hV9r4HEONf9/replay) on the site (requires sign in). Read more about them [here](https://techcrunch.com/2017/09/27/interviewing-io-hopes-to-close-the-engineer-diversity-gap-with-anonymous-interviews/).

I have used interviewing.io both as an interviewer and an interviewee and found the experience to be really great! [Aline Lerner](https://twitter.com/alinelernerLLC), the CEO and co-founder of interviewing.io and her team are passionate about revolutionizing the technical interview process and helping candidates to improve their skills at interviewing. She has also published a number of technical interview-related articles on the [interviewing.io blog](http://blog.interviewing.io/). interviewing.io is still in beta now but I recommend signing up as early as possible to increase the likelihood of getting an invite.

Another platform that allows you to practice coding interviews is [Pramp](https://pramp.com/). Where interviewing.io matches potential job seekers with seasoned technical interviewers, Pramp takes a different approach. Pramp pairs you up with another peer who is also a job seeker and both of you take turns to assume the role of interviewer and interviewee. Pramp also prepares questions for you, along with suggested solutions and prompts to guide the interviewee.

Personally, I am not that fond of Pramp's approach because if I were to interview someone, I would rather choose a question I am familiar with. Also, many users of the platform do not have the experience of being interviewers and that can result in a horrible interview experience. There was once where my matched peer, as the interviewer, did not have the right understanding of the question and attempted to lead me down the wrong path of solving the question. However, this is more of a problem of the candidate than the platform though.

### **Conclusion**

Coding interviews are tough. But fortunately, you can get better at them by studying and practicing for them, and doing mock interviews. To recap, to do well in coding interviews:

1.  Decide on a programming language

2.  Study CS fundamentals

3.  Practice solving algorithm questions

4.  Internalize the [Do's and Don'ts of interviews](https://github.com/side-projects-42/tech-interview/blob/master/preparing/cheatsheet.md)​

5.  Practice doing mock interviews

6.  Interview successfully to get the job

By following these steps, you will improve your coding interview skills, and be one step closer (or probably more) to landing your dream job.

All the best!

​

​




# ➤ Initial page

[demo](https://bgoonz.github.io/INTERVIEW-PREP-COMPLETE/)

# Getting a Gig: A Guide

# Introduction

# Contents

- Introduction (you read that already)
- [Your Resume](#your-resume)
- [Your Cover Letter](#your-cover-letter)
- [Your Attitude](#your-attitude)
- [Your Skills](#your-skills)
  - Building Them
  - Selling Them
- [Your Search](#your-search)
  - Events
  - Networking
  - Referrals
  - Cold Calling
  - Fellowships
- [Conclusion](#conclusion)

# Your Resume

Your resume is your personal summary sheet. Your resume is the thing that gets your foot in the door. So, there’s a few things you should do (and not do) to make it as awesome as you are.

### Make your name **BIG.**

Your name has to stand out from everything else, because you want it to be remembered. Making it the biggest thing on the page is the easiest thing you can do to make that possible. I’ve seen soooo many resumes where the name is at the top, but it’s just bolded and centered and they expect that to be enough. It’s not.

### Remove the objective.

Nobody looks at the objective. Nobody. I personally spoke to a bunch of recruiters from various companies and they all said that they never look at them. Use that space to talk about projects you’ve done, activities you’ve done, etc.

### Keep it to a single page.

Recruiters are looking for a short summary of you. They’re reading several resumes a day, and if they see something longer than they typically read, they could pass over yours for something more concise! If you’d like to say more, put a link to a personal website or portfolio for someone to find it. A resume is a summary, not a tome.

### Remove irrelevant information.

I know that lifeguarding in high school was a good gig that helped you gain people skills and attention to detail. But you’re in tech. That doesn’t matter as much to tech companies. Sorry, buddy. I still think you’re great with people. When you’re a first semester freshman, it’s okay to have old high school stuff on there, just because it’s less likely that you have other things to put on your resume. But as soon as you have a college GPA to work with, a club or two, and some volunteer experiences to replace that, do it.

### Don’t make it a scavenger hunt.

When an application reviewer (engineer, recruiter, or otherwise) is looking over your resume, don’t make it difficult for them to understand who you are and what you know.

For example, if you have online profiles like GitHub, LinkedIn, Twitter, or even your own personal website, put it on your resume. Don’t make them have to search long and hard for you online if they want to know more!

If you decide to put relevant coursework on your resume, **please**, don’t just put course numbers. Nobody knows what that means. And nobody is going to go to your university’s website to find out exactly what CS229 is. Put down the course titles instead!

And finally, put down your graduation date. So many students I’ve seen don’t put it on there because they are hiding the fact that they’re a freshman, or they’re “technically a junior if you count the credits.” That doesn’t matter. Trust me. Just put down your graduation date so that the company knows how much experience you have, and how soon they can potentially pull you in for full-time.

### Include only certain personal information.

Companies aren’t allowed to ask about your religion, marital status, or race/ethnicity, so you shouldn’t include that.

In terms of contact information: you don’t need your mailing address. That is a thing of the past. Just like my youth. Tech companies email, and **maybe** call. That’s all you need! Some great things that you might also want to put on there are your personal website (if you have one, which you should), your GitHub profile (if you have one, which you should), and your LinkedIn (if you have one, which you should).

Though there’s some who might disagree, you should **include your GPA.** If your major GPA is significantly higher than your overall GPA, you might want to consider having both. When you have graduated and have a full-time job, you won’t need it as much. But at this point in your beautiful life, keep it in there. Some companies care about GPA more than others, so you might as well play it safe and have it there.

# CV Sample

Your cover letter is your written sales pitch. You’ve got a resume that summarizes everything. Now you have to write out a more complete, professional description of you and what you can offer a given company. Here’s a sample cover letter to get you started:

> Dear \***\*\_\*\***,
>
> I hope your day is going well! My name is \***\*\_\*\***, and I’m a \***\*\_\*\*** at \***\*\_\*\***. I am very interested in working for \***\*\_\*\*** next \***\*\_\*\***. Your commitment to \***\*\_\*\*** and \***\*\_\*\*** that I saw on the website inspired me! The products you build and the values you stand for make \***\*\_\*\*** seem like an ideal workplace for me.

A little about me, I \[insert relevant work experience, extracurriculars, and projects here\]. I think these experiences would make me a great candidate for you.

> Please let me know if there’s anything else you need from me. I look forward to hearing from you! I can be reached at \***\*\_\*\*** and \***\*\_\*\***.
>
> Best regards,
>
> ---

Now, remember, this is just a sample. You can write a cover letter in any format you’d like. But, you should be sure to include the following:

- **Who** - Who you are. Easy enough.
- **Where** - Where you’re coming from.
- **Why** - Why you’re interested in this company, and show that you researched them.
- **What** - What you can bring to the table.
- **When** - When you’re available to start, and when they can contact you.
- **How** - How they can reach you.

# Your Attitude

When you’re internship/job hunting, it’s very easy to feel down if you don’t hear back from companies, an interview goes poorly, or you start comparing yourself to people. It’s a tough field we’re going into.

So. I won’t spend much time on this. But I want to emphasize something: **You’re brilliant.** You’re in this field for a reason. When your grades aren’t awesome or someone gets something that you wanted, don’t feel down on yourself. So many opportunities will come your way if you just keep working hard and refining your skills.

Mark Twain once said, “Comparison is the death of joy.” When you start to compare your skills to others, it’s hard to not feel as good about your own, or to get a little too competitive about your work. Work hard and don’t let others get you down. It’s remarkable how significantly that can improve both your work and your interviewing experience!

When you’re talking to companies and recruiters at career fairs and hackathons and over the phone, be confident, not arrogant. Be grateful for the opportunity they’re giving you, and smile! A great attitude will take you VERY far.

# Your Skills

Obviously, your skills are what a company is buying from you when they hire you. So, honing in those skills and presenting them in an effective way is _probably_ the most important thing in getting a gig.

## Building Them

Chances are, if you’ve had a data structures and/or algorithms class, you’re already going to do pretty well in the technical interviews. That is, if you can recall the information you learned.

Here’s a checklist of things that you should probably be prepared to know in a technical interview:

- Data types
- Basic Bitwise Operations
- String Operations
- Arrays
- Linked Lists
  - Singly Linked
  - Doubly Linked
  - Circular Linked
- Queues
- Stacks
- Heaps
- Trees
  - Binary Trees
  - Binary Search Trees
  - Tries
  - Self Balancing Trees
- Traversing Trees
  - Breadth First Search - BFS
  - Depth First Search - DFS
  - Preorder, Inorder, Postorder
- Graphs
  - Dijkstra’s Algorithm / A\* Search
- Hash Maps
  - Handling Collisions
- Sorting algorithms
  - Insertion
  - Selection
  - Merge
  - Quick
- Time Complexities

This guide isn’t for teaching you these skills. But there are several guides, problem sets, and practice systems out there that can help.

**General Guides**

- [Sorting Algorithms](http://www.sorting-algorithms.com/)
- [Big-O Cheat Sheet](http://bigocheatsheet.com/)
- [Data Structures and Algorithms Overview](http://www.dsalgo.com/2013/02/index.php.html?m=1)
- [Algorithm Implementations](http://algorithm.zone/)
- [Top 10 Algorithms for coding interviews](http://www.programcreek.com/2012/11/top-10-algorithms-for-coding-interview/)

**Problem Sets**

- [Data Structures Questions](http://www.geeksforgeeks.org/data-structures/)
- [FitCoding](http://www.fitcoding.com/)
- [Google CodeJam Practice Questions](https://code.google.com/codejam/contests.html)

**Online Judging Systems**

- [LeetCode Online Judge](https://oj.leetcode.com/problemset/algorithms/)
- [HackerRank Online Judge](https://www.hackerrank.com/)
- [Project Euler](https://projecteuler.net/)

**Mock Interviews**

- [Pramp](https://www.pramp.com) - free
- [Careercup](http://www.careercup.com/interview) - paid
- [Gainlo](http://www.gainlo.co/) - paid
- [Impact Interview](http://www.impactinterview.com/software-engineering-interview-coaching/) - paid

Here’s some books that might also be useful.

- [Algorithms, 4th edition, by Robert Sedgewick and Kevin Wayne](http://www.amazon.com/Algorithms-4th-Edition-Robert-Sedgewick/dp/032157351X)
- [Introduction to Algorithms, 3rd Edition, by Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford Stein (also referred as CLRS)](http://www.amazon.com/Introduction-Algorithms-Edition-Thomas-Cormen/dp/0262033844)
- [Think Complexity, by Allen B. Downey](http://greenteapress.com/complexity/thinkcomplexity.pdf)
- [Problems on Algorithms, 2nd edition, by Ian Parberry and William Gasarch](http://larc.unt.edu/ian/books/free/poa.pdf)
- [Data Structures and Algorithms in Java](http://rineshpk.weebly.com/uploads/1/8/2/0/1820991/data_structures_and_algorithms_in_javatqw_darksiderg.pdf)
- [Cracking the Coding Interview, 6th edition, by Gayle Laakmann McDowell](http://www.amazon.com/Cracking-Coding-Interview-6th-Programming/dp/0984782850/ref=sr_1_1?ie=UTF8&qid=1443719471&sr=8-1&keywords=coding+interview)

Typically, for an internship or your first job, questions won’t get much more specific unless you’re applying for a specific role. For example, if I wanted to be a mobile intern, I might be asked iOS/Android/Windows Phone specific questions, or if I wanted to be a web intern, I might be asked HTML/CSS/JavaScript questions, or if I wanted to be a backend intern, I might be asked about Django or Node or Ruby on Rails. That definitely depends on the company, and what you’re both looking for.

Make sure you’re able to implement and use the above data structures without the assistance of an IDE. Typically, onsite technical interviews involve coding on paper or a whiteboard, and phone/video interviews usually involve some kind of collaborative text editor. Yes, that means you won’t have access to auto-complete, auto-compiling, or the internet to check for errors. So be ready for that!

## Selling Them

When you’re actively emailing and speaking with recruiters, they’re going to ask you a lot of questions that are just checkboxes for what they’re looking for in terms of skills.

If you’ve written anything in a language before, **put it on your resume**. A lot of companies have parsers that look for specific things that, again, will put a tick on those checkboxes before putting you through to the next round of review. Now, if you’ve only ever done “Hello, world!” in Python, don’t say that you’re a Python ninja or whatever. You don’t want to be thrown into an interview that will only hurt your self-confidence. Speaking from experience. Trust me.

When a recruiter or engineer is asking you about a certain project you’ve done, or how you’ve used a particular language, be as specific as possible. Tell them **exactly** what you did on that particular project (or internship or what have you). Tell them how much you contributed, what languages you used, how long was the duration of development for that project, what was the outcome of the project, etc. etc.

For example, don’t say, “I’m the webmaster for a club website. Next question.” Okay, Dwight Schrute. Go back to your beet farm. Instead, say something more like this: “I developed and currently maintain the website for my university’s computer science club. I built it from the ground up with HTML, CSS, JavaScript, and jQuery on the front-end. It’s a static site, so a backend wasn’t needed. The website’s main function is to promote the club and give members crucial updates about meetings and events, and I update it regularly via a Python script I wrote.” Oh my, you enchanting software engineer, you. Let me hire you.

When you’re talking to companies about specific things you’ve done, make sure they know:

- **What?** - What? - What did you make? What does it do? What impact has it made? What was the hardest part? What could you have done better?
- **Why?** - Why did you make it? Was it for a hackathon, a school project, an open source contribution, or something else?
- **How?** - With which technologies did you make this? Did you use a specific API? What parts of it did you work on?
- **When?** - Did you do this recently or are you still living off of when you peaked in 10th grade?
- **Who?** - Did you work on this with anyone? Who did what? Who is this for?

# Your skills are something that you have, and the reason why you have them is because you’ve used them in some way. All you have to do to prove yourself is to explain yourself! No need to gGetting a Gig: A Guide

# Introduction

Hey friends! This is a guide for getting a gig in college as a tech major. I graduated May 2014 with 10 job offers after having 5 internships throughout my four years of college. You can do that, too. Because you’re great.

# Contents

- Introduction (you read that already)
- [Your Resume](#your-resume)
- [Your Cover Letter](#your-cover-letter)
- [Your Attitude](#your-attitude)
- [Your Skills](#your-skills)
  - Building Them
  - Selling Them
- [Your Search](#your-search)
  - Events
  - Networking
  - Referrals
  - Cold Calling
  - Fellowships
- [Conclusion](#conclusion)

# Your Resume

Your resume is your personal summary sheet. Your resume is the thing that gets your foot in the door. So, there’s a few things you should do (and not do) to make it as awesome as you are.

### Make your name **BIG.**

Your name has to stand out from everything else, because you want it to be remembered. Making it the biggest thing on the page is the easiest thing you can do to make that possible. I’ve seen soooo many resumes where the name is at the top, but it’s just bolded and centered and they expect that to be enough. It’s not.

### Remove the objective.

Nobody looks at the objective. Nobody. I personally spoke to a bunch of recruiters from various companies and they all said that they never look at them. Use that space to talk about projects you’ve done, activities you’ve done, etc.

### Keep it to a single page.

Recruiters are looking for a short summary of you. They’re reading several resumes a day, and if they see something longer than they typically read, they could pass over yours for something more concise! If you’d like to say more, put a link to a personal website or portfolio for someone to find it. A resume is a summary, not a tome.

### Remove irrelevant information.

I know that lifeguarding in high school was a good gig that helped you gain people skills and attention to detail. But you’re in tech. That doesn’t matter as much to tech companies. Sorry, buddy. I still think you’re great with people. When you’re a first semester freshman, it’s okay to have old high school stuff on there, just because it’s less likely that you have other things to put on your resume. But as soon as you have a college GPA to work with, a club or two, and some volunteer experiences to replace that, do it.

### Don’t make it a scavenger hunt.

When an application reviewer (engineer, recruiter, or otherwise) is looking over your resume, don’t make it difficult for them to understand who you are and what you know.

For example, if you have online profiles like GitHub, LinkedIn, Twitter, or even your own personal website, put it on your resume. Don’t make them have to search long and hard for you online if they want to know more!

If you decide to put relevant coursework on your resume, **please**, don’t just put course numbers. Nobody knows what that means. And nobody is going to go to your university’s website to find out exactly what CS229 is. Put down the course titles instead!

And finally, put down your graduation date. So many students I’ve seen don’t put it on there because they are hiding the fact that they’re a freshman, or they’re “technically a junior if you count the credits.” That doesn’t matter. Trust me. Just put down your graduation date so that the company knows how much experience you have, and how soon they can potentially pull you in for full-time.

### Include only certain personal information.

Companies aren’t allowed to ask about your religion, marital status, or race/ethnicity, so you shouldn’t include that.

In terms of contact information: you don’t need your mailing address. That is a thing of the past. Just like my youth. Tech companies email, and **maybe** call. That’s all you need! Some great things that you might also want to put on there are your personal website (if you have one, which you should), your GitHub profile (if you have one, which you should), and your LinkedIn (if you have one, which you should).

Though there’s some who might disagree, you should **include your GPA.** If your major GPA is significantly higher than your overall GPA, you might want to consider having both. When you have graduated and have a full-time job, you won’t need it as much. But at this point in your beautiful life, keep it in there. Some companies care about GPA more than others, so you might as well play it safe and have it there.

# Your Cover Letter

Your cover letter is your written sales pitch. You’ve got a resume that summarizes everything. Now you have to write out a more complete, professional description of you and what you can offer a given company. Here’s a sample cover letter to get you started:

> Dear \***\*\_\*\***,
>
> I hope your day is going well! My name is \***\*\_\*\***, and I’m a \***\*\_\*\*** at \***\*\_\*\***. I am very interested in working for \***\*\_\*\*** next \***\*\_\*\***. Your commitment to \***\*\_\*\*** and \***\*\_\*\*** that I saw on the website inspired me! The products you build and the values you stand for make \***\*\_\*\*** seem like an ideal workplace for me.

A little about me, I \[insert relevant work experience, extracurriculars, and projects here\]. I think these experiences would make me a great candidate for you.

> Please let me know if there’s anything else you need from me. I look forward to hearing from you! I can be reached at \***\*\_\*\*** and \***\*\_\*\***.
>
> Best regards,
>
> ---

Now, remember, this is just a sample. You can write a cover letter in any format you’d like. But, you should be sure to include the following:

- **Who** - Who you are. Easy enough.
- **Where** - Where you’re coming from.
- **Why** - Why you’re interested in this company, and show that you researched them.
- **What** - What you can bring to the table.
- **When** - When you’re available to start, and when they can contact you.
- **How** - How they can reach you.

# Your Attitude

When you’re internship/job hunting, it’s very easy to feel down if you don’t hear back from companies, an interview goes poorly, or you start comparing yourself to people. It’s a tough field we’re going into.

So. I won’t spend much time on this. But I want to emphasize something: **You’re brilliant.** You’re in this field for a reason. When your grades aren’t awesome or someone gets something that you wanted, don’t feel down on yourself. So many opportunities will come your way if you just keep working hard and refining your skills.

Mark Twain once said, “Comparison is the death of joy.” When you start to compare your skills to others, it’s hard to not feel as good about your own, or to get a little too competitive about your work. Work hard and don’t let others get you down. It’s remarkable how significantly that can improve both your work and your interviewing experience!

When you’re talking to companies and recruiters at career fairs and hackathons and over the phone, be confident, not arrogant. Be grateful for the opportunity they’re giving you, and smile! A great attitude will take you VERY far.

# Your Skills

Obviously, your skills are what a company is buying from you when they hire you. So, honing in those skills and presenting them in an effective way is _probably_ the most important thing in getting a gig.

## Building Them

Chances are, if you’ve had a data structures and/or algorithms class, you’re already going to do pretty well in the technical interviews. That is, if you can recall the information you learned.

Here’s a checklist of things that you should probably be prepared to know in a technical interview:

- Data types
- Basic Bitwise Operations
- String Operations
- Arrays
- Linked Lists
  - Singly Linked
  - Doubly Linked
  - Circular Linked
- Queues
- Stacks
- Heaps
- Trees
  - Binary Trees
  - Binary Search Trees
  - Tries
  - Self Balancing Trees
- Traversing Trees
  - Breadth First Search - BFS
  - Depth First Search - DFS
  - Preorder, Inorder, Postorder
- Graphs
  - Dijkstra’s Algorithm / A\* Search
- Hash Maps
  - Handling Collisions
- Sorting algorithms
  - Insertion
  - Selection
  - Merge
  - Quick
- Time Complexities

This guide isn’t for teaching you these skills. But there are several guides, problem sets, and practice systems out there that can help.

**General Guides**

- [Sorting Algorithms](http://www.sorting-algorithms.com/)
- [Big-O Cheat Sheet](http://bigocheatsheet.com/)
- [Data Structures and Algorithms Overview](http://www.dsalgo.com/2013/02/index.php.html?m=1)
- [Algorithm Implementations](http://algorithm.zone/)
- [Top 10 Algorithms for coding interviews](http://www.programcreek.com/2012/11/top-10-algorithms-for-coding-interview/)

**Problem Sets**

- [Data Structures Questions](http://www.geeksforgeeks.org/data-structures/)
- [FitCoding](http://www.fitcoding.com/)
- [Google CodeJam Practice Questions](https://code.google.com/codejam/contests.html)

**Online Judging Systems**

- [LeetCode Online Judge](https://oj.leetcode.com/problemset/algorithms/)
- [HackerRank Online Judge](https://www.hackerrank.com/)
- [Project Euler](https://projecteuler.net/)

**Mock Interviews**

- [Pramp](https://www.pramp.com) - free
- [Careercup](http://www.careercup.com/interview) - paid
- [Gainlo](http://www.gainlo.co/) - paid
- [Impact Interview](http://www.impactinterview.com/software-engineering-interview-coaching/) - paid

Here’s some books that might also be useful.

- [Algorithms, 4th edition, by Robert Sedgewick and Kevin Wayne](http://www.amazon.com/Algorithms-4th-Edition-Robert-Sedgewick/dp/032157351X)
- [Introduction to Algorithms, 3rd Edition, by Thomas H. Cormen, Charles E. Leiserson, Ronald L. Rivest, and Clifford Stein (also referred as CLRS)](http://www.amazon.com/Introduction-Algorithms-Edition-Thomas-Cormen/dp/0262033844)
- [Think Complexity, by Allen B. Downey](http://greenteapress.com/complexity/thinkcomplexity.pdf)
- [Problems on Algorithms, 2nd edition, by Ian Parberry and William Gasarch](http://larc.unt.edu/ian/books/free/poa.pdf)
- [Data Structures and Algorithms in Java](http://rineshpk.weebly.com/uploads/1/8/2/0/1820991/data_structures_and_algorithms_in_javatqw_darksiderg.pdf)
- [Cracking the Coding Interview, 6th edition, by Gayle Laakmann McDowell](http://www.amazon.com/Cracking-Coding-Interview-6th-Programming/dp/0984782850/ref=sr_1_1?ie=UTF8&qid=1443719471&sr=8-1&keywords=coding+interview)

Typically, for an internship or your first job, questions won’t get much more specific unless you’re applying for a specific role. For example, if I wanted to be a mobile intern, I might be asked iOS/Android/Windows Phone specific questions, or if I wanted to be a web intern, I might be asked HTML/CSS/JavaScript questions, or if I wanted to be a backend intern, I might be asked about Django or Node or Ruby on Rails. That definitely depends on the company, and what you’re both looking for.

Make sure you’re able to implement and use the above data structures without the assistance of an IDE. Typically, onsite technical interviews involve coding on paper or a whiteboard, and phone/video interviews usually involve some kind of collaborative text editor. Yes, that means you won’t have access to auto-complete, auto-compiling, or the internet to check for errors. So be ready for that!

## Selling Them

When you’re actively emailing and speaking with recruiters, they’re going to ask you a lot of questions that are just checkboxes for what they’re looking for in terms of skills.

If you’ve written anything in a language before, **put it on your resume**. A lot of companies have parsers that look for specific things that, again, will put a tick on those checkboxes before putting you through to the next round of review. Now, if you’ve only ever done “Hello, world!” in Python, don’t say that you’re a Python ninja or whatever. You don’t want to be thrown into an interview that will only hurt your self-confidence. Speaking from experience. Trust me.

When a recruiter or engineer is asking you about a certain project you’ve done, or how you’ve used a particular language, be as specific as possible. Tell them **exactly** what you did on that particular project (or internship or what have you). Tell them how much you contributed, what languages you used, how long was the duration of development for that project, what was the outcome of the project, etc. etc.

For example, don’t say, “I’m the webmaster for a club website. Next question.” Okay, Dwight Schrute. Go back to your beet farm. Instead, say something more like this: “I developed and currently maintain the website for my university’s computer science club. I built it from the ground up with HTML, CSS, JavaScript, and jQuery on the front-end. It’s a static site, so a backend wasn’t needed. The website’s main function is to promote the club and give members crucial updates about meetings and events, and I update it regularly via a Python script I wrote.” Oh my, you enchanting software engineer, you. Let me hire you.

When you’re talking to companies about specific things you’ve done, make sure they know:

- **What?** - What? - What did you make? What does it do? What impact has it made? What was the hardest part? What could you have done better?
- **Why?** - Why did you make it? Was it for a hackathon, a school project, an open source contribution, or something else?
- **How?** - With which technologies did you make this? Did you use a specific API? What parts of it did you work on?
- **When?** - Did you do this recently or are you still living off of when you peaked in 10th grade?
- **Who?** - Did you work on this with anyone? Who did what? Who is this for?

Your skills are something that you have, and the reason why you have them is because you’ve used them in some way. All you have to do to prove yourself is to explain yourself! No need to go overboard and brag. Just be honest, and confident.

# Your Search

You have a resume and cover letter in hand, and you have the skills to make anyone want you. Now, you just have to find the right gig for you.

## Events

When you’re on the hunt for a great internship or first job, the events you go to can really set you apart, and will help you meet people that could potentially help you in the long run.

The biggies that you will definitely run into are:

- Hackathons
- Meetups
- Conferences
- Career Fairs

So, how do you find these events? They’re happening all the time, you just need to know where to look. Firstly, ask people in the field. Talk to a mentor, a fellow student, a professor, a colleague… anyone could come through for you! I remember my first tech event I went to in college was because I ran into a guy that I met orientation day. And now he and I are coworkers. Fancy that. Anyway, people can get you very far.

Otherwise, when people don’t work, we always have the glorious internet leading the way. There’s so many resources out there I definitely can’t list them all. So I’ll list just a few.

- Your School - Yeah, this is kind of an easy shot, but not a lot of people consider their schools as an event generator, when they should. Go on to your university’s website and find the career fair, find a seminar, find a company presentation, find something that will help you learn and meet people. You’ll probably find a lot of options!
- [Meetup](http://www.meetup.com) - Meetup is a great place to find groups of people who are interested in the same things you are, who meet regularly. Look for engineering meetups that are hosted **at** companies. You’ll get to see an office, and meet people who actually work there (in addition to those who might work at other organizations).
- [Eventbrite](https://www.eventbrite.com/) - Eventbrite is best for finding events that aren’t recurring. You can often find workshops, networking events, parties, and classes there. I tend to just search for the term, “tech” or “computer” and the results simply flow. Like a babbling brook. Or something.
- [Major League Hacking](https://mlh.io/) - MLH provides a fairly thorough schedule of university hackathons every semester. Most of the events on their schedule provide travel reimbursement, but there’s so many that you’ll likely find one near you!
- [Lanyrd](http://lanyrd.com/) - Lanyrd is a “social conference directory” that is full of conferences based on almost any topic. Follow your favorite speakers or search for a particular language or technology, and you’ll be set.

Like I mentioned before, there’s a lot of resources out there for finding events. Now that you have places to go to, what do you do there? WHAT A CLEVER SEGUE.

## Networking

The whole point of going to events (besides learning something, of course) is to network. Meeting and maintaining relationships with people in this industry is essential.

So, how **do** you just network with people? How do you make it as natural as eating pie on Pi Day? I’ll show you, Bert.

First of all, don’t think of it as networking. You don’t want to get the heebie-jeebies. Think of it as meeting people who like what you like. When you’re at these events, you’ll occasionally see groups of people staying in their own groups, not often reaching out to others. You’re not going to do that. You’re going to be a professional, social butterfly.

Follow generally these steps (as casually or formally as the event calls for) when networking:

1.  Introduce yourself. This seems obvious, but you’d be surprised how often people just sort of slide into a conversation without ever actually providing anyone with their name or title. Go up to people and tell them who you are.

2.  Make small talk about tech. Again, an obvious tip, but important. You want to know what this person’s skills are, and you want them to know yours. Someday, they might be looking for someone to help them on a project in a language that you know, or vice-versa. Get the important details out in the open about each other so that not only you can remember each other, but you can help each other out in the future. And don’t forget to have fun with it!

3.  Exchange contact information. If you have no way of finding the person you’re talking to again, and they don’t have a way of finding you, then you’re just wasting a potentially valuable connection. Whether you give them a business card or an email address, or even a Twitter handle, keep that information!

4.  Follow-up. This is probably **the most important thing I will tell you in this whole guide.** Hence the bold letters. So pretty. Anyway. Following up is the guaranteed way of leaving an impression with someone. Whether you email or tweet or InMail or Facebook message or pigeon mail, just sending a simple, “it was nice to meet you!” message is absolutely **vital** when it comes to networking. I’ve actually heard stories of people changing their mind about hiring someone based on a follow-up message. And following up doesn’t stop at the “nice to meet you” message. At some point down the line, it’s great practice to send a “how are you doing?” message to someone you’re interested in maintaining a relationship with. For all three of my mentors that I had in college (and to this day), the way we built our relationship was through these sorts of follow-up messages. **Do them.**

Networking is about building relationships, and what you can do with those relationships is up to you. But we’re talking about getting a job. So let’s move on to one of the best ways of getting one, with these relationships.

## Referrals

Referrals are your in. If you can get a referral from an employee of the company you’re applying for, that’s money. It pushes you towards the top of the pile of resumes that they’re getting every single day. Using the relationships you’ve built from networking, all it takes is a simple ask! You can get a referral from current employees, former ones, interns, former interns, friends of engineers, acquaintances of recruiters… really, anyone who is connected with the company. If they have a job posting up for a given position, they are looking around for engineers just as much as you’re looking around for a great gig! The company knows that they’re going to be speaking with someone potentially really good (because they were recommended by someone trusted), and you get to speak to a company for whom you want to work. Having a referral is a win for both parties.

Asking for a referral really depends on your relationship with the referrer. If you know them in a strictly business setting, you might want to send them a more professional request. But if you know the referrer pretty well, chances are you know how to ask for a favor. One thing that you must remember though is to, again, **follow up**! If you haven’t heard back from your referrer, reach out and check on your status. If they let you know that you’re in the system, be gracious and take them for coffee or something. Common courtesy. You’ve got this.

## Cold Calling

A lot of people are fans of cold calling, which is making unsolicited contact with a person at a company and hoping for something good to come of it. I admit, I’m not one of those people. Seems spammy. But, I’ll tell you about some ways to do that anyway, to make your cold calls as potentially successful as possible.

First of all, you should have an email for someone at the company you’re looking at. You could ask around your network for contact information for a given person, or you could just go out on a limb and [test some emails to see if they’re valid](http://mailtester.com/). A lot of companies have fairly standard email address templates (firstname.lastname@company.com, for example), so you can just keep sending a few until you find a legitimate one. If you need names to test out, you can scour LinkedIn or the company’s website to try and find something that works.

Once you have a legitimate email on your hands, get to work on making a personalized message to them. Emphasis on the personal. When you’re cold calling, you can’t have just any standard email template where you stick in the company’s name where it fits. You have to clearly let the person know why you’re writing, from where you got their information (if it’s not just a random guess, of course), why you would be a good fit for the company (where you will **sell** those awesome skills of yours), and why you think the company is great. Essentially, you’re writing a glorified cover letter.

When the email has been sent, you’re done. If you haven’t heard back in a week or two, send a follow-up, but if they still haven’t replied after that, chances are they won’t reply at all. And that’s okay. It happens. That’s the territory when it comes to cold calling.

## Fellowships

Fellowships are a great way to network with a community and get valuable mentorship that will most certainly help you in the long run. They vary depending on the program, but typically you’ll get assigned a mentor or two, go to several events to network with professionals, and intern for a company that has partnered with the specific fellowship program.

Here’s a list of some example fellowship programs. This is by no means a complete list (feel free to send a pull request or file an issue if there’s another you’d like to be added), but it should get you started!

- [Cansbridge Fellowship](http://www.cansbridgefellowship.com/)
- [CODE2040](http://code2040.org/)
- [FirstMark Elite](http://firstmarkelite.com/)
- [First Round Capital](http://www.university.firstround.com/)
- [Ford-Mozilla Fellows](https://advocacy.mozilla.org/open-web-fellows/)
- [hackNY Fellows](http://apply.hackny.org/)
- [Knight-Mozilla Fellows](http://opennews.org/fellowships/)
- [KPCB Fellows](http://kpcbfellows.com/)
- [Mayfield Fellows Program](http://stvp.stanford.edu/mayfield-fellows-program/)
- [NYC Turing Fellows](http://nycturingfellows.org/)
- [PennApps Fellows](http://www.pennappsfellows.com/)
- [True Entrepreneur Corps](http://www.trueventures.com/tec/)

In addition to these fellowships, several companies offer special programs for younger students that are similarly geared towards learning and mentorship. Here’s another list that is not complete, but will get you started:

- [Microsoft Explore](http://careers.microsoft.com/careers/en/us/university-programs.aspx) (I’m biased because I did this one, but this program is AWESOME)
- [Google Engineering Practicum](https://www.google.com/jobs/students/engpracticum)
- [Facebook University of Engineering](https://www.facebook.com/careers/university/fbueng)
- [Intel IRISE](http://www.intel.com/content/www/us/en/jobs/locations/united-states/students/internships/intel-early-internship-software-engineering.html)
- [Qualcomm EIP (Early Identification Program)](https://www.qualcomm.com/company/careers/interns)
- \[Pinterest Engage Software Engineer Intern\] (https://careers.pinterest.com/careers/details/pinterest-engage-software-engineer-intern\_san-francisco\_143952)

o overboard and brag. Just be honest, and confident.

# Your Search

You have a resume and cover letter in hand, and you have the skills to make anyone want you. Now, you just have to find the right gig for you.

## Events

When you’re on the hunt for a great internship or first job, the events you go to can really set you apart, and will help you meet people that could potentially help you in the long run.

The biggies that you will definitely run into are:

- Hackathons
- Meetups
- Conferences
- Career Fairs

So, how do you find these events? They’re happening all the time, you just need to know where to look. Firstly, ask people in the field. Talk to a mentor, a fellow student, a professor, a colleague… anyone could come through for you! I remember my first tech event I went to in college was because I ran into a guy that I met orientation day. And now he and I are coworkers. Fancy that. Anyway, people can get you very far.

Otherwise, when people don’t work, we always have the glorious internet leading the way. There’s so many resources out there I definitely can’t list them all. So I’ll list just a few.

- Your School - Yeah, this is kind of an easy shot, but not a lot of people consider their schools as an event generator, when they should. Go on to your university’s website and find the career fair, find a seminar, find a company presentation, find something that will help you learn and meet people. You’ll probably find a lot of options!
- [Meetup](http://www.meetup.com) - Meetup is a great place to find groups of people who are interested in the same things you are, who meet regularly. Look for engineering meetups that are hosted **at** companies. You’ll get to see an office, and meet people who actually work there (in addition to those who might work at other organizations).
- [Eventbrite](https://www.eventbrite.com/) - Eventbrite is best for finding events that aren’t recurring. You can often find workshops, networking events, parties, and classes there. I tend to just search for the term, “tech” or “computer” and the results simply flow. Like a babbling brook. Or something.
- [Major League Hacking](https://mlh.io/) - MLH provides a fairly thorough schedule of university hackathons every semester. Most of the events on their schedule provide travel reimbursement, but there’s so many that you’ll likely find one near you!
- [Lanyrd](http://lanyrd.com/) - Lanyrd is a “social conference directory” that is full of conferences based on almost any topic. Follow your favorite speakers or search for a particular language or technology, and you’ll be set.

Like I mentioned before, there’s a lot of resources out there for finding events. Now that you have places to go to, what do you do there? WHAT A CLEVER SEGUE.

## Networking

The whole point of going to events (besides learning something, of course) is to network. Meeting and maintaining relationships with people in this industry is essential.

So, how **do** you just network with people? How do you make it as natural as eating pie on Pi Day? I’ll show you, Bert.

First of all, don’t think of it as networking. You don’t want to get the heebie-jeebies. Think of it as meeting people who like what you like. When you’re at these events, you’ll occasionally see groups of people staying in their own groups, not often reaching out to others. You’re not going to do that. You’re going to be a professional, social butterfly.

Follow generally these steps (as casually or formally as the event calls for) when networking:

1.  Introduce yourself. This seems obvious, but you’d be surprised how often people just sort of slide into a conversation without ever actually providing anyone with their name or title. Go up to people and tell them who you are.

2.  Make small talk about tech. Again, an obvious tip, but important. You want to know what this person’s skills are, and you want them to know yours. Someday, they might be looking for someone to help them on a project in a language that you know, or vice-versa. Get the important details out in the open about each other so that not only you can remember each other, but you can help each other out in the future. And don’t forget to have fun with it!

3.  Exchange contact information. If you have no way of finding the person you’re talking to again, and they don’t have a way of finding you, then you’re just wasting a potentially valuable connection. Whether you give them a business card or an email address, or even a Twitter handle, keep that information!

4.  Follow-up. This is probably **the most important thing I will tell you in this whole guide.** Hence the bold letters. So pretty. Anyway. Following up is the guaranteed way of leaving an impression with someone. Whether you email or tweet or InMail or Facebook message or pigeon mail, just sending a simple, “it was nice to meet you!” message is absolutely **vital** when it comes to networking. I’ve actually heard stories of people changing their mind about hiring someone based on a follow-up message. And following up doesn’t stop at the “nice to meet you” message. At some point down the line, it’s great practice to send a “how are you doing?” message to someone you’re interested in maintaining a relationship with. For all three of my mentors that I had in college (and to this day), the way we built our relationship was through these sorts of follow-up messages. **Do them.**

Networking is about building relationships, and what you can do with those relationships is up to you. But we’re talking about getting a job. So let’s move on to one of the best ways of getting one, with these relationships.

## Referrals

Referrals are your in. If you can get a referral from an employee of the company you’re applying for, that’s money. It pushes you towards the top of the pile of resumes that they’re getting every single day. Using the relationships you’ve built from networking, all it takes is a simple ask! You can get a referral from current employees, former ones, interns, former interns, friends of engineers, acquaintances of recruiters… really, anyone who is connected with the company. If they have a job posting up for a given position, they are looking around for engineers just as much as you’re looking around for a great gig! The company knows that they’re going to be speaking with someone potentially really good (because they were recommended by someone trusted), and you get to speak to a company for whom you want to work. Having a referral is a win for both parties.

Asking for a referral really depends on your relationship with the referrer. If you know them in a strictly business setting, you might want to send them a more professional request. But if you know the referrer pretty well, chances are you know how to ask for a favor. One thing that you must remember though is to, again, **follow up**! If you haven’t heard back from your referrer, reach out and check on your status. If they let you know that you’re in the system, be gracious and take them for coffee or something. Common courtesy. You’ve got this.

## Cold Calling

A lot of people are fans of cold calling, which is making unsolicited contact with a person at a company and hoping for something good to come of it. I admit, I’m not one of those people. Seems spammy. But, I’ll tell you about some ways to do that anyway, to make your cold calls as potentially successful as possible.

First of all, you should have an email for someone at the company you’re looking at. You could ask around your network for contact information for a given person, or you could just go out on a limb and [test some emails to see if they’re valid](http://mailtester.com/). A lot of companies have fairly standard email address templates (firstname.lastname@company.com, for example), so you can just keep sending a few until you find a legitimate one. If you need names to test out, you can scour LinkedIn or the company’s website to try and find something that works.

Once you have a legitimate email on your hands, get to work on making a personalized message to them. Emphasis on the personal. When you’re cold calling, you can’t have just any standard email template where you stick in the company’s name where it fits. You have to clearly let the person know why you’re writing, from where you got their information (if it’s not just a random guess, of course), why you would be a good fit for the company (where you will **sell** those awesome skills of yours), and why you think the company is great. Essentially, you’re writing a glorified cover letter.

When the email has been sent, you’re done. If you haven’t heard back in a week or two, send a follow-up, but if they still haven’t replied after that, chances are they won’t reply at all. And that’s okay. It happens. That’s the territory when it comes to cold calling.

## Fellowships

Fellowships are a great way to network with a community and get valuable mentorship that will most certainly help you in the long run. They vary depending on the program, but typically you’ll get assigned a mentor or two, go to several events to network with professionals, and intern for a company that has partnered with the specific fellowship program.

Here’s a list of some example fellowship programs. This is by no means a complete list (feel free to send a pull request or file an issue if there’s another you’d like to be added), but it should get you started!

- [Cansbridge Fellowship](http://www.cansbridgefellowship.com/)
- [CODE2040](http://code2040.org/)
- [FirstMark Elite](http://firstmarkelite.com/)
- [First Round Capital](http://www.university.firstround.com/)
- [Ford-Mozilla Fellows](https://advocacy.mozilla.org/open-web-fellows/)
- [hackNY Fellows](http://apply.hackny.org/)
- [Knight-Mozilla Fellows](http://opennews.org/fellowships/)
- [KPCB Fellows](http://kpcbfellows.com/)
- [Mayfield Fellows Program](http://stvp.stanford.edu/mayfield-fellows-program/)
- [NYC Turing Fellows](http://nycturingfellows.org/)
- [PennApps Fellows](http://www.pennappsfellows.com/)
- [True Entrepreneur Corps](http://www.trueventures.com/tec/)

In addition to these fellowships, several companies offer special programs for younger students that are similarly geared towards learning and mentorship. Here’s another list that is not complete, but will get you started:

- [Microsoft Explore](http://careers.microsoft.com/careers/en/us/university-programs.aspx) (I’m biased because I did this one, but this program is AWESOME)
- [Google Engineering Practicum](https://www.google.com/jobs/students/engpracticum)
- [Facebook University of Engineering](https://www.facebook.com/careers/university/fbueng)
- [Intel IRISE](http://www.intel.com/content/www/us/en/jobs/locations/united-states/students/internships/intel-early-internship-software-engineering.html)
- [Qualcomm EIP (Early Identification Program)](https://www.qualcomm.com/company/careers/interns)
- \[Pinterest Engage Software Engineer Intern\] (https://careers.pinterest.com/careers/details/pinterest-engage-software-engineer-intern\_san-francisco\_143952)
