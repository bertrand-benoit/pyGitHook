# pyGitHook

[![Codacy Badge](https://api.codacy.com/project/badge/Grade/21ad636cfd8f4b32b7e24a5ad72486cf)](https://app.codacy.com/app/bertrand-benoit/pyGitHook?utm_source=github.com&utm_medium=referral&utm_content=bertrand-benoit/pyGitHook&utm_campaign=Badge_Grade_Dashboard)

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
To fit [PEP8](https://www.python.org/dev/peps/pep-0008) Style Guide, file name uses `_` instead of `-`, and `.py` extension.

You just need to download the hook(s) you want, and put them in the **.git/hooks/** sub-directory of your repository.

When moving file to your **.git/hooks/** sub-directory, you then must rename the file accordingly, to fit what Git awaits.

### Prevent merging between some branches
For this feature, you need the **prepare_commit_msg.py** hook.

Installation:
 - copy file to the **.git/hooks/** sub-directory of your repository, and rename it to **prepare-commit-msg**
 - edit configuration at beginning of the hook to match your source/destination branches rules

## Contributing
Don't hesitate to [contribute](https://opensource.guide/how-to-contribute/) or to contact me if you want to improve the project.

You can [report issues or request features](https://github.com/bertrand-benoit/pyGitHook/issues) and propose [pull requests](https://github.com/bertrand-benoit/pyGitHook/pulls).

## Versioning
The versioning scheme we use is [SemVer](http://semver.org/).

## Authors
[Bertrand BENOIT](mailto:contact@bertrand-benoit.net)

## License
This project is under the GPLv3 License - see the [LICENSE](LICENSE) file for details.
