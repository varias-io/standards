# RFC: PHP Coding Standards

**Primary author(s)**: Giovan Angela

**Created**: 04-10-2022

**Last updated**: 04-10-2022

**Approver(s)**:

| Name | yes/not yet | date |
| ---- | ----------- | ---- |
|      | [ ]         |      |

## Overview
<!-- If someone only reads this far, what do you want them to know? -->

We should use some company wide standards in order to keep the styling of code as clean and consistant as possible per project, developer and environment. Therefore this RFC proposes to start using [PSR-12](https://www.php-fig.org/psr/psr-12/) as the standard for the PHP codebase.

## Goal
<!-- What problems are you trying to solve? What problems are you not trying to solve? -->

The aim of this proposal is to ensure every project and developer conforms to the same styling specification. This will help lower the amount of file changes that can be made by developers when they use their custom code formatter. This will also declutter the git history when used correctly.

## Motivation
<!-- What is the current state of the world? Why is this change being proposed? -->

There is currently no standard code style being used, outside of the Summa project. Developers use different code styles that are common by their respective IDE and this may lead to repeated file changes that are purely style changes. 

## Design
[PHP-CS-Fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer) will be used to check and fix the style of the php code that has been commited.

Using a github workflow action, found in the `.github` folder, we'll enable the check after each commit on a PR. This workflow will check the files that have been changed compared to the main branch.

Also added is a composer command, found in `composer.json`, to check and fix the code styling on a local machine using `composer phpcs` and `composer phpcs-fix` respectively.

## Drawbacks
<!-- What are the possible drawbacks of this proposal? ex. Higher costs, less flexibility for the developer, etc... -->
The drawbacks for this proposal could be:

For existing projects:
- Inconvenient to set up correctly
- One PR with an enormous amount of file changes related to styling
- If the style applier has a bug the effect of the code may change and introduce a fault or failure.

## Revisions
1. RFC created 