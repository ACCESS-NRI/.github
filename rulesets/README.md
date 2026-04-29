# Rulesets

Rulesets are newer versions of branch protection rules - they can be layered, bypassed, and can control how tag/branch patterns (including the default branch) can be created, modified, and deleted. See more at https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets.

Since rulesets are in JSON, they can be imported and exported in a repository via `Settings > Rules > Rulesets > New ruleset > Import a ruleset`. Having a basic, common set of rules throughout the organisation is good for consistency and repository protection. So, we have a couple of rulesets ready to go for people to stand up repos quickly. 

## The Rulesets

Note that these rulesets can be edited after import, or more specific rulesets layered on top.

### Base Ruleset

**File:** [base-ruleset.json](https://github.com/ACCESS-NRI/.github/blob/main/rulesets/base-ruleset.json)

This ruleset contains a basic list of protections:

Bypass List:

* Organisation Admins
* Repository Admins

Branches these rules match:

* Default branch

Restrictions:

* Restricts deletions
* Blocks force pushes

PR Rules:

* Requires 1 Approval
* Requires review from Code Owners where appropriate

### Stricter PR Ruleset

**File:** [strict-pr-ruleset.json](https://github.com/ACCESS-NRI/.github/blob/main/rulesets/strict-pr-ruleset.json)

All of the above, and:

PR Rules:

* Dismisses stale PR approvals when new commits are pushed
* Requires review of the most recent reviewable push
* Requires conversation resolution before merging
