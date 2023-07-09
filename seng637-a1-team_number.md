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

![Jira Project](https://github.com/seng637-summer/seng637-a1-chd-vicis/blob/main/media/JiraProject.png)
Screenshot of Jira Project

# High-level description of the exploratory testing plan

Below summarizes the groups test plan for exploratory testing followed by the two subgroups.  As testing was performed issues were created in Jira to log bugs and issues.

### General Approach
The team adopted a general approach to exploratory testing, which involved gaining an understanding of the System Under Test (SUT) along with its requirements, anticipated outcomes, and functionalities. They established expectations for creating bug reports in Jira and proceeded to utilize the software through "run-throughs" to acquaint each team member with the system and identify bugs. The bug report format was deliberately kept simple, consisting of four key inputs: initial state, detailed steps for reproduction, expected outcome, and actual outcome.

Prior to commencing the exploratory testing phase, the team read Appendix B to comprehend the SUT requirements. They compiled a broad list of test cases and operations to target, but it's important to note that these guidelines were intentionally kept general and non-prescriptive. The objective was to explore the software comprehensively, allowing flexibility to deviate from standard operations and prioritize edge cases or other critical areas as each team saw fit. The following is the list of general test cases that the teams utilized as guidelines.

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

There were notable distinctions between exploratory testing and manual functional testing regarding the obtained results and the efficiency of each approach. The primary dissimilarity between the two types lay in the fact that exploratory testing proved to be more challenging and demanded substantial critical thinking, whereas manual functional testing was straightforward, efficient, less time-consuming, and easier to navigate. The challenges associated with exploratory testing stemmed from it being conducted initially, requiring the teams to familiarize themselves with the software, thereby making expected outcomes less apparent during initial usage. Moreover, exploratory testing necessitated more critical thinking because the identification of bugs did not always provide immediate clarity regarding the specific factors that led to their occurrence. The ad-hoc nature of the operations performed during exploratory testing meant that the teams had to carefully consider the state of the System Under Test (SUT), the inputs used, and other factors such as previous actions that could have contributed to the bug. In contrast, manual functional testing benefited from well-defined states of the SUT, predetermined inputs, and expected outcomes. Another factor contributing to the perceived difficulty of exploratory testing was the occurrence of edge-case scenarios, where the exact outcomes may not have been known, even when referencing Appendix B. Consequently, exploratory testing demanded increased focus and was considered more challenging, while manual functional testing proved to be highly efficient, easily navigable, and less time-consuming.

In terms of results, it was noted that the majority of the bugs were found during the exploratory phase and the types of bugs found during the exploratory were more severe.  It is logical to find more bugs during the exploratory phase because it was performed first and there was more freedom to deviate from the different use cases.  While the MFT use cases were exhaustive they did not cover every type of operation performed, such as entering an invalid keyboard input when selecting a transaction type (issue A1-15).  In this case there is no MFT that would correspond to this operation so it would not have been found unless an even more exhaustive MFT list would have to have been created.  Creating exhaustive lists are challenging especially given that they are typically centered around use-cases which by its nature highlights typical operations as opposed to atypical.

The other noticeable difference between the bugs found in the exploratory vs the manual function testing was that the exploratory bugs found more severe bugs.  For example, MFT found only system breaking issue (program freezing or crashing) while exploratory testing found four (MFT-6/A1-23 & A1-2, A1-7, A1-10, A1-15).  This seems logical given that during software development one of the main challenges is accounting for all edge-cases and it is especially difficult given how many challenges arise when developing software such as requirement changes, team changes, merging of different code bases, reliance on libraries that are not fully visible or understood and multiple builds for different systems and environments to name a few.  Given these challenges, software testing and especially exploratory testing is one of the only places that edge-cases can realistically be identified.

Screenshot of A1-23 in Jira.  Note that this was a duplicate of A-7 so it is not included in the final list of bugs.
![A1-23]([https://github.com/seng637-summer/seng637-a1-chd-vicis/blob/main/media/JiraProject.png](https://github.com/seng637-summer/seng637-a1-chd-vicis/blob/main/media/A1-23.png))

# Notes and discussion of the peer reviews of defect reports
During the peer reviews of the defect reports, there was unexpectedly minimal discussion regarding comprehension of each other's bug reports, primarily due to the predetermined format of the reports. Only minor adjustments to wording were observed. The revisions made during the peer review process focused on enhancing the description of the System Under Test (SUT) state to achieve greater consistency across the reports. Additionally, it was observed that both teams found Jira to be a user-friendly and efficient tool, appreciating its simplicity and ease of use.

# How the pair testing was managed and team work/effort was divided 

Pair testing was organized by dividing the group into two subgroups: one with two members and the other with three members. Prior to starting any testing, all five members gathered and collectively reviewed the entire README file to ensure a shared understanding of the testing plan and laboratory requirements. Subsequently, each member created a Jira account and familiarized themselves with the issue tracker. Afterward, a project was created in Jira, and each member experimented with creating, editing and deleting issues to establish familiarity.  Once the lab requirements and Jira were familiar to everyone, the two subgroups commenced the exploratory testing phase. They allocated approximately 30 minutes for this phase, excluding the time spent on writing issues in Jira. After completing the exploratory testing, the entire group reconvened to review each other's issue lists and eliminate any duplicates. This was done systematically by going through the first subgroup's list, one item at a time, and cross-referencing it with the second subgroup's list to ensure no duplication.

For the MFT, the group continued in the same pair subgroups. The first subgroup handled test cases 1-20, while the second subgroup tackled cases 21-40. As new bugs were discovered, they were compared against the existing list and added only if they were unique. Once all the test cases were completed, the entire group gathered to discuss the identified issues and provide feedback (as noted in the previous section).  The testers also went through all the bugs found in version 1.0 individually to ensure consistency.

Finally the regression testing began with the entire team going through all the existing bugs in Jira and testing them in version 1.1 and making note if they were resolved or fixed.  Then the team perform the MFT again on all 40 cases in a similar approach as before, with the subgroups dividing the issues evenly and retesting them on the new version of the ATM. Throughout the regression testing if an issue was resolved, it was marked as such in Jira via the status button ("To Do" vs "Done"). If it remained unresolved, a comment was added to indicate its persistence in version 1.1. Additionally, comments were included to highlight any discrepancies between the systems if the issue was not resolved. For instance, issue A1-11 remained unresolved but with a difference expected outcome, so the issue was changed to reflect this.

Throughout the testing process, if either pair group had any questions or concerns about the overall process, they reached out to the other group via Discord to clarify their questions. Both groups ensured that they performed each testing phase in parallel to minimize deviations in the testing methodology.


# Difficulties encountered, challenges overcome, and lessons learned

### Difficulties encountered
-    Ensuring that duplicate issues of the same type were not entered in Jira posed a significant challenge. Although both teams collaborated, a substantial amount of effort was dedicated to reviewing each other's bugs and consolidating the lists
-    Comparing bugs often revealed similar but not identical data captured by both groups. This made it difficult to determine the exact cause of a bug. For instance, in bug A1-7, where an invalid pin freezes the system, it was not immediately clear whether the issue was due to the pin being too long or simply an incorrect number, as the teams used different pins.
-    Analyzing the differences between the various types of testing was not straightforward with respect to certain types of bugs such as benign bugs. While it was evident that all testing phases found benign bugs, it remained unclear which testing phases might be more effective for this because while exploratory testing seemed difficult it might not be the case for larger projects where the team would also need to create the MTF. 
 Although not feasible for a lab, with a much larger software program and proper metadata, it might have been easier to identify the most critical testing phase for finding benign bugs and allocate time accordingly.


### Challenges overcome
-    Avoiding duplicate bug entries in Jira during manual function testing required diligent searching to ensure that bugs were not already captured during exploratory testing.
-    Keeping track of all the high-level system requirements proved time-consuming and necessitated frequent referencing of Appendix B.
-    The testing process took longer than anticipated, leading to rescheduling of meetings to cover the entire test suite. However, the team managed to complete the testing in a timely manner.
-    Regression testing was greatly streamlined because each group divided the list of issues and tested them separately.

### Lessons learned
-    Exploratory testing takes far more critical thinking than MFT
-   MFT is more efficient, less time consuming and less ambiguous when recording results than exploratory
-    Establishing a specific outline for bug issues during the exploratory phase is crucial to avoid missing information when merging results from different pairs/groups.
-    Regular communication between pair groups during exploratory sessions helps prevent significant discrepancies in issue descriptions before too many issues were logged.
-    Extending the duration of exploratory testing beyond the suggested 30 minutes, as mentioned in the README, could have been beneficial, as it appeared to be the most productive testing phase

