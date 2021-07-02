# SourceTree, Atom integration

Make sure that the latest GIT is installed (https://github.com/git-for-windows/build-extra/blob/main/ReleaseNotes.md#changes-since-git-for-windows-v2280-july-28th-2020)

Ensure that SourceTree isn't using the imbedded GIT; this is a setting on the GIT tab in options.

Then it should allow authentication through Windows

# Creating a new repo from a subset of an old one

This aims to preserve only the history of the required files.  It uses the https://github.com/newren/git-filter-repo tool; this is a third party python tool recomended by GIT for this type of history manipulation.  

The tool can be installed using PIP.  Once installed it follows the same GIT commandline structure

- Clone the existing repo into a directory:
```bash
git clone --branch <branch> --origin origin --progress -v <URL to Repo>
```
- Remove the origin to avoid accidently pushing it back
```bash
git remote rm origin
```
- Remove the files and history for everything except the files and directories specified.  Note as the origin was removed in the previous step the ```--force``` option is required
```bash
git filter-repo --path <path 1> --path <path 2> etc --force
```
