# GitHub Command Line Tools

## Basic commands
If you want to learn more about the CLI commands, here is the official documentation. It explains all the features and flags you can use and will complement what we will cover in this article.


### Authentication
Before working with GitHub CLI, you have to authenticate yourself. Run the following commands to authenticate with your GitHub account:

`gh auth login [flags]`

The default authentication mode is a web-based browser flow. You can use `-h` or `--hostname` to specify the hostname of your repository (when you have an Enterprise account for exemple) and `--with-token` to read a token from standard input.


### Logout
If you need to log out from your Github account, use this command:

`gh auth logout [flags]`

This command deletes the authentication configuration of the host. You can specify the host you want to log out by using the `--hostname` flag.


### Repository
To create, clone, fork or view your repositories, use the following command:

`gh repo`


### Clone
To clone locally your GitHub repository:

`gh repo clone <repository> [<directory>]`

To clone your repository you have to use the `OWNER/REPO` syntax. But if you don’t pass the owner argument in your command, it defaults to the name of the authenticated user.


### Create
It is very simple to create your own repository:

`gh repo create [<name>] [flags]`

If you don’t pass a name, GitHub will create a repository with your current directory's name. If you want to add a description of your repository, use the flag `-d` or `--description`.


### Pull Requests
To manage your pull request, you need to use:

`gh pr`

This command and the following inherit from parents commands. You can always specify your repository by using the flag `--repo` or `-R`.


### Create
Create a pull request on GitHub with this command.

`gh pr create [flags]`

 You can manage your pull request by adding these flags:

* `--title`: Title of the pull request

* `--body`: Body of the pull request

* `--base`: The branch into which you want your code to be merged

* `--head`: The branch that contains commits for your pull request (default: current branch)

* `--assignee`: Assign people by their login


### Close
To close a pull request, you need to know its URL, the branch name or the number of the pull request:

`gh pr close {<number> | <url> | <branch>} [flags]`

If you want to delete the source branch when closing it, both locally and remotely, you can add the flag `-d` or `--delete-branch`.


### List
To list and filter pull requests in your repository, use the following command.

`gh pr list [flags]`

You can filter your search by using the following tags:

* `--limit` or `-L`: Maximum number of items to fetch (default 30)

* `--state` or `-s {open|closed|merged|all}`: Filter by state (default "open")

* `--label` or `-l`: Filter by labels

* `--assignee` or `-a`: Filter by assignee


### Diff
To see the changes in your pull request, use the following command:

`gh pr diff [<number> | <url> | <branch>] [flags]`


### Merge
Finally, here is the command to merge a pull request:

`gh pr merge {<number> | <url> | <branch>} [flags]`

By default, the branch of your pull request is deleted, both locally and remotely, when you merge. If you want to keep it you can add the flag --delete-branch=false.

## GitHub environments variables
* `GITHUB_TOKEN`: The authentication token requested by the github.com API.

* `GITHUB_ENTERPRISE_TOKEN`: Authentication token for API request to GitHub Enterprise.

* `GH_REPO`: specify your GitHub repository.

* `GH_HOST`: specify the GitHub hostname.


With this overview, you should now be able to start using GitHub CLI to manage all your workflow and be more efficient. If you want, you can learn more about using GitHub and CodePipeline to automate a deployment on AWS in this article.
