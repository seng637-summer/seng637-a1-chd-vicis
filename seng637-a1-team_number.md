# SENG 637 - Dependability and Reliability of Software Systems

## Lab. Report \#1 – Introduction to Testing and Defect Tracking

| Group: 1      |
|-----------------|
| Jash Dubal                |   
| Steven Duong              |   
| Nikhil Naikar               |   
| Jason Xu                |
| Christopher DiMattia                |


**Table of Contents**

(When you finish writing, update the following list using right click, then
“Update Field”)

[1. Introduction](#introduction)

[2. High-level description of the exploratory testing plan](#high-level-description-of-the-exploratory-testing-plan)

[3. Comparison of exploratory and manual functional testing](#comparison-of-exploratory-and-manual-functional-testing)

[4. Notes and discussion of the peer reviews of defect reports](#notes-and-discussion-of-the-peer-reviews-of-defect-reports)

[5. How the pair testing was managed and team work/effort was divided](#how-the-pair-testing-was-managed-and-team-work/effort-was-divided)

[6. Difficulties encountered, challenges overcome, and lessons learned](#difficulties-encountered,-challenges-overcome,-and-lessons-learned)

# Introduction

An introduction of your lab work, and what you knew about exploratory and manual
functional testing before this lab

In this lab, Team 1 of SENG-637 conducted software testing on an ATM simulation system, which can be accessed [here](https://github.com/seng637-summer/seng637-a1-chd-vicis/blob/main/seng637-a1-artifacts.zip).  The primary objective of the lab was to apply the lessons and techniques learned in the lectures to a practical software testing scenario. The team focused on achieving three specific goals:
1. Acquire practical experience in testing a software system
2. Understand and gain experience in three different types of testing: exploratory, manual scripted, and regression testing
3. Utilize and become familiar with a professional issue tracking system such as Jira 

Throughout the lab, the team successfully conducted exploratory, manual scripted, and regression testing, which resulted in the discovery of 21 unique bugs. These bugs were documented using Jira, a professional issue tracking system. The team found the experience of using Jira valuable, collaborated on pair testing for the first time, and composed practical bug reports. Additionally, they gained insights into the strengths and weaknesses of various testing approaches and how they complement each other.

Before undertaking this lab, the team members had a theoretical understanding of software testing from the class lectures but lacked practical experience. Their testing experience was limited to ad-hoc testing while developing programs during undergraduate and graduate courses. Furthermore, the team had no prior exposure to a professional issue tracker such as Jira.

# High-level description of the exploratory testing plan

Below summarizes the groups test plan for exploratory testing followed by the two pair groups.  As testing was performed issues were created in jira to log potential bugs.

## General Approach
1. Read and understand the system's high level requirements found in Appendix B and make note of potential areas for bugs 
2. Familiarization with the ATM System - perform a single run-through via a transaction (deposit) as described in the README
3. Explore standard functionalities of a user such as performing transactions
4. Explore standard functionalities of an operator such as entering how many $20 bills are in the ATM
5. Explore non-standard functionalities and attempt operations that shouldn't be allowed

## Test Cases & ATM Requirements Targeted
Card Validation & Pin Verification
-    Test valid card
-    Test invalid card
-    Test valid card and valid PIN
-    Test valid card with invalid PIN
-    Test card retention after three consecutive invalid PIN attempts

Cash Withdrawal
-    Test successful and insufficient balance cash withdrawal from valid savings, checking, and money market accounts

Deposit Processing
-    Test deposit to all the valid accounts

Money Transfer
-    Test successful transfer between two valid accounts
-    Test transfer with an invalid source or destination account
-    Test transfer with insufficient balance

Balance Inquiry
-    Test balance inquiry for a invalid accound
-    Test balance inquiry for an invalid account

Transaction Cancellation
-    Test transaction cancellation using the Cancel key
-    Test transaction cancellation at various stages (withdrawal, deposit, transfer)

User Interface
-    Test keyboard input for all transaction types
-    Test display output for transaction status, prompts, and error messages

Receipt Generation
-    Test receipt generation for successful transactions
-    Test receipt content for accuracy (date, time, location, transaction details, balances)

# Comparison of exploratory and manual functional testing

There were several difference between the exploratory and manual functional testing.  The two main difference were, the majority of the bugs were found during the exploratory phase and the types of bugs found during the exploratory were more severe.  It is logical to find more bugs during the exploritory phase because it was performed first and there was more freedom to devitate from the different use cases.  While the SUT (system under test) use cases were fairly exhaustive they did not cover every possible type of operation performed, such as entering an invalid keyboartd input when selecting a transaction type (issue A1-15).  In this case there is no MFT that would correspond to this operation so it wouldn't have been found unless an even more exhaustive MFT list would have to have been created.  Creating exhaustive lists are challengeing especially given that they are typically centered around use-cases which by it's nature highlights typical operations as opposed to atypical.

The other noticable difference between the bugs found in the exploratory vs the manual function testing was that the exploratory bugs often found more severe bugs.  For example MFT found only one major issue (program freezing or crashing) while exploratory testing found three (MFT-6 & A1-15, A1-10, A1-7).  This seems logical given that during software development one of the main challenges is accounting for all edge-cases and it is especially difficult given how many challenges arise when developing software such as requirement changes, team changes, merging of different code bases, reliance on libraries that are not fully visible or understood and multiple builds for different systems and enviroments to name a few.  Given these challenges, software testing and especially exploratory testing is one of the only places that edge-cases can realistically be identified.

A similarity between exploratory and MFT was that both found a significany amount of benign bugs such as showing incorrect information (MFT-14 & A1-13).  This is expected given that begnign bugs are likely to be the most common and both testing schemes are suited for finding these types of bugs.

# Notes and discussion of the peer reviews of defect reports
Did both teams find the reports to be the same?
Were there different approaches?
How did you compare after finishing?
Two jira project created and then merged?

# How the pair testing was managed and team work/effort was divided 

Pair testing was managed by splitting the group into two groups, one group of two and another of three.  Before any testing was started all five members met and reviewed the entire README file together to ensure a common understanding of the testing plan and lab requirments.  Afterwards each member made a Jira account and familiarized themselves with the issue tracker after which point a project was made in Jira and each member ensured they could create, edit and delete issues.  After familiariztion with the lab requirements and Jira the two groups began the exploratory testing phase and spent rouglhy 30 minutes (not including writing issues in Jira) perfomring exploratory testing.  After the exploratory testing the group met, reviewed each other's list of issues and removed duplicate issues.  This was done by group through the first groups list one by one and searching the other groups list to ensure it was not duplicated.

The group performed MFT in the same pair groups but with the first group doing test cases 1-20 while the second group performed cases 21-40.

Throughout the testing if a group had questions about the overall process then they reach out to the other group over discord and clarified their issue.  Both groups made sure to perform the each testing phase in parrallel to avoid large deviations in how the testing was performed.

# Difficulties encountered, challenges overcome, and lessons learned

### Difficulties encountered
-    Ensuring that duplicate issues of the same type were not entered in Jira posed a significant challenge. Although both teams collaborated, a substantial amount of effort was dedicated to reviewing each other's bugs and consolidating the lists
-    Comparing bugs often revealed similar but not identical data captured by both groups. This made it difficult to determine the exact cause of a bug. For instance, in bug A1-7, where an invalid pin freezes the system, it was not immediately clear whether the issue was due to the pin being too long or simply an incorrect number, as the teams used different pins.
-    Analyzing the differences between the various types of testing was not straightforward. While it was evident that all testing phases were important, it remained unclear which testing phases might be more effective in terms of bug severity or types (user vs. operator). Although not feasible for a lab, with a much larger software program and proper metadata, it might have been easier to identify the most critical testing phase for finding "system-breaking" bugs and allocate time accordingly.


### Challenges overcome
-    Avoiding duplicate bug entries in Jira during manual function testing required diligent searching to ensure that bugs were not already captured during exploratory testing.
-    Keeping track of all the high-level system requirements proved time-consuming and necessitated frequent referencing of Appendix B.
-    The testing process took longer than anticipated, leading to rescheduling of meetings to cover the entire test suite. However, the team managed to complete the testing in a timely manner.
-    Learning and becoming familiar with Jira was a straightforward task that was easily overcome.
-    Regression testing was greatly streamlined because each group divided the list of issues and tested them separately.

### Lessons learned
-    Establishing a specific outline for bug issues during the exploratory phase is crucial to avoid missing information when merging results from different pairs/groups.
-    Regular communication between pair groups during exploratory sessions helps prevent significant discrepancies in issue descriptions before too many issues were logged.
-    Extending the duration of exploratory testing beyond the suggested 30 minutes, as mentioned in the README, could have been beneficial, as it appeared to be the most productive testing phase

