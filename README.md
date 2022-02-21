# 🌈 Welcome to Pintos

## Introduction

**Pintos is a simple operating system framework for the 80x86 architecture.** It supports **kernel threads**, **loading and running user programs**, and **a file system**, but it implements all of these in a very simple way. In the Pintos projects, you will strengthen its support in all three of these areas. You will also add a virtual memory implementation.

**Pintos could, theoretically, run on a regular IBM-compatible PC**. Unfortunately, it is impractical to supply every student a dedicated PC for use with Pintos. Therefore, we will run Pintos projects in a system simulator, that is, a program that simulates an 80x86 CPU and its peripheral devices accurately enough that unmodified operating systems and software can run under it. In class we will use the [Bochs](http://bochs.sourceforge.net) and [QEMU](http://fabrice.bellard.free.fr/qemu/) simulators. Pintos has also been tested with [VMware Player](http://www.vmware.com).

**These projects are hard.** They have a reputation of taking a lot of time, and deservedly so. We will do what we can to reduce the workload, such as providing a lot of support material, but there is plenty of hard work that needs to be done. We welcome your feedback. If you have suggestions on how we can reduce the unnecessary overhead of assignments, prevent students from being distracted by redundant work and help class participants concentrate on the more important underlying parts, please let us know.

## History

Pintos was originally developed at Stanford by Ben Pfaff [blp@cs.stanford.edu](mailto:blp@cs.stanford.edu) to substitute for the old OS course project Nachos. After more than a decade of iterations, Pintos has been adopted by over fifty institutes as the OS course project, including Stanford, UC Berkeley, Carnegie Mellon, Johns Hopkins, and so on. You can read the original [Pintos paper](https://benpfaff.org/papers/pintos.pdf) (Yes, they even write a paper for it !) to learn the details of Pintos' design philosophy and its comparison with other instructional operating system kernels, e.g., JOS, Nachos, GeekOS, and so on.

{% hint style="info" %}
**Why the name "Pintos"?:**

First, like nachos, pinto beans are common Mexican food. Second, Pintos is small and a "pint" is a small amount. Third, like drivers of the eponymous car, students are likely to have trouble with blow-ups. —— Ben Pfaff
{% endhint %}

## Project Overview

**There are five labs in total.** Lab0 is designed to prepare you for the later projects and practice your GDB ability, so it is intentionally much simpler than the remaining projects. In Lab1 - 4, you will extend Pintos in different dimensions and make it more robust and powerful.

| Project                       | Release   | Code Due           | Design Doc Due     | Content                                | Point |
| ----------------------------- | --------- | ------------------ | ------------------ | -------------------------------------- | ----- |
| **Lab0: Getting Real**        | **02/22** | **03/03 11:59 pm** | **03/03 11:59 pm** | Bootstrap Pintos                       | 4     |
| **Lab1: Threads**             | **03/08** | **03/24 11:59 pm** | **03/27 11:59 pm** | Kernel threads scheduling              | 9     |
| **Lab2: User Programs**       | **03/29** | **04/14 11:59 pm** | **04/17 11:59 pm** | Load & Run user programs, System calls | 9     |
| **Lab3a: Virtual Memory**     | **04/19** | **05/05 11:59 pm** | **05/08 11:59 pm** | Demand Paging                          | 9     |
| **Lab3a: Virtual Memory**     | **05/10** | **05/19 11:59 pm** | **05/22 11:59 pm** | Mmap Files                             | 9     |
| (optional) Lab4: File Systems | **/**     | /                  | /                  | Implement File systems                 | 0     |

**In each lab, we will release all the test cases to support your local development.** After the deadline, we will run the same test suite to grade your submissions, so don't worry that your evil teaching assistants (TAs) will intentionally design many corner cases only to deduct your scores.

However, your evil TAs firmly believe that there is a great difference between "elegant code" and "working code". **So a large part of your score will be determined by the quality of your design document and your code.** Don't worry, your kind TAs firmly resist "involution" and advocates "Ockham's Razor", so we will provide document templates for you to limit your document to hundreds of words long. Also, we will make the scoring criteria of coding style publicly available.

**In a word, we hope this project will be a challenging but rewarding experience for all of you guys.** If you have any suggestions, feel free to contact PKUFlyingPig zhongyinmin@pku.edu.cn.

## Prerequisite

We highly recommend you read the [prerequisites](https://pku-minic.github.io/online-doc/#/preface/prerequisites) and [facing-problems](https://pku-minic.github.io/online-doc/#/preface/facing-problems) sections of the PKU Compiler Project.

## Version Control

We highly recommend you to use Git for version control in the class. If you are new to Git, there are plenty of tutorials online you can read, e.g., [this one](https://csdiy.wiki/%E5%BF%85%E5%AD%A6%E5%B7%A5%E5%85%B7/Git/).

## Submission

We will be using [PKU course website](https://course.pku.edu.cn) to collect assignments and release your scores. See the submission section under each lab's description for more details.

**Pay attention to the deadline for each code and design doc submission.** Usually, the code submission dues three days earlier than its design doc submission (except for lab 0), which forces you to spend enough time to express your design ideas sufficiently but succinctly.

## Grading

**We will grade your assignments based on test results (60%) as well as design doc and code quality (40%).** Note that the testing grades are fully automated. So please turn in the working code, otherwise there is no credit (See section [Grading](broken-reference) for more details).

## <mark style="color:red;">Cheating and Collaboration</mark>

{% hint style="danger" %}
<mark style="color:red;">**This class has zero tolerance for cheating.**</mark> <mark style="color:red;"></mark><mark style="color:red;">We will run tools to check your submissions against a comprehensive database of solutions including past and present submissions for potential cheating. The stakes are very high. So do not cheat, do not cheat, do not cheat!</mark>
{% endhint %}

<mark style="color:red;">**The basic policies for the project assignments are as follows:**</mark>

* <mark style="color:red;">**Never copy project code or text found on the Internet**</mark><mark style="color:red;">, e.g., GitHub.</mark>
* <mark style="color:red;">**Never share code or text on the project.**</mark> <mark style="color:red;"></mark><mark style="color:red;">That also means do not make your solutions public on the Internet.</mark>
* <mark style="color:red;">**Never use others' code or text in your solutions.**</mark> <mark style="color:red;"></mark><mark style="color:red;">This includes code/text from prior years or other institutions.</mark>
* <mark style="color:red;">You may read but</mark> <mark style="color:red;"></mark><mark style="color:red;">**not**</mark> <mark style="color:red;"></mark><mark style="color:red;">copy Linux or BSD source code.</mark> <mark style="color:red;"></mark><mark style="color:red;">**You must cite any document or code that inspired your code**</mark><mark style="color:red;">. As long as you cite what you used, it's not cheating. In the worst case, we deduct points if it undermines the assignment.</mark>

**On the other hand, we encourage collaboration in the following form:**

* Explain a concept to another student, or ask another student to explain a concept to you.
* Discuss algorithms or approaches for an exercise. But you should not exchange, look at, or copy each other's code.
* Discuss testing strategies and approaches.
* Help someone else debug if they've got stuck. But you should not give that student code solution.

The course staff will actively detect possible ethics violations. For each project submission, **we will run automated cheating detection tools** to check your submission against a comprehensive database of solutions including solutions on the Internet, past submissions, and solutions from other institutions.

## What's next?

In the next chapter, you will set up your local development environment, boot Pintos and get familiar with its debugging and testing tools. You will use these utilities throughout the semester again and again and again. So read carefully and patiently \~\~
