# Pull Requests

Pull requests are a feature that makes it easier for developers to collaborate. They provide a user-friendly web interface for discussing proposed changes before integrating them into the official project.

![Pull Request Visualizer](https://cdn.discordapp.com/attachments/786053009964269591/1135689245856641107/02.svg)

As our team uses GitHub, we'll expect you to work on features and open pull requests to merge those features into the main repository. This allows us to review your code, and make sure that it works before merging it into the main repository.

## Why Pull Requests?

Let's refresh ourselves on what it means to pull changes from a source. 

When we make changes and/or produce new code (features), they will typically comprise of a series of commits on a unique branch.
The thing is, these changes are all isolated on their own branches, so in order to bring the changes together we *merge* them together.

However, there typically needs to be some sort of process to ensure that all changes are valid and work as intended. This is where pull requests come in.

In their simplest form, pull requests are a mechanism for a developer to notify team members that they have completed a feature. Once their feature branch is ready, the developer files a pull request via their GitHub account. This lets everybody involved know that they need to review the code and **merge it into the the desired branch**.

But, the pull request is more than just a notification - it’s a dedicated forum for discussing the proposed feature. If there are any problems with the changes, teammates can post feedback in the pull request and even tweak the feature by pushing follow-up commits. All of this activity is tracked directly inside each pull request.

### Anatomy of Pull Requests

When you file a pull request, all you’re doing is requesting that another developer (e.g., the project maintainer) pulls your branch to merge it with the target branch.

This means that you need to provide 4 pieces of information to file a pull request: 

- The Source Repository
- The Source Branch
- The Destination Repository
- The Destination Branch.

!!! note
    In most cases, the source repository and destination repository will be the same. It will only be different if you are following a [forking workflow](./git-dev-patterns.md#forking-workflow-optional).

### Code Review

Code review and collaboration are at the core of pull requests. Depending on your role, you may be an author, a reviewer, or both on one or more pull requests.

#### Authors Guidelines
Code review is a conversation. As an author, you should be prepared to answer questions and explain your code. You should also be open to receiving feedback and criticism. Remember, the goal is to improve the code and the project as a whole.

!!! tip
    When you create a pull request, you'll be asked to provide a title and description. The title should be short and descriptive, and the description (can be optional) should provide context for the changes you've made.

    Things they should not be is "N/A", "Merge changes", or "Fixes bug".

#### Reviewers Guidelines
During your code review, you'll comment with feedback, suggestions, and ideas. You may take time to consider if there are any obvious logic errors, all cases are fully implemented, and the code conforms to existing style guidelines.

After your review, if the pull request is ready to be merged (or if you trust the author to resolve your tasks before merging), click the Approve button in the top right. A green checkmark appears next to your name in the Reviewers field after you approve a pull request.

## Pull Requests in Action

### Creating a Pull Request

Github offers their own [documentation](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) on creating pull requests. We'll go over the basics here.

To create a pull request, you'll need to [create a branch](./git-in-action-multiple.md#git-checkout), and [push](./git-in-action-multiple.md#git-push) that branch to GitHub.

Once you've pushed your branch to GitHub, you can create a pull request. To do this, go to the repository on GitHub, and click the `Pull Requests` tab. 

![Pull Request Tab](https://docs.github.com/assets/cb-52309/mw-1440/images/help/repository/repo-tabs-pull-requests.webp)

Then, click the `New Pull Request` button.

![New Pull Request Button](https://cdn.discordapp.com/attachments/786053009964269591/1135686451162517614/image.png)

???+ tip
    GitHub may detect that you've pushed changes to a branch, and prompt you to create a pull request, directly from the repository page.

    ![Pull Request Prompt](https://docs.github.com/assets/cb-34106/mw-1440/images/help/pull_requests/pull-request-compare-pull-request.webp)

Next, GitHub will prompt you to select a base branch and a compare branch. 

- The base branch is the branch that you want to merge your changes into. 
- The compare branch is the branch that you want to merge into the base branch. 
 
!!!tip
    Typically, the compare branch is the branch that you created.

![Selecting the base and compare branches](https://docs.github.com/assets/cb-87213/mw-1440/images/help/pull_requests/pull-request-review-edit-branch.webp)

Once you've selected the base and compare branches, you can click the "Create Pull Request" button. You'll be prompted to enter a title and description for your pull request. Once you've done this, you can click the "Create Pull Request" button again.

Add the programming lead as a reviewer, and click the "Create Pull Request" button again. This will create the pull request.

## Code Review

### Receiving Code Review

Once you've created a pull request, you can ask other members of the team to review your code and provide feedback. On our team, **ask the programming lead to review your code**. You can include other members at your own discretion.

To request a review from a suggested person under Reviewers, next to their username, click Request.

![Request Review Pane](https://docs.github.com/assets/cb-18313/mw-1440/images/help/pull_requests/request-suggested-review.webp)

Optionally, to request a review from someone other than a suggested person, click Reviewers.

If you know the name of the person or team you'd like a review from, type the username of the person or the name you're asking to review your changes. Click their username to request a review.

![Re Request Review Pane](https://docs.github.com/assets/cb-28785/mw-1440/images/help/pull_requests/request-re-review.webp)

### Reviewing Code

Pull up the pull request that you want to review. You can do this by clicking on the pull request in the pull request tab.

Next, head over to :octicons-file-diff-24: **Files Changed**

![Files Changed](https://docs.github.com/assets/cb-23571/mw-1440/images/help/pull_requests/pull-request-tabs-changed-files.webp)

You can change the format of the diff view in this tab by clicking :octicons-gear-24: and choosing the unified or split view. The choice you make will apply when you view the diff for other pull requests.

![Diff View](https://docs.github.com/assets/cb-186190/mw-1440/images/help/pull_requests/diff-settings-menu.webp)

#### Adding Comments

Hover over the line of code where you'd like to add a comment, and click the blue comment icon. To add a comment on multiple lines, click and drag to select the range of lines, then click the blue comment icon.

![Add Comment](https://docs.github.com/assets/cb-44254/mw-1440/images/help/commits/hover-comment-icon.webp)

You can also directly suggest changes with the :octicons-file-diff-16: button

![Suggest Change](https://docs.github.com/assets/cb-26290/mw-1440/images/help/pull_requests/suggestion-block.webp)

#### Approving Changes

When you're done commenting, click Start a review. If you have already started a review, you can click Add review comment.

![Approving Changes](https://docs.github.com/assets/cb-115068/mw-1440/images/help/pull_requests/review-changes-button.webp)

- Select Comment to leave general feedback without explicitly approving the changes or requesting additional changes.
- Select Approve to submit your feedback and approve merging the changes proposed in the pull request.
- Select Request changes to submit feedback that must be addressed before the pull request can be merged.

!!! tip
    Before you submit your review, your line comments are pending and only visible to you. You can edit pending comments anytime before you submit your review. To cancel a pending review, including all of its pending comments, click Review changes above the changed code, then click Cancel review.
