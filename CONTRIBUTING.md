# Contributing to BarnBridge

TODO: Add TLDR about BBIPs

## Intro

(Clubhouse Projects)[https://app.clubhouse.io/barnbridge/projects] shows all the components that are for the Product.

All the commits go into one branch for each of the repositories, **the master branch**, through Pull Requests. The builds and the deployments for the environments above are done from there.

A Pull Request contains at least 1 or more Clubhouse stories that have been completed from a development point of view.

There are 3 types of stories in Clubhouse: Features, Bugs, and Chores. Features are enhancements to the product. Bugs are issues that disrupt the usability of the product. Chores are any work that has to be completed but does not quite fall within the aforementioned types. 

## Workflow

### Unscheduled
- Collection of stories in the backlog.

### Ready for Development
- Collection of stories that are ready to be developed.
- Stories that are part of the current Sprint.

### In Development
- Collection of stories that are in development.
- Stories that have a Github branch associated with.

### Ready for Review
- Collection of stories that are in development.
- Stories that have a Github PR associated with and are ready to be reviewed by the other devs.

### Deploy on Staging
- Collection of stories that are done and ready to be reviewed by the team.
- Stories that are deployed in the development environment.
- Stories that are deployed in the staging environment at the end of the sprint.

### Completed
- Collection of stories that are done and represent the final scope of the release.
- Stories that are captured in a Platform release, release that ends in the production environment every 4 weeks.

## Environments

### Development 
- URL: TODO
- Follows the changes in the Master branch on Github.
- For every PR that gets merged into the Master branch, build & deploy automatically for the latest tag.

### Staging
- URL: TODO
- Follows the changes in the Master branch on Github.
- For every PR that gets merged into the Master branch, create a build for the latest tag.
- Deploy manually at the end of the Sprint.

### Production
- URL: TODO
- The same pattern as for Staging.
- Deploy manually every 4 weeks.

## How to Start Working on a Story

1. Choose your story -- `story_id`
2. Create a new branch locally: 
   1. `git checkout master && git pull`
   2. `git checkout -b [story_type]/[owner_username]/[chstory_id]`
3 Push the local branch to remote => story state, “In Development”
   1. `git push -u origin [story_type]/[owner_username]/[chstory_id]`
4. Make commits in your branch 🚀
   1. Optionally, you might want to include other stories in your branch.
   2. You can do this by mentioning [chstory_id] in your commit.
5. Open a Pull Request.
   1. Ask for Reviews from your peer developers.
6. Merge Pull Request 🥂
   1. ⚠️ It is the best practice to always rebase your branch with the Pull Request base branch before you merge it in.

Read more - [Clubhouse docs](https://help.clubhouse.io/hc/en-us/articles/207540323-Using-the-Clubhouse-GitHub-Integration-with-Branches-and-Pull-Requests).

### Automation Between Github and Clubhouse
- Branch gets pushed to remote =>  the story(ies) state updates to “In Development”.
- PR with branch is opened to master branch => the story(ies) state updates to “Ready for Review”.
- PR with branch is merged to master branch => the story(ies) state updates to “Ready for Deploy”.

### Git Best Practices

Git commit: https://chris.beams.io/posts/git-commit/
- Keep a Subject and a Message.
- The Subject is no longer than 50 characters.
- Use imperative language: “If applied, this commit will Your subject line here”
  - Example: “If applied, this commit will Update getting started documentation”
  - => Therefore the commit will be: **Update getting started documentation**

Merge vs Rebase: https://link.medium.com/3u4qBdz0t8 
- It is best practice to git rebase over git merge to keep a clean git history.
- Reason is that you can backtrack an issue faster this way.

