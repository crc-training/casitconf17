## Lab 1
## Verify Local Environment
Allotted Time: 10 minutes

## Overview

In this exercise each participant configures and tests a local development environment and registers for the Community Slacks.

## Connect to Node (Everyone)

* ssh chef@NODE 

If you don't have ssh available please downlowd an ssh client. For Windows, a good option is [putty](http://www.putty.org/).


## Introduction to Git

## Customize your workstation (Everyone)

```
   git config --global user.name "YOUR NAME"
   git config --global user.email "YOUR EMAIL ADDRESS"

```

Example: 

```
$ git config --global user.name "Jennifer Davis"
$ git config --global user.email "sparklydevops@gmail.com"
```

## Verify .gitconfig creation (Everyone)

```
   cat ~/.gitconfig
```

Example:

```
   cat ~/.gitconfig
[user]
   name = Jennifer Davis
   email = sparklydevops@gmail.com
```

## Set your preferred git editor (Everyone)

If you don't set your preferred editor, it will use the default text editor for the system.

* emacs
* nano
* vi/vim

```
   git config --global core.editor EDITORNAME
```

Example:
```
$ git config --global core.editor nano
```

## Add any additional desired git aliases (Optional)


## Verify the configuration (Everyone)

```
   git config --list
```

Example Output:

```
[sumac@ip-10-0-0-107 ~]$ git config --list
user.name=Jennifer Davis
user.email=sparklydevops@gmail.com
core.editor=vi
```

## Create a project Directory (Everyone)

```
   mkdir wd
   cd wd
```


## Create a GitHub identity (Everyone)

* If you don't already have a github account, create one.
* Browse to http://github.com. Supply a username, email address, and password.
* Free plan is fine. Other plans allow you to have private repositories.

## (Optional) Setting up your GitHub keys (Everyone)

If you want to skip the added burden of entering your username and password each time at the prompt with git, you can follow the steps here to set up your ssh keys:

https://help.github.com/articles/generating-ssh-keys/

Example output of successful setup of keys:

```
[sumac@ip-10-0-0-107 ~]$ ssh -T git@github.com
Hi sparklydevops! You've successfully authenticated, but GitHub does not provide shell access.
```


![Commiting to my branch](images/lab_1_fork.png "GUI shows availability to click on pull request.")
![Creating a pull request](images/lab_1_pull_request.png "Leave a comment and create pull request")

## Join the Chef Community Slacks

Follow the instructions on the [Chef Community Slack Page](http://community-slack.chef.io/) and then sign in to the Chef Community Slack. You can either use Slack from a web browser or from the app. 

Join the [Habitat Community Slack](http://slack.habitat.sh).


## Outcomes

* You will have logged into your node and configured git.
* You will have signed up for the Chef and Habitat Community Slack.

\pagebreak