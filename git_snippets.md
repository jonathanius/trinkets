# Git Snippets
[Git Book](https://git-scm.com/book/en/v2/) <br>
[Interactive Cheatsheet](https://ndpsoftware.com/git-cheatsheet.html) <br>
[Comparison of Workflows](https://www.atlassian.com/git/tutorials/comparing-workflows) <br>
[Merging vs Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

#### List all branches from `<origin>`
> git ls-remote `<origin>`

> git remote show `<origin>`

#### Create remote `<branch>` on `<origin>` from local and set it to be upstream.

> git push -u `<origin>` `<branch>`

#### List remote branches
> git branch -r

> git branch --remote

#### Display the log of the current branch
Full log information
> git log

Summarised log information
> git shortlog

> git log --oneline

Graph representation and summarised version of the log.
> git log --graph --oneline

#### Discard working changes
> git reset --hard

#### Checkout a prior `<commit id>` to update the working directory to a prior state. Note that pulling from upstream may fast-forward back to the current working state. Therefore, it is a good idea to create a `<new_branch>` with `<commit id>` as its head.
> git checkout `<commit id>` <br>
> git branch `<new_branch>` <br>
> git checkout `<new_branch>`

#### Revert to a previous `<commit id>`. This will create a new commit and, so, may result in merge conflicts.
> git revert `<commit id>`

#### Delete `<branch>`
Force delete uncommitted changes
> git branch -D `<branch>`

#### Display commit graph for all branches
> git log --graph --oneline --all

##### Display the branch currently checked out
> git branch --show-current

#### The commit history comments of `<filename>`
> git shortlog -p `<filename>`

#### The most recent commit for `<filename>`
> git log -n 1 -p `<filename>`

> git log --pretty=format:"%ai%n%an%n%H" -n 1 -p `<filename>`

> git log --pretty=format:"%ai%n%an%n%H" -n 1 `<remote>`/`<branch>`

Display the patch information
> git log --format=medium -n 1 -p `<filename>`

Display the statistics
> git log --format=medium -n 1 --stat `<filename>`

#### Additional Information about `<commit id>`
Display local branches that contain `<commit id>`.
> git branch --contains `<commit id>`

Display remote branches that contain `<commit id>`.
> git branch --remote --contains `<commit id>`

#### Search files in the working directory
List file names and line numbers that match `<serch pattern>`
> git grep -n `<search pattern>`

#### Search the log
Locate `<search string>` in the last commit to the working branch
> git log -n 1 -S `<search string>`

Locate `<regex string>` in the last commit to `<filename>`
> git log -n 1 -G `<regex string>` --stat `<filename>`
