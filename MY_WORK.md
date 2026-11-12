 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---#

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Abdullah Feaz Aldowsiry |
| **Student ID** | 445050221 |
| **University Email** | 445050221@std.psau.edu.sa |
| **GitHub Username** | abdullahAl-dowsiry |
| **Repository Link** | https://github.com/abdullahAl-dowsiry/OS-Assignment3-Abdullah-Al-Dowsiry |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 10, 2026, Evening]

What I did: Set up my GitHub repository and cloned the assignment project into VS Code.

Details:

* Forked the original Assignment 3 repository and renamed my copy.
* Used Git Clone to download the repository into my Documents folder.
* Opened the project in VS Code and checked its files.

Challenges: At first, I typed Git Clone into the VS Code search panel instead of opening the command menu. I also had difficulty finding where to select the destination folder.

Solution: I used the Git Clone command correctly, selected the Documents folder, and opened the cloned repository in VS Code.

Time spent: 30 minute


---

### Entry 2 - [November 11, 2026, Afternoon]

What I did: Implemented Feature 1 to protect the shared ready queue using ReentrantLock.

Details:

* Added a ReentrantLock named queueLock inside the ReadyQueue class.
* Protected the add(), poll(), processOf(), and snapshot() methods.
* Used lock(), try, and finally to ensure the lock is released correctly.
* Compiled and tested the program.
* Committed and pushed Feature 1 to GitHub.

Challenges: I had difficulty identifying where to place the lock and unlock statements without breaking the methods.

Solution: I reviewed the critical sections and placed the shared queue operations inside try/finally blocks to ensure mutual exclusion.

Time spent: 60 minute


---

### Entry 3 - [November 11, 2026, Afternoon]

What I did: Implemented Feature 2 to protect the shared statistics from race conditions.

Details:

* Added a ReentrantLock named statsLock inside the SharedStats class.
* Protected contextSwitchCount, completedProcessCount, and totalServiceTime.
* Used lock() and try/finally in the methods that update these variables.
* Protected the getter methods to ensure synchronized reads.
* Successfully compiled the Java file and pushed Feature 2 to GitHub.

Challenges: I needed to understand why the shared counters required synchronization and how to protect their reading and updating operations.

Solution: I used one ReentrantLock for the three statistics and applied try/finally blocks to release the lock safely.

Time spent: 45 minute


---

### Entry 4 - [November 11, 2026, Evening]

What I did: Implemented Feature 3 to replace busy waiting with a counting semaphore.

Details:

* Added a Semaphore named availableItems to the ReadyQueue class.
* Used release() when a process was added to the ready queue.
* Added take() with acquire() so CPU threads wait when the queue is empty.
* Removed the old busy-waiting loop from CpuWorker.
* Added wakeWaitingCPUs() to allow blocked CPU threads to terminate.
* Ran the program five times and passed all four verification checks.
* Committed and pushed Feature 3 to GitHub.

Challenges: I had difficulty replacing the polling loop without causing errors or leaving CPU threads blocked.

Solution: I used the semaphore to block CPUs until work became available and added a shutdown mechanism. After correcting the code, all five tests passed with zero busy-waiting polls.

Time spent: 45 minute


---

### Entry 5 - [November 12, 2026, Evening]

What I did: Started documenting my work in the MY_WORK.md file.

Details:

* Read the documentation requirements and reviewed the development log instructions.
* Filled in my student information and GitHub repository link.
* Documented my work on the repository setup and the three synchronization features.
* Reviewed the successful verification results from my final program.

Challenges: I initially had difficulty locating the Student Information and Development Log sections in the file.

Solution: I used the search feature in VS Code to find the correct sections and filled them in step by step.

Time spent: 15 minute


---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

Development Log Summary

Total time spent on assignment: 3 hours and 15 minutes.

Most challenging part: Replacing busy waiting with a counting semaphore in Feature 3. I needed to make sure that CPU threads could wait for processes without getting stuck.

Most interesting learning: I learned how ReentrantLock protects shared data from race conditions and how Semaphore allows threads to wait without busy waiting. Seeing all four verification checks pass helped me understand synchronization better.

What I would do differently next time: I would read the code more carefully before making changes, test each feature separately, and document my progress after every work session.

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

I learned that synchronization helps threads work safely

Race conditions can happen when threads use the same data

I used ReentrantLock to protect shared data

I used try finally to release the locks

I also used Semaphore to stop busy waiting

After these changes my program passed all the tests

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The hardest part was Feature 3

I had to remove busy waiting

It was difficult to understand Semaphore at first

I was worried that some CPU threads would get stuck

I tested the program many times to fix the problem

Finally the program worked and passed all the tests

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I tried to understand the code first

I checked the errors in VS Code

I asked for help when I had problems

I fixed the code step by step

I tested the program after making changes

Finally I solved the problems and the program worked

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is useful in banking systems

It helps keep account balances correct

It is also useful in ticket booking systems

ReentrantLock can stop two threads from booking the same seat

Semaphore can help manage waiting jobs in a print queue

These tools help prevent problems with shared data

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

My first program had race conditions because the shared data was not protected

Two CPU threads could read the same value before updating it

This caused lost updates and incorrect results

RaceWindow made this problem easier to see but it can also happen without it

The problem is hard to detect because it depends on when the threads run

Verification block of the original starter:

Context switches
expected 32 observed 28 MISMATCH
Completed processes
expected 15 observed 13 MISMATCH
Total service time
expected 71917 observed 62018 MISMATCH
Busy waiting polls
expected 0 observed 834 MISMATCH

Verification block of my final version:

Context switches
expected 32 observed 32 PASS
Completed processes
expected 15 observed 15 PASS
Total service time
expected 71917 observed 71917 PASS
Busy waiting polls
expected 0 observed 0 PASS

Explanation of the timeline:

CPU 1 reads contextSwitchCount as 12

CPU 2 reads the same value 12 before CPU 1 updates it

RaceWindow pause makes this overlap easier to happen

CPU 1 writes 13 and CPU 2 also writes 13

The correct value should be 14 but the result is 13 so one update is lost

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*


I used queueLock to protect the ready queue and statsLock to protect the shared statistics

I used one statsLock for all three counters because it is simpler but separate locks could reduce waiting

I used a different lock for the queue so it does not block statistics operations

ReentrantLock provides mutual exclusion and try finally releases the lock so other threads can make progress

The default ReentrantLock is not fair so bounded waiting is not guaranteed and some threads may wait longer

Critical section	Lock used	Why it needs protection
ReadyQueue add()	queueLock	Protects the shared list and map
ReadyQueue poll()	queueLock	Prevents two CPUs from removing the same thread
ReadyQueue processOf()	queueLock	Protects access to the shared map
ReadyQueue snapshot()	queueLock	Protects reading the shared queue
contextSwitchCount	statsLock	Prevents lost updates
completedProcessCount	statsLock	Prevents incorrect counting
totalServiceTime	statsLock	Prevents lost updates
SharedStats getter methods	statsLock	Protects reads of shared statistics

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In my first test busy waiting caused 834 polls because CPUs kept checking the empty queue

I used a Semaphore called availableItems with an initial value of 0 to count available processes

After adding 15 processes the semaphore has 15 permits if no CPU has taken any yet

In my final program CPUs wait using acquire instead of busy waiting

When the last process finishes release wakes the waiting CPUs so they can stop otherwise they could wait forever

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*


This is the Producer Consumer problem

The main thread adds processes and the CPU workers consume them but CPU workers can also add processes back to the queue

For a bounded queue we need empty with K permits and full with 0 permits and mutex with 1 permit

Deadlock can happen if a producer holds mutex while waiting for an empty slot because the consumer cannot enter the queue

We can prevent this by waiting for an empty slot before taking mutex and this breaks the hold and wait condition

Classical problem and roles:

Producer Consumer problem

Producer is the main thread and CPU workers when they add processes back

Consumer is the CPU worker when it takes a process

Semaphores for a bounded queue:

empty = K

full = 0

mutex = 1

Deadlock scenario and prevention:

A producer locks mutex when the queue is full

The producer waits for empty but the consumer cannot take mutex to remove a process

Both threads become stuck

To prevent this the producer must wait for empty before locking mutex

This avoids holding mutex while waiting for another resource

## Summary

Key concepts I understood through these questions:

1. I learned how race conditions happen
2. I learned how ReentrantLock protects shared data
3. I learned how Semaphore prevents busy waiting

Concepts I need to study more:

1. How to prevent deadlock
2. How to choose the correct locks

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
