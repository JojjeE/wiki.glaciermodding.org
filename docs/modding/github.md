---
description: A crash course in contributing to Hitman mods hosted on GitHub.
---

# Contributing to GitHub Projects

By using the official [Simple Mod Framework mod template](https://github.com/atampy25/smf-mod) on GitHub, mod creators can automatically handle changelogs and generating mod ZIP archives for distribution.

It also allows for greater collaboration such as for our [Unofficial Community Patch](https://github.com/glacier-modding/H3-Unofficial-Community-Patch) project.

In this guide, we will teach you how to contribute specifically to the Unofficial Community Patch project, but the principles apply to all Hitman mods hosted via GitHub. The etiquette for making issues and pull requests will differ from project to project.

## Requirements

- A GitHub account. [Register one here](https://github.com/signup).
- GitHub Desktop. [Download it here](https://desktop.github.com/download/).
- The latest LTS Node.js release with npm. [Download it here](https://nodejs.org/en/download), click *Windows Installer (.msi)* or otherwise install it for your OS. When you install Node.js make sure all features, especially **Add to PATH** are installed.

### Prepare our fork

The basic principles of GitHub and Git is to make our own version of a repository to work against. This is called *forking* and we are creating a *fork*. Later when we've developed and made our commits, we make a *pull request* toward the original source, the *upstream repository*, asking them to accept the changes in our *fork*. Generally you will only need to make a fork once.

Go to the [Unofficial Community Patch repository](https://github.com/glacier-modding/H3-Unofficial-Community-Patch). Click the **Fork** button.

![Clicking the fork button.](/img/github/forking.png)

You do not need to make any changes. Simply click **Create fork**. Wait while it works.

![Forking a repository.](/img/github/forking_confirm.png)

When your fork has opened in a new tab, open your file browser and navigate to your **Simple Mod Framework** folder. Enter the **Mods** folder, and create a new folder called **GlacierOrganisation.CommunityPatches**. If you already have the Unofficial Community Patch mod the folder already exists, you can enter the folder, and delete all files inside until it is completely empty.

### GitHub Desktop

Register your GitHub account first.

When running the installer, click **Sign in to GitHub.com** and authorize GitHub Desktop.

Configure Git. The easiest is to let it use your GitHub account name and email address. Click **Finish**.

In the welcome screen, select your UCP fork in the list of your repositories. Click **Clone** at the bottom of the screen.

![Getting started with GitHub Desktop.](/img/github/desktop_welcome.png)

In the cloning dialog, under **Local path**, click **Choose** and select the **GlacierOrganisation.CommunityPatches** folder in your Simple Mod Framework mods directory. And make sure that this folder is empty.

![Cloning the repository.](/img/github/desktop_cloning.png)

Click **Clone**. Wait for GitHub Desktop to finish downloading all the files.

When it's done it will ask how you plan to use this fork. Make sure **To contribute to the parent project** is selected. Click **Continue**.

Now click the **Repository** tab and choose **Open in Command Prompt** (You may have a different shell such as PowerShell or Windows Terminal, the option is still in the same place.)

![Opening the Command Prompt.](/img/github/desktop_open_terminal.png)

In the terminal type the command `npm install` and wait for it to finish. If you are running into trouble make sure you have installed Node.js and try restarting your computer, then try again.

:::caution Updating the mod

Now that you have the mod set up as a Git repository you **should not update the mod through Simple Mod Framework** when it alerts you of a new version.

Instead please see the final section [Keeping your fork up to date](#keeping-your-fork-up-to-date).

:::

## Create a branch

A Git repository can be thought of as a project's history and a *commit* is an entry in that history. On a fork, we don't want to make commits directly to the `main` branch. `main` is considered the version of the mod that's currently out for release, and our fork can synchronize its `main` branch with the Glacier 2 Modding organization's repository.

So to prevent our fork from getting out of sync, we create a branch for our contributions. Click **Current branch** at the top of the screen and click **New branch**.

Name it something based on the contribution you are making. For example `fix-guard-shirts` or `eyelash-fix` or `fix-robe`. Something that makes sense for you. Then click **Create branch**.

![Creating a new branch.](/img/github/create_branch.png)

## Make your changes

With the branch now created you are free to work on the changes you want to submit. Do your work in GlacierKit, or any other software, deploy the mod and make sure your contribution works.

Then, go back to GitHub Desktop to make our submission.

## Making a commit

The changed files are checked, which is what we want. In the lower left text boxes we write what our commit will do. First a summary, and then a description. The SMF mod template uses [conventional commits](https://www.conventionalcommits.org/en/v1.0.0) to create changelogs, the Unofficial Community Patch is no different. To quote the readme:

> As a rule of thumb, anything that doesn't drastically alter the mod or make sweeping changes that could break other mods should be either an `enhancement` (for improvements to existing parts of the mod), `feat` (for new parts of the mod) or `fix` (for bugfixes). You can specify the part of the mod you're changing in parentheses like so: `fix(localisation): typo in French text`.
>
> If you do drastically alter the mod or make sweeping changes that could break other mods, add an exclamation mark just before the `:`, and write `BREAKING CHANGE: This thing is now this thing, which means this.` in the "description" or "footer" of the commit.

As far as the Unofficial Community Patch is concerned, we prefer that new additions begin with `feat:` and fixes *to the mod itself* (not fixes to the *game*) begin with `fix:`. Make sure the first word after that begins in lower case as well.

![Making a new commit.](/img/github/making_commit.png)

You will also notice that the description includes the number #459, this is an [issue on the GitHub page](https://github.com/glacier-modding/H3-Unofficial-Community-Patch/issues/459).

Mentioning it in this way will *link* our pull request with the issue. Specifically typing "**Closes** #459" as a description in our commit means that GitHub will automatically close that issue as completed when our pull request is merged. [See GitHub docs](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/using-keywords-in-issues-and-pull-requests#linking-a-pull-request-to-an-issue) for more info. For the Unofficial Community Patch we recommend making an issue for your contribution if one does not exist already.

When you've written a good commit message, click **Commit**. With that done, click **Publish branch** and wait a minute for it to upload to GitHub.

![Publishing our branch.](/img/github/publish_branch.png)

## Submit a pull request

With the branch on GitHub it's time to open a pull request. In GitHub Desktop you can click **Preview Pull Request**.

![A Pull Request preview.](/img/github/pr_preview.png)

This screen is essentially a preview of the changes we are making to the repository. Click **Create pull request** and your browser will open to GitHub. All you have to do now is click **Create pull request** again.

![Opening a pull request on GitHub.](/img/github/github_pr.png)

Your pull request is now open for the project maintainers to examine, and you will receive a notification when your pull request receives comments, is merged, or closed.

![The GitHub pull request is open and awaiting interaction.](/img/github/github_pr_open.png)

For now, you'll want to go back to GitHub Desktop and switch back to the `main` branch.

![Switching branches back to main.](/img/github/switch_to_main.png)

## Keeping your fork up to date

If your pull request was merged, or you otherwise want to update the mod, it's time to sync up our `main` branch with the upstream repository.

In GitHub Desktop, first make sure you are on the `main` branch. Then click **Branch** and choose **Update from upstream/main**.

![Synchronizing our main branch.](/img/github/sync_fork.png)

When this is done you are free to make a new branch if you want to contribute again. You should always make sure `main` is synchronized before making a new branch to develop on.
