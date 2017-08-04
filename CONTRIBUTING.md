# Contributor's Guide

We welcome pull requests from Coderplex Community(our students) and seasoned JavaScript developers alike! Follow these steps to contribute:

1. Find an issue that needs assistance by searching for the [Help Wanted](https://github.com/coderplex/coderplex-website/labels/help%20wanted) tag.

2. Let us know you are working on it by posting a comment on the issue.

3. Follow the [Contribution Guidelines](#contribution-guidelines) to start working on the issue.

Remember to feel free to ask for help in our Discord server.

Working on your first Pull Request? You can learn how from this *free* series [How to Contribute to an Open Source Project on GitHub](https://egghead.io/series/how-to-contribute-to-an-open-source-project-on-github)

###### If you've found a bug that is not on the board, [follow these steps](README.md#found-a-bug).

--------------------------------------------------------------------------------

## Contribution Guidelines

- [Prerequisites](#prerequisites)
- [Forking The Project](#forking-the-project)
- [Create A Branch](#create-a-branch)
- [Setup Linting](#setup-linting)
- [Setup Prettier](#setup-prettier)
- [Setup coderplex](#setup-coderplex)
- [Make Changes](#make-changes)
- [Run The Test Suite](#run-the-test-suite)
- [Squash Your Commits](#squash-your-commits)
- [Creating A Pull Request](#creating-a-pull-request)
- [Common Steps](#common-steps)
- [How We Review and Merge Pull Requests](#how-we-review-and-merge-pull-requests)
- [How We Close Stale Issues](#how-we-close-stale-issues)
- [Next Steps](#next-steps)
- [Other resources](#other-resources)

### Prerequisites

| Prerequisite                                | Version |
| ------------------------------------------- | ------- |
| [MongoDB](http://www.mongodb.org/downloads) | `~ ^3`  |
| [Node.js](http://nodejs.org)                | `~ ^8`  |
| npm (comes with Node)                       | `~ ^5`  |

> _Updating to the latest releases is recommended_.

If Node or MongoDB is already installed in your machine, run the following commands to validate the versions:

```shell
node -v
mongo --version
```

To check your MongoDB version on Windows, you have to locate the installation directory. It is probably located at something like `C:\Program Files\MongoDB\Server\3.4\` where 3.4 is your version number.

If your versions are lower than the prerequisite versions, you should update.

Platform-specific guides to setting up a development environment:
- [How to clone and setup the coderplex website on a Windows pc] - TODO
- [How to Clone and Setup the coderplex Website on a Mac] - TODO

### Forking The Project

#### Setting Up Your System

1. Install [Git](https://git-scm.com/) or your favorite Git client.
2. (Optional) [Setup an SSH Key](https://help.github.com/articles/generating-an-ssh-key/) for GitHub.
3. Create a parent projects directory on your system. For this guide, it will be assumed that it is `/mean/`

#### Forking coderplex-website

1. Go to the top level freeCodeCamp repository: <https://github.com/coderplex/coderplex-website>
2. Click the "Fork" Button in the upper right hand corner of the interface ([More Details Here](https://help.github.com/articles/fork-a-repo/))
3. After the repository has been forked, you will be taken to your copy of the FCC repo at `yourUsername/coderplex-website`

#### Cloning Your Fork

1. Open a Terminal / Command Line / Bash Shell in your projects directory (_i.e.: `/yourprojectdirectory/`_)
2. Clone your fork of freeCodeCamp

```shell
$ git clone https://github.com/yourUsername/coderplex-website.git
```

##### (make sure to replace `yourUsername` with your GitHub Username)

This will download the entire FCC repo to your projects directory.

#### Setup Your Upstream

1. Change directory to the new coderplex-website directory (`cd coderplex-website`)
2. Add a remote to the official FCC repo:

```shell
$ git remote add upstream https://github.com/coderplex/coderplex-website.git
```

Congratulations, you now have a local copy of the coderplex-website repo!

#### Maintaining Your Fork

Now that you have a copy of your fork, there is work you will need to do to keep it current.

##### **Rebasing from Upstream**

Do this prior to every time you create a branch for a PR:

1. Make sure you are on the `staging` branch

  > ```shell
  > $ git status
  > On branch staging
  > Your branch is up-to-date with 'origin/staging'.
  > ```

  > If your aren't on `staging`, resolve outstanding files / commits and checkout the `staging` branch

  > ```shell
  > $ git checkout staging
  > ```

2. Do a pull with rebase against `upstream`

  > ```shell
  > $ git pull --rebase upstream staging
  > ```

  > This will pull down all of the changes to the official staging branch, without making an additional commit in your local repo.

3. (_Optional_) Force push your updated staging branch to your GitHub fork

  > ```shell
  > $ git push origin staging --force
  > ```

  > This will overwrite the staging branch of your fork.

### Create A Branch

Before you start working, you will need to create a separate branch specific to the issue / feature you're working on. You will push your work to this branch.

#### Naming Your Branch

Name the branch something like `fix/xxx` or `feature/xxx` where `xxx` is a short description of the changes or feature you are attempting to add. For example `fix/email-login` would be a branch where you fix something specific to email login.

#### Adding Your Branch

To create a branch on your local machine (and switch to this branch):

```shell
$ git checkout -b [name_of_your_new_branch]
```

and to push to GitHub:

```shell
$ git push origin [name_of_your_new_branch]
```

##### If you need more help with branching, take a look at _[this](https://github.com/Kunena/Kunena-Forum/wiki/Create-a-new-branch-with-git-and-manage-branches)_.

### Setup Linting

You should have [XO plugin running in your editor](https://github.com/sindresorhus/xo#editor-plugins), and it will highlight anything doesn't conform to [XO Recommended JavaScript Style Guide](https://github.com/sindresorhus/xo)
> Please do not ignore any linting errors, as they are meant to **help** you and to ensure a clean and simple code base.

### Setup Prettier

You should have [Prettier plugin running in your editor](https://github.com/prettier/prettier#editor-integration), and it enforces a consistent code **style**. You can read more about Prettier [here](https://github.com/prettier/prettier)

### Setup coderplex-website
Once you have coderplex-webiste cloned, before you start the application, you first need to install all of the dependencies:

```bash
# Install NPM dependencies
npm install
```

Then you need to setup coderplex-backend server follow instructions here(TODO)



Now navigate to your browser and open
<http://localhost:3000>. If the app loads,
congratulations – you're all set. Otherwise, let us know by asking in the [Contributors chat room](https://gitter.im/FreeCodeCamp/Contributors) on Gitter. There also might be an error in the console of your browser or in Bash / Terminal / Command Line that will help identify the problem. If the app launches but you are encountering errors with the UI itself, for example if fonts are not being loaded or if the code editor is not displaying properly, you may try the following:

### Make Changes
This bit is up to you!

### Run The Test Suite
When you're ready to share your code, run the test suite:

```shell
$ npm test
```

and ensure all tests pass.

### Squash Your Commits
When you make a pull request, all of your changes need to be in one commit.

If you have made more than one commit, then you will need to _squash_ your commits.

To do this, see [Squashing Your Commits](http://forum.freecodecamp.com/t/how-to-squash-multiple-commits-into-one-with-git/13231).

### Creating A Pull Request

#### What is a Pull Request?

A pull request (PR) is a method of submitting proposed changes to the freeCodeCamp
Repo (or any Repo, for that matter). You will make changes to copies of the
files which make up freeCodeCamp in a personal fork, then apply to have them
accepted by freeCodeCamp proper.

#### Important: ALWAYS EDIT ON A BRANCH

Take away only one thing from this document: Never, **EVER**
make edits to the `staging` branch. ALWAYS make a new branch BEFORE you edit
files. This is critical, because if your PR is not accepted, your copy of
staging will be forever sullied and the only way to fix it is to delete your
fork and re-fork.

#### Methods

There are two methods of creating a pull request for coderplex-website:

-   Editing files on a local clone (recommended)
-   Editing files via the GitHub Interface

##### Method 1: Editing via your Local Fork _(Recommended)_

This is the recommended method. Read about [How to Setup and Maintain a Local
Instance of coderplex-website](#maintaining-your-fork).

1.  Perform the maintenance step of rebasing `staging`.
2.  Ensure you are on the `staging` branch using `git status`:

```bash
$ git status
On branch staging
Your branch is up-to-date with 'origin/staging'.

nothing to commit, working directory clean
```

1.  If you are not on staging or your working directory is not clean, resolve
    any outstanding files/commits and checkout staging `git checkout staging`

2.  Create a branch off of `staging` with git: `git checkout -B
    branch/name-here` **Note:** Branch naming is important. Use a name like
    `fix/short-fix-description` or `feature/short-feature-description`. Review
     the [Contribution Guidelines](#contribution-guidelines) for more detail.

3.  Edit your file(s) locally with the editor of your choice

4.  Check your `git status` to see unstaged files.

5.  Add your edited files: `git add path/to/filename.ext` You can also do: `git
    add .` to add all unstaged files. Take care, though, because you can
    accidentally add files you don't want added. Review your `git status` first.

6.  Commit your edits (follow any one of the below methods):

    a. Using the inbuilt script (_recommended_):
       - We have a [tool](https://commitizen.github.io/cz-cli/) that helps you to make standard commit messages. Simply execute `npm run commit` after you have added the necessary files as mentioned in the step earlier.

    b. Using Commitizen CLI:
       - If you are already using [commitizen](http://commitizen.github.io/cz-cli/), simply doing a `git cz` works as expected too!

7.  Squash your commits, if there are more than one.

8.  If you would want to add/remove changes to previous commit simply add the files as in Step 5 earlier,
    and use `git commit --amend` or `git commit --amend --no-edit` (for keeping the same commit message).

9.  Push your commits to your GitHub Fork: `git push -u origin branch/name-here`

10.  Go to [Common Steps](#common-steps)

##### Method 2: Editing via the GitHub Interface

Note: Editing via the GitHub Interface is not recommended, since it is not
possible to update your fork via GitHub's interface without deleting and
recreating your fork.

### Common Steps

1.  Once the edits have been committed, you will be prompted to create a pull
    request on your fork's GitHub Page.

2.  By default, all pull requests should be against the FCC main repo, `staging`
    branch.

3.  Submit a [pull
    request](http://forum.freecodecamp.com/t/how-to-contribute-via-a-pull-request/19368)
    from your branch to coderplex-website `staging` branch.

4.  The title (also called the subject) of your PR should be descriptive of your
    changes and succinctly indicates what is being fixed.

    -   **Do not add the issue number in the PR title or commit message.**

    -   Examples: `Add Test Cases to Bonfire Drop It` `Correct typo in Waypoint
        Size Your Images`

5.  In the body of your PR include a more detailed summary of the changes you
    made and why.

    -   If the PR is meant to fix an existing bug/issue then, at the end of
        your PR's description, append the keyword `closes` and #xxxx (where xxxx
        is the issue number). Example: `closes #1337`. This tells GitHub to
        close the existing issue, if the PR is merged.

6.  Indicate if you have tested on a local copy of the site or not.


### How We Close Stale Issues

We will close any issues or pull requests that have been inactive for more than 15 days, except those that match the following criteria:
- bugs that are confirmed
- pull requests that are waiting on other pull requests to be merged
- features that are a part of a GitHub project

### Next Steps

#### If your PR is accepted

Once your PR is accepted, you may delete the branch you created to submit it.
This keeps your working fork clean.

You can do this with a press of a button on the GitHub PR interface. You can
delete the local copy of the branch with: `git branch -D branch/to-delete-name`

#### If your PR is rejected

Don't despair! You should receive solid feedback from the Issue Moderators as to
why it was rejected and what changes are needed.

Many Pull Requests, especially first Pull Requests, require correction or
updating. If you have used the GitHub interface to create your PR, you will need
to close your PR, create a new branch, and re-submit.

If you have a local copy of the repo, you can make the requested changes and
amend your commit with: `git commit --amend` This will update your existing
commit. When you push it to your fork you will need to do a force push to
overwrite your old commit: `git push --force`

Be sure to post in the PR conversation that you have made the requested changes.

### Other resources

-   [Searching for Your Issue on
    GitHub](http://forum.freecodecamp.com/t/searching-for-existing-issues/19139)

-   [Creating a New GitHub
    Issue](http://forum.freecodecamp.com/t/creating-a-new-github-issue/18392)

-   [Select Issues for Contributing Using
    Labels] - TODO

-   [How to clone the coderplex-website on a Windows
    pc] - TODO

-   [How to log in to your local FCC site - using
    GitHub] - TODO

-   [Writing great git commit
    messages](http://forum.freecodecamp.com/t/writing-good-git-commit-messages/13210)

-   [Contributor Chat Support - For the Coderplex Repositories, and running a local
    instance] - Discord Server Link
