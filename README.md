# pyGitHook
This repository provides various useful Git Hooks written in Python.

## History
This project was initially created to answer [this issue on StackOverflow](https://stackoverflow.com/a/53284942/10524205).

The needs was to prevent merging from 'testing' branch in something else than the 'master' one.

## References
If you need to learn Git Hook, check the [official Git Book](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)

You can easily integrate with various code hosting platform, for instance:

 - [GitHub](https://developer.github.com/webhooks/)
 - [GitLab](https://docs.gitlab.com/ee/administration/custom_hooks.html)
 - [BitBucket](https://confluence.atlassian.com/bitbucketserver/using-repository-hooks-776639836.html)

## Usage
You just need to download the hook(s) you want, and put them in the .git/hooks/ sub-directory of your repository.

You must keep the same name, which corresponds to what Git awaits.

### Prevent merging between some branches
**prepare-commit-msg** is what you need.

You just need to adapt the constants at beginning of the script.

_Documentation will be updated soon_
