# Steward publication setup

Publish to `https://github.com/StewardFinancial/steward.git` using a dedicated team publishing account. Keep the development repository private.

Configure the approved publishing login in local Git configuration as `steward.publisherLogin`; do not put a personal account identifier in tracked files. Configure `user.name` as `Steward Team` and `user.email` as `team@steward.invalid`. This reserved, non-deliverable address provides unlinked team attribution; it is not a verified GitHub identity. Enable the local guard with `git config --local core.hooksPath .githooks`.

The guard requires the approved authenticated publishing account, the organization remote, and team author/committer metadata throughout the proposed history. An organization name or commit author label does not hide the authenticated pushing account from GitHub activity. Use the dedicated team publishing account for Git transport too.

Create the organization's `steward-team` team with repository write access before relying on CODEOWNERS. Protect main from force pushes and deletion, and require signed commits once the dedicated publishing account has its signing identity configured. Local guards cannot replace remote protections. Keep an independently stored release manifest.
