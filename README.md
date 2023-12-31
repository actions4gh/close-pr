# Close GitHub Pull Request

❌ Close a GitHub Pull Request as unmerged

<p align=center>
  <img src="https://i.imgur.com/C56XhjE.png">
</p>

👨‍💻 Use the [GitHub CLI] \
😱 You don't even need a GitHub Action to do it!

## Usage

![GitHub Actions](https://img.shields.io/static/v1?style=for-the-badge&message=GitHub+Actions&color=2088FF&logo=GitHub+Actions&logoColor=FFFFFF&label=)
![GitHub](https://img.shields.io/static/v1?style=for-the-badge&message=GitHub&color=181717&logo=GitHub&logoColor=FFFFFF&label=)

**🚀 Here's what you're after:**

```yml
name: Close with Lorem Ipsum comment
on:
  pull_request:
    types: labeled
jobs:
  test-action:
    if: github.event.label.name == 'lorem ipsum'
    permissions:
      pull-requests: write
    runs-on: ubuntu-latest
    steps:
      - run: gh pr close "$NUMBER" --comment "$COMMENT"
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          GH_REPO: ${{ github.repository }}
          NUMBER: ${{ github.event.number }}
          COMMENT: >
            Lorem ipsum is placeholder text commonly used in the graphic, print,
            and publishing industries for previewing layouts and visual mockups.
```

💡 The GitHub CLI is always provided on all GitHub runners. To install it on
custom runners check out [actions4gh/setup-gh].

```sh
gh pr close {<number> | <url> | <branch>} [flags]
```

**`gh issue comment` options:** <sup>(excerpt)</sup>

- **`-c`, `--comment <string>`:** Leave a closing comment

- **`-d`, `--delete-branch`:** Delete the local and remote branch after close

- **`-R`, `--repo <[HOST/]OWNER/REPO>`:** Select another repository using the
  `[HOST/]OWNER/REPO` format

[📚 gh pr close | GitHub CLI](https://cli.github.com/manual/gh_pr_close)

[github cli]: https://cli.github.com/
[actions4gh/setup-gh]: https://github.com/actions4gh/setup-gh
