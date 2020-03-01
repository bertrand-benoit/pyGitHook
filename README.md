:warning: This project is now hosted on [Gitlab](https://gitlab.com/bertrand-benoit/pyGitHook); switch to it to get newer versions.

# pyGitHook
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/3c849e832c8a4656ad983a7277227437)](https://www.codacy.com/manual/gitlabRepositories/pyGitHook_2?utm_source=gitlab.com&amp;utm_medium=referral&amp;utm_content=bertrand-benoit/pyGitHook&amp;utm_campaign=Badge_Grade)

This repository provides various useful Git Hooks written in Python.

## History
This project was initially created to answer [this issue on StackOverflow](https://stackoverflow.com/a/53284942/10524205).

The needs was to prevent merging from 'testing' branch in something else than the 'master' one.

## References
If you need to learn Git Hook, check the [official Git Book](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)

You can easily integrate with various code hosting platform, for instance:

-   [GitHub](https://developer.github.com/webhooks/)
-   [GitLab](https://docs.gitlab.com/ee/administration/custom_hooks.html)
-   [BitBucket](https://confluence.atlassian.com/bitbucketserver/using-repository-hooks-776639836.html)

## Usage
To fit [PEP8](https://www.python.org/dev/peps/pep-0008) Style Guide, file name uses `_` instead of `-`, and `.py` extension.

You just need to download the hook(s) you want, and put them in the **.git/hooks/** sub-directory of your repository.

When moving file to your **.git/hooks/** sub-directory, you then must rename the file accordingly, to fit what Git awaits.

### Prevent merging between some branches
For this feature, you need the **prepare_commit_msg.py** hook.

Installation:
-   copy file to the **.git/hooks/** sub-directory of your repository, and rename it to **prepare-commit-msg**
-   edit configuration at beginning of the hook to match your source/destination branches rules

## Contributing
Don't hesitate to [contribute](https://opensource.guide/how-to-contribute/) or to contact me if you want to improve the project.

You can [report issues or request features](https://gitlab.com/bertrand-benoit/pyGitHook/issues) and propose [merge requests](https://gitlab.com/bertrand-benoit/pyGitHook/merge_requests).

## Versioning
The versioning scheme we use is [SemVer](http://semver.org/).

## Authors
[Bertrand BENOIT](mailto:contact@bertrand-benoit.net)

## License
This project is under the GPLv3 License - see the [LICENSE](LICENSE) file for details.
