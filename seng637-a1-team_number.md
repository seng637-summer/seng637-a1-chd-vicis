# SENG 637 - Dependability and Reliability of Software Systems

## Lab. Report \#1 – Introduction to Testing and Defect Tracking

| Group: SENG637- 2   |
|-----------------|
| Jash Dubal                |   
| Steven Duong              |   
| Nikhil Naikar               |   
| Jason Xu                |
| Christopher DiMattia                |


**Table of Contents**

[1. Introduction](#introduction)

[2. High-level description of the exploratory testing plan](#high-level-description-of-the-exploratory-testing-plan)

[3. Comparison of exploratory and manual functional testing](#comparison-of-exploratory-and-manual-functional-testing)

[4. Notes and discussion of the peer reviews of defect reports](#notes-and-discussion-of-the-peer-reviews-of-defect-reports)

[5. How the pair testing was managed and team work/effort was divided](#how-the-pair-testing-was-managed-and-team-work/effort-was-divided)

[6. Difficulties encountered, challenges overcome, and lessons learned](#difficulties-encountered,-challenges-overcome,-and-lessons-learned)

# Introduction

In this lab, Team 2 of SENG-637 conducted software testing on an ATM simulation system, which can be accessed [here](https://github.com/seng637-summer/seng637-a1-chd-vicis/blob/main/seng637-a1-artifacts.zip).  The primary objective of the lab was to apply the lessons and techniques learned in the lectures to a practical software testing scenario. The team focused on achieving three specific goals:
1. Acquire practical experience in testing a software system
2. Understand and gain experience in three different types of testing: exploratory, manual scripted, and regression testing
3. Utilize and become familiar with a professional issue tracking system such as Jira 

Throughout the lab, the team successfully conducted exploratory, manual scripted, and regression testing, which resulted in the discovery of 18 unique bugs. These bugs were documented using Jira, a professional issue tracking system. The team found the experience of using Jira valuable, collaborated on pair testing for the first time, and composed practical bug reports. Additionally, they gained insights into the strengths and weaknesses of various testing approaches and how they complement each other.

Before undertaking this lab, the team members had a brief understanding of software testing including exploratory and manual function testing from the class lectures but lacked practical experience. More specifically the team members went through examples in class on how to perform a manual scripted test by recording the initial state, expected output vs actual and how to reproduce the bug of a software system.  Aside from the class examples the team's only testing experience was limited to ad-hoc testing while developing programs during undergraduate and graduate courses. Furthermore, the team had no prior exposure to a professional issue tracker such as Jira.

![Jira Project]([path/to/image.jpg](https://github.com/seng637-summer/seng637-a1-chd-vicis/blob/main/media/JiraProject.png))
Screenshot of Jira Project

# High-level description of the exploratory testing plan

Below summarizes the groups test plan for exploratory testing followed by the two pair groups.  As testing was performed issues were created in Jira to log bugs and issues.

### General Approach
The team's general approach to exploratory testing was to understand the SUT (system under test) and its general requirements, expected outcomes and functionalities, set expectations for writing bug reports in Jira and then use the software and perform "run-throughs" to familiarize each team with the software and identify bugs.  Before beginning the exploratory testing and after reading Appendix B to understand the SUT requirements, the team developed a general list of test cases and operations to target, but it should be noted these were kept very general and non-prescriptive as the focus is on exploring the software and allowing the team flexibility to deviate from standard operations and focus on edge-cases or any other focus that seems critical during the testing.  Below is the list of general test cases the team's used as guides.

### Test Cases & ATM Requirements Targeted
Card Validation & Pin Verification
-    Test valid/invalid cards
-    Test valid/invalid PINs
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
-    Test balance inquiry for a invalid account
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

Operator
-    Test turning on/off the ATM system
-    Testing loading the system with money  

# Comparison of exploratory and manual functional testing

There were several differences between the exploratory and manual functional testing in terms of results and how efficient each type was to perform.  The most noticeable difference between the two types was the exploratory testing was noted to be more challenging and required significant critical thinking whereas MFT was extremely straight forward, efficient, less time consuming and easier to navigate.  It's believed that exploratory testing was more challenging because it was done first so the team's had to familiarize themselves with the software, so expected outcomes were not as obvious upon first use.  Exploratory testing also required more critical thinking because when bugs were found it wasn't always obvious what set of factors led to the bug because the exact set of operations that created the bug were done ad-hoc and so the team's had to think critically about the state of the SUT, the inputs and if other factors such as previous actions may have led to a bug whereas in MFT the state of the SUT, the exact input and expected outcome is already well defined.  Another reason exploratory testing was considered more difficult was because the team's ended up in edge-case scenarios and so the exact outcome may not have been known even with Appendix B.  As a result, the exploratory testing was considered more difficult and required more focus while the MFT was considered extremely efficient, easy to navigate and less time consuming.

In terms of results, it was noted that the majority of the bugs were found during the exploratory phase and the types of bugs found during the exploratory were more severe.  It is logical to find more bugs during the exploratory phase because it was performed first and there was more freedom to deviate from the different use cases.  While the MFT use cases were exhaustive they did not cover every type of operation performed, such as entering an invalid keyboard input when selecting a transaction type (issue A1-15).  In this case there is no MFT that would correspond to this operation so it would not have been found unless an even more exhaustive MFT list would have to have been created.  Creating exhaustive lists are challenging especially given that they are typically centered around use-cases which by its nature highlights typical operations as opposed to atypical.

The other noticeable difference between the bugs found in the exploratory vs the manual function testing was that the exploratory bugs found more severe bugs.  For example, MFT found only system breaking issue (program freezing or crashing) while exploratory testing found four (MFT-6/A1-23 & A1-2, A1-7, A1-10, A1-15).  This seems logical given that during software development one of the main challenges is accounting for all edge-cases and it is especially difficult given how many challenges arise when developing software such as requirement changes, team changes, merging of different code bases, reliance on libraries that are not fully visible or understood and multiple builds for different systems and environments to name a few.  Given these challenges, software testing and especially exploratory testing is one of the only places that edge-cases can realistically be identified.

# Notes and discussion of the peer reviews of defect reports
During the peer reviews of the defect reports there was surprisingly little discussion with respect to understanding each other team's bug reports because the format of the bug report was determined beforehand.  Only minor changes to wording was noted.  Any changes to bug reports during the peer review was centered around describing the state of the SUT to ensure more consistency between reports.  It was also noted that Jira was straightforward and easy to use with both team's noting how efficient and simple it was to use.

# How the pair testing was managed and team work/effort was divided 

Pair testing was organized by dividing the group into two subgroups: one with two members and the other with three members. Prior to starting any testing, all five members gathered and collectively reviewed the entire README file to ensure a shared understanding of the testing plan and laboratory requirements. Subsequently, each member created a Jira account and familiarized themselves with the issue tracker. Afterward, a project was created in Jira, and each member experimented with creating, editing and deleting issues to establish familiarity.  Once the lab requirements and Jira were familiar to everyone, the two subgroups commenced the exploratory testing phase. They allocated approximately 30 minutes for this phase, excluding the time spent on writing issues in Jira. After completing the exploratory testing, the entire group reconvened to review each other's issue lists and eliminate any duplicates. This was done systematically by going through the first subgroup's list, one item at a time, and cross-referencing it with the second subgroup's list to ensure no duplication.

For the MFT, the group continued in the same pair subgroups. The first subgroup handled test cases 1-20, while the second subgroup tackled cases 21-40. As new bugs were discovered, they were compared against the existing list and added only if they were unique. Once all the test cases were completed, the entire group gathered to discuss the identified issues and provide feedback (as noted in the previous section).  The testers also went through all the bugs found in version 1.0 individually to ensure consistency.

Finally the regression testing began with the entire team going through all the existing bugs in Jira and testing them in version 1.1 and making note if they were resolved or fixed.  Then the team perform the MFT again on all 40 cases in a similar approach as before, with the subgroups dividing the issues evenly and retesting them on the new version of the ATM. Throughout the regression testing if an issue was resolved, it was marked as such in Jira via the status button ("To Do" vs "Done"). If it remained unresolved, a comment was added to indicate its persistence in version 1.1. Additionally, comments were included to highlight any discrepancies between the systems if the issue was not resolved. For instance, issue A1-11 remained unresolved but with a difference expected outcome, so the issue was changed to reflect this.

Throughout the testing process, if either pair group had any questions or concerns about the overall process, they reached out to the other group via Discord to clarify their questions. Both groups ensured that they performed each testing phase in parallel to minimize deviations in the testing methodology.


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
-    Exploratory testing takes far more critical thinking than MFT
-   MFT is more efficient, less time consuming and less ambiguous when recording results than exploratory
-    Establishing a specific outline for bug issues during the exploratory phase is crucial to avoid missing information when merging results from different pairs/groups.
-    Regular communication between pair groups during exploratory sessions helps prevent significant discrepancies in issue descriptions before too many issues were logged.
-    Extending the duration of exploratory testing beyond the suggested 30 minutes, as mentioned in the README, could have been beneficial, as it appeared to be the most productive testing phase

