# My App

## Contribution Guide

### Issues

The issues are named after the feature or bug to be implemented. For example, "Add missing ID when fetching buses". It is important to assign a verb to the issues so everyone knows what to do.
Last, we add a bracket with a value to the issue title. This value tells how hard the issue to be worked on is.

In the case of bugs, the issue should be described as precisely as possible and, if necessary, even provided with a picture or video. This will make it easier to edit later.

If an issue is to be worked on, enter yourself as the _assignee_.

**Important**: You should only enter yourself as an _assignee_ if you also worked on the issue.

### Board

We use the Projects Board from GitHub as a board. This board is automated and requires little manual work.

### Labels

We use this [Guide][LABELS_GUIDE_URL] for the labels.

### GitFlow (Branching)

#### Key Benefits

**Parallel Development**

One of the great things about GitFlow is that it makes parallel development very easy, by isolating new development from finished work. New development (such as features and non-emergency bug fixes) is done in feature branches, and is only merged back into main body of code when the developer(s) is happy that the code is ready for release.

Although interruptions are a BadThing(tm), if you are asked to switch from one task to another, all you need to do is commit your changes and then create a new feature branch for your new task. When that task is done, just checkout your original feature branch and you can continue where you left off.

**Collaboration**

Feature branches also make it easier for two or more developers to collaborate on the same feature, because each feature branch is a sandbox where the only changes are the changes necessary to get the new feature working. That makes it very easy to see and follow what each collaborator is doing.

**Release Staging Area**

As new development is completed, it gets merged back into the develop branch, which is a staging area for all completed features that haven’t yet been released. So when the next release is branched off of develop, it will automatically contain all of the new stuff that has been finished.

**Support For Emergency Fixes**

GitFlow supports hotfix branches - branches made from a tagged release. You can use these to make an emergency change, safe in the knowledge that the hotfix will only contain your emergency fix. There’s no risk that you’ll accidentally merge in new development at the same time.


#### How It Works

New development (new features, non-emergency bug fixes) are built in feature branches.
Feature branches are branched off of the develop branch, and finished features and fixes are merged back into the develop branch when they’re ready for release.
When it is time to make a release, a release branch is created off of develop.

The code in the release branch is deployed onto a suitable test environment, tested, and any problems are fixed directly in the release branch. This deploy -> test -> fix -> redeploy -> retest cycle continues until you’re happy that the release is good enough to release to customers.

When the release is finished, the release branch is merged into master and into develop too, to make sure that any changes made in the release branch aren’t accidentally lost by new development.

The master branch tracks released code only. The only commits to master are merges from release branches and hotfix branches.

Hotfix branches are used to create emergency fixes.

They are branched directly from a tagged release in the master branch, and when finished are merged back into both master and develop to make sure that the hotfix isn’t accidentally lost when the next regular release occurs.

All merges onto the master branch should be tagged with the app version.

**Important**: No commits should be done on the master and developer branch, only on the feature branch!

The branch should be similar to the issue to be implemented, e.g. the issue is called _#1 Branching into the Readme_, then the branch should be called _feature/#1-readme-branching_.
We write the ID (#1) of the issue to be processed in the name of the branch.

For releases and HotFixes the branch is named according to the new version.

![GITFLOW_VIRTUALIZATION_IMAGE]

### Commits

The commits are given a meaningful name and description.
The description should say why this change was made and **not** how. The how can be read in the code.

If you are done with editing the issue, you have to add a keyword and the ID of the issue to close the issue.

Here is the [Guide][LINKING_ISSUE_TO_PULLREQUEST] from GitHub.

### Folder and file structure

We use this [Guide][FOLDER_AND_FILE_STRUCTURE_GUIDE_URL] for the structure and naming of files and folders.

### Best Practices

We use this [Guide][BEST_PRACTICES_GUIDE_URL] for the structure of classes and functions.

### Definition of Done

- [ ] New feature branch created
- [ ] Issue edited
- [ ] Documentation created for new code
- [ ] Tests for new code (issue) created
- [ ] All tests successful
- [ ] Pull Request created
- [ ] Pull Request Review successful

[LABELS_GUIDE_URL]: https://github.com/Hebrasco/project-fundamentals/tree/master/guides/labels/readme.md
[GITFLOW_GUIDE_URL]: https://github.com/Hebrasco/project-fundamentals/blob/master/guides/gitflow/readme.md
[LINKING_ISSUE_TO_PULLREQUEST]: https://docs.github.com/en/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue
[FOLDER_AND_FILE_STRUCTURE_GUIDE_URL]: none
[BEST_PRACTICES_GUIDE_URL]: none
