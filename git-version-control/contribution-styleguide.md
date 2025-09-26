# Contribution Styleguide
```
Author:   Carter Dugan
          CarterDugan@asei.com
Created:  9/26/2025
Modified: 9/26/2025
```


## Table of Contents

* [Disclaimer](#disclaimer)
* [Overview](#overview)
* [Versioning](#versioning)
* [Branching Convention](#branching-convention)
    * [Classification](#classification)
    * [Verbosity](#verbosity)
    * [Synchronization](#synchronization)
* [Pull Requests](#pull-requests)
    * [Conflict Resolution](#conflict-resolution)
    * [Details](#details)
        * [Titles](#titles)
        * [Descriptions](#descriptions)
        * [Reviewers](#reviewers)
        * [Labels](#labels)
    * [Review Process](#review-process)
    * [Merge Strategy](#merge-strategy)



## Disclaimer

This document is a work in progress. If you are unfamiliar with Git, you should at least consult the [quickstart](./quickstart.md) guide and the [additional resources](./README.md/#additional-resources) highlighted in the [README](./README.md).


## Overview

Our contribution philosphy aims to provide a simple method of collarboarting on code that is both intuitive and thorough. For that reason, we will not be re-inventing the wheel, but integrating the existing Trunk-Based Development strategy. **For a large, detailed collection of documentation on T-BD, look [here](https://trunkbaseddevelopment.com/)**. This document will detail the most important aspects of the strategy as it relates to American Sound's open source and proprietary code bases.

## Versioning

Versions are tracked in the following format: `vMAJOR.MINOR.PATCH`. For example, `v1.0.0` is the first major release with no patches. `v1.2.3` is the **first** major release with **two** minor updates and **three** patches since `v1.0.0`'s release.

## Branching Convention

### Classification

Branches should be classified into the following categories:

* `feature` branches consist of code for new features. Typically, a project would have several features added as minor updates before a desired state is reached for a release. So, several `vMAJOR.MINOR+1.PATCH`s before a `vMAJOR+1.MINOR.PATCH`

* `bugfix` branches should branch from the *most recent* commit in `main`. This is for low-priority bugs.

* `hotfix` branches should branch from the *latest release tag* in `main`. Upon merge of a hotfix branch, the patch digit in the version number should be updated in a new release tag `vMAJOR.MINOR.PATCH+1`


### Verbosity

When creating a branch, the branch name should be prefixed with the classification in the style of `<classification>/<branchname>`. Branch names should be brief but descriptive. Here are some examples:

* `feature/xyz-device-driver-support`
* `feature/front-page-ui-overhaul`
* `bugfix/database-negative-db-index-edgecase`
* `bugfix/rare-crash-from-invalid-ui-resolution`
* `hotfix/major-elf-config-file-corruption`
* `hotfix/libraryname-lib-security-patch`


### Synchronization

To synchronize a branch with `main`, we rebase.

## Pull Requests

### Conflict Resolution

### Details

### Review Process

### Merge Strategy