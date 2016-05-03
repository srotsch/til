## Render a simple list of all changes committed to a Git repository since the last tag

```shell
git --no-pager log --date=short --no-merges --pretty="%<(12)%ad%<(9)%h%s" `git describe --abbrev=0 --tags`..HEAD
```

### Explaining the options

**--no-pager** Do not pipe Git output into a pager.

**--date=short** Show only the date, but not the time, in `YYYY-MM-DD` format.

**--no-merges** Do not print commits with more than one parent.

**--pretty="%<(12)%ad%<(9)%h%s"** Print the author date (`%ad`), abbreviated commit hash (`%h`) and subject (`%s`), nicely aligned (`%<(12)` and `%<(9)`)

**\`git describe --abbrev=0 --tags\`..HEAD** Show only commits happened since the last tag (`git describe --abbrev=0 --tags`)

### Example output from the TYPO3 [crawler](https://github.com/AOEpeople/crawler) extension

```
2016-03-24  900f53a  [BUGFIX] Fix broken displayCond
2016-03-24  2957404  Revert "[TASK] Re-enable Workspace after Core Issue #70052 fixed"
2016-03-23  8a15cb6  [TASK] Missing "hide"/"disable" field in the configuration record form
2016-03-10  995b96f  [TASK] config.absRefPrefix not respected by tx_crawler_lib::getFrontendBasePath()
2016-03-18  8046f87  [TASK] Set version to 5.0.5-dev
```
