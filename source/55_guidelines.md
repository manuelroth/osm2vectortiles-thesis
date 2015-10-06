## Guidelines

### Releases

We use semantic versioning \footnote{\url{http://semver.org/}}.
At the end of each iteration a new release will be created. We start
at version `0.1.0`. The version number consists of a major, minor and patch version.

**Major: **Incompatible changes

**Minor: **Backwards compatible changes

**Patch: **Bugfixes

### Git


#### Commit Messages

We use the seven rules of great git commit messages\footnote{\url{http://chris.beams.io/posts/git-commit/}}.


- Separate subject from body with a blank line
- Limit the subject line to 50 characters
- Capitalize the subject line
- Do not end the subject line with a period
- Use the imperative mood in the subject line
- Wrap the body at 72 characters
- Use the body to explain what and why vs. how

#### History

##### Rewriting

Git history should be kept clean and therefore local branches should be squashed meaningfully.

##### Pulling

To avoid unnecessary merge messages one should always use the `--rebase` parameter.

### Workflow

We use the Feature Branch Workflow\footnote{\url{https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow/}}.

Every project member has a local repository with a copy of the remote repository (GitHub).
For each feature ticket in GitHub a separate branch will be created. Once a ticket
has been completed a pull request will be created and needs to be merged into the Master
branch by an other team member.

Every team member is responsible that the code is reviewed by the other team mebmer.
The reviewer will add his comments to the pull requst comment section. As soon
as all issues have been resolved and continuous integrations runs successfully
the branch will be merged into master.

### Coding Standards

### Testing

#### Unit Tests

At the moment there is no need for unit tests.

#### Integration Tests

To guarantee our solution works we will create a few completly integrated
integration tests that cover our core use cases.
