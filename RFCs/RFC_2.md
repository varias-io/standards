# RFC: Branch and PR naming and tagging convention

**Primary author(s)**: Giovan Angela

**Created**: 10-10-2022

**Last updated**: 10-10-2022

**Approver(s)**:

| Name | yes/not yet | date |
| ---- | ----------- | ---- |
|      | [ ]         |      |

## Overview
<!-- If someone only reads this far, what do you want them to know? -->
Use one convention when naming branches or PR's.

## Goal
<!-- What problems are you trying to solve? What problems are you not trying to solve? -->
The goal is to have one naming convention for PR's and branches such that it creates a clearer overview of the branches and allows for easier searching, by example on ticket number. Coincidentally this also enhances the developer experience in the terminal when using the autocomplete feature.

## Motivation
<!-- What is the current state of the world? Why is this change being proposed? -->
There are several types of names beings used without a clear structure. Some even use the name to indicate if it is an enchancement, feature, bugfix, etc... This does not give an organised or professional impression. Cleaning this mess up would, in time, help enhance the education of our developers and keeps our codebase organised.


## Design
<!-- How will this be implemented? -->
Use the Jira board issue title as PR and branch title. For example this fictive issue for Summa (SUM-415) with description "Add documentation for undocumented code" will have a branch named "sum-415/add-documentation-for-undocumented-code" and it's PR will should be named "SUM-415 Add documentation for undocumented code". For branches and PRs that do not have an issue in Jira -> create a ticket in Jira.

Set of labels that can be used to give an indication of the type of the PR:
- Bugfix -> Something isn’t working
- Discussion -> There is an open discussion which needs to be resolved first
- Documentation -> An improvement/addition to the documentation
- Enhancement -> An improvement to existing functionality OR the developer experience
- Feature -> A new feature
- Help Wanted -> The assignee encountered an issue and need help
- Housekeeping -> Something that keeps or makes the codebase clean(er) 
- Refactor -> A change to the codebase with no impact on the current behaviour

## Drawbacks
<!-- What are the possible drawbacks of this proposal? ex. Higher costs, less flexibility for the developer, etc... -->
The drawbacks for this proposal could be:
- Cluttering Jira with new issues
- Long branch names

## Revisions
1. RFC created 
2. Updated the goal and motivation
