# Git Snippets
[Git Book](https://git-scm.com/book/en/v2/) <br>
[Interactive Cheatsheet](https://ndpsoftware.com/git-cheatsheet.html) <br>
[Comparison of Workflows](https://www.atlassian.com/git/tutorials/comparing-workflows) <br>
[Merging vs Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)

#### Run the garbage collector to remove loose objects and reduce the size of the local DB.
> git gc

#### Create remote `<branch>` on `<origin>` from local and set it to be upstream.
> git push -u `<origin>` `<branch>`

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

#### Checkout a prior `<commit_id>` to update the working directory to a prior state. Note that pulling from upstream may fast-forward back to the current working state. Therefore, it may be convenient to create a `<new_branch>` with `commit_id` as its head.
> git checkout `<commit_id>` <br>
> git branch `<new_branch>` <br>
> git checkout `<new_branch>`

#### Revert to a previous `<commit_id>`. This will create a new commit and, so, may result in merge conflicts.
> git revert `<commit_id>`

#### Delete `<branch>`
Force delete uncommitted changes
> git branch -D `<branch>`

#### Display commit graph for all branches
> git log --graph --oneline --all

#### Compare files changed between `<upstream_branch>` and `<working_branch>`
> git diff --name-only `<working_branch>`..`<upstream_branch>`

> git checkout `<working_branch>` <br>
> git diff --name-only `<upstream_branch>`

#### Generate a diff for `<file_name>` between `<old_commit>` and `<new_commit>`
> git diff `<file_name>` `<old_commit>` `<new_commit>`

Redirect the diff above to `<diff_file.txt>` using diff command option.
> git diff --output `<diff_file.txt>` `<file_name>` `<old_commit>` `<new_commit>`

Redirect the diff above to `<diff_file.txt>` by redirecting standard output.
> git diff `<file_name>` `<old_commit>` `<new_commit>` >> `<diff_file.txt>`

##### Display the branch currently checked out
> git show-branch --current

#### The commit history comments of `<file_name>`
> git shortlog -p `<file_name>`

#### The most recent commit for `<file_name>`
> git log -n 1 -p `<file_name>`

> git log --pretty=format:"%ai%n%an%n%H" -n 1 -p `<file_name>`

Display commit information from `<branch>` on `<remote>`. Fetch from remote first to ensure that origin is up to date.
> git fecth `<remote>`
> git log --pretty=format:"%ai%n%an%n%H" -n 1 `<remote>`/`<branch>`

Display patch information for `<file_name>`
> git log --format=medium -n 1 -p `<file_name>`

Display log statistics
> git log --format=medium -n 1 --stat `<file_name>`

#### Additional Information about `<commit_id>`
Display local branches that contain `<commit_id>`.
> git branch --contains `<commit_id>`

#### Search files in the working directory
List file names and line numbers that match `<serch_pattern>`
> git grep -n `<search_pattern>`

#### Search the log
Locate `<search_string>` in the last commit to the working branch
> git log -n 1 -S `<search_string>`

#### Locate `<regex_string>` in the last commit to `<file_name>`
> git log -n 1 -G `<regex_string>` --stat `<file_name>`

### Remote Repositories
[Git Documentation](https://docs.github.com/en/get-started/git-basics/managing-remote-repositories)
#### List remote branches
> git branch -r

> git branch --remote

#### List remote URLs
> git remote -v

#### Change remote `name`'s URL (HTTPS) to `host.domain`, `owner`, and `repository`
> git remote set-url `name` https://`host.domain`/`owner`/`repository`.git

#### List all branches from `<origin>`
> git ls-remote `<origin>`

> git remote show `<origin>`

#### Prune remote branches
> git fetch --prune

#### Display remote branches that contain `<commit_id>`.
> git branch --remote --contains `<commit_id>`
