# RFC: Git message standard

**Primary author(s)**: Giovan Angela

**Created**: 10-10-2022

**Last updated**: 10-10-2022

**Approver(s)**:

| Name | yes/not yet | date |
| ---- | ----------- | ---- |
|      | [ ]         |      |

## Overview
<!-- If someone only reads this far, what do you want them to know? -->
Use a short descriptive title and, if required, a longer explainatory body of what the commit is trying to fix, add, change, etc.

## Goal
<!-- What problems are you trying to solve? What problems are you not trying to solve? -->
The goal is to create a cleaner and descriptive `git log` such that, when looking back in the git history, it is easier to distinguish what has happend.

## Motivation
<!-- What is the current state of the world? Why is this change being proposed? -->
Currently no single convention is used in commit messages. This change would allow for a cleaner history.

Let's for example do the following commit:
`git commit -m "Derezz the master control program"`
This will result in the following `git log`:
```
commit f41c2eb121ee491234997c1f3ea4de2b5130f7ea
Author: Giovan Angela <deoxys@github.com>
Date:   Mon Oct 10 00:00:00 2022 +0200

    Derezz the master control program
```
Using a title and body by utilising a text editor with a body results in the following `git log`:

```
commit f41c2eb121ee491234997c1f3ea4de2b5130f7ea
Author: Giovan Angela <deoxys@github.com>
Date:   Mon Oct 10 00:00:00 2022 +0200

    Derezz the master control program

    MCP turned out to be evil and had become intent on world domination.
    This commit throws Tron's disc into MCP (causing its deresolution)
    and turns it back into a chess game.

    [Ticket: 542]
```
While still maintaining a "normal" `git log --oneline`:
```
f41c2e Derezz the master control program
```

## Design
For this to work a dev should not use the `git commit -m "descriptive text"` to commit, but rather use `git commit` which will open a text editor in which a title and body can be typed. Not changing the template will result in not performing a commit. A commit template (`.gitmessage.txt`) is provided in the `git` folder which contains the following text:

```
Subject line (try to keep under 50 characters)

Multi-line description of commit,
feel free to be detailed.

[Ticket: X]
```
This template can be set as the default message, per project, when running `git commit` by using the following command: `git config commit.template ./git/.gitmessage.txt`

In short:
- Separate subject from body with a blank line
- Limit the subject line to 50 characters
- Capitalize the subject line
- Do not end the subject line with a period
- Use the imperative mood in the subject line
- Wrap the body at 72 characters
- Use the body to explain what and why vs. how

## Drawbacks
<!-- What are the possible drawbacks of this proposal? ex. Higher costs, less flexibility for the developer, etc... -->
The drawbacks for this proposal could be:
- More work for the dev

## Revisions
1. RFC created 