

# Github 101

## By

# Christa Wright

Github is a great version control system that software developers implement into their workflow. Its great when you&#39;re working solo and especially effective when you&#39;re working in a team. Learning how to use Github will ease the transition into industry and make team projects a breeze.

So, to begin, download Github and configure your environment. Github offers a lot of documentation to make this easier, here is a link for this. I _highly_ suggest you take the time to set this up now. https://help.github.com/articles/set-up-git/

The commands are

$ git config --global user.name &quot;_Mona Lisa_&quot;

$ git config --global user.name

&gt; Mona Lisa

NOTE: If you need to ever switch accounts, the only way I have found to do this; Windows: go to **Credential Manager** then select **Windows Credentials** and remove the github permission. When you go to push a project, you&#39;ll be prompted to type in your username and password.

_So, now that you have your github account figured out, lets clear some things up_. I&#39;ll be using some terminology that is used often in tech. Here are some definitions.

**Repo** : short for _repository,_ is a central file storage location. It&#39;s used to store several versions of the same project.

**Branch:** a branch runs parallel to a version of the repo. When a branch is made, all the files of the current repo are &#39;copied&#39; into the branch. So, you&#39;ll be free to make your changes without affecting the main branch.

**Master Branch:** This is the main branch that all branches will be merged into. This is what will be used for production, and it&#39;s a common saying &quot;Don&#39;t break master.&quot; So, only merge quality code into master.

**Commit:** a commit is similar to saving a file. Think of it like a checkpoint in a video game, if you die you can go back to that checkpoint. This holds for coding too. If you&#39;re working away on your project and eventually you break it, or it stops working, you can go back to where you made your last commit. When you commit something, you&#39;ll be given a chance to leave a message, leaving yourself a helpful message so you know what each commit does helps. Sometimes I&#39;ll use WIP (Work In Progress) when I&#39;m lazy, and am confident that everything will be fine. Usually it is, but sometimes it&#39;s not and I&#39;ll have to go back through several commits cursing that I didn&#39;t document my work better.

**Merge:** Merging takes the chances from a branch and adds them to another, such as the master branch. This often happens in the form of a pull request (see below).

**Pull Request: (PR)** A pull request is made when you&#39;ve been working on a branch and are ready to have it reviewed by others in the project to have it merged into master. PRs are a great way to check for quality control.

**Local:** Having something &#39;local&#39; means that it is on your own personal machine (computer). You&#39;ll have a _local_ copy of a _repo_ when you clone it.

For more terms refer to : https://help.github.com/articles/github-glossary/

Ok, so know that you know the lingo, let&#39;s get started.

If you are working in a group you&#39;ll either be the one making the repo, or the one cloning it to get it locally.

If you&#39;re the one making the repo:

On Github, make the repo you&#39;re planning to make.

Clone it down, and you&#39;ll easily be able to work with it.

**Note:** There are several ways to make a new repo, you could make it locally with git init, but the method above is the easiest way to start it – personally.

 At this point if you&#39;re contributing to the project, you will also clone it.

**$ git clone** [repo url]

Now that you have the repo locally on your machine, you&#39;re ready to start coding.

But wait! Make sure you make a new branch, so you won&#39;t be pushing to master! Do this with the command

**$ git checkout -b [branch\_name]** (without the brackets [] )

To check that you&#39;re on the new branch use the command

**$ git branch**

This will show you the branches you have locally and will highlight the branch you&#39;re on.

Now you&#39;re ready to begin coding. Write your code in the repo. When you make some progress make a commit.

**$ git status**  (this will show you what git is currently tracking)

**$ git branch** (THIS IS IMPORTANT! Make sure you&#39;re on the right branch)

**$ git add .       ** (the . command makes all the files tracked by git , you can also just add individual files by typing in the file name )

**$ git commit -m &quot;Write your message here&quot;**

Now you can check your commits and the commits of the other group members by typing

**$ git log** ( Shows the history of commits with the commit number, author, date, and commit message. When a project has many commits the list gets large )

This is often overwhelming, so I&#39;ll filter it by typing

**$ git log –pretty=oneline** ( This will show the messages of the commits and some other info)

When you&#39;re ready to push:

Double check to make sure you&#39;re on the right branch:

**$ git branch**

Now go through and

**$ git add . [**OR**] git add [**the file you are adding**]**

**$ git commit -m [**Your message**]**

If you have multiple commits, make sure you squash them. Look at the history of your commit with _git log_ and count them. To squash:

**$ git rebase -i HEAD~[**x**]** (x represents the number of commits you have. For an example refer to this link: [http://gitready.com/advanced/2009/02/10/squashing-commits-with-rebase.html](http://gitready.com/advanced/2009/02/10/squashing-commits-with-rebase.html)

You&#39;ll now have a vim interface where you will be presented with _x_ commits. To squash them change the _pick_ to an **s** for squash. When you&#39;re done you&#39;ll be taken to another screen with your commit messages here. Remember you&#39;re in vim. Scroll down to the commit messages and press dd to delete the line. Leave only one message undeleted. Feel free to change the message to something that represents what you are merging.

Now you may push your local repo on your own branch to the repo on Github.

**$ git push**

Sometimes you&#39;ll have to do

**$ git push -f** (f for force)

Git may say that you need to change the upstream, follow git&#39;s prompts.

After pushing to the online repo, refresh your Github page. You may not be able to see your changes in the repo! That&#39;s ok, you&#39;ll be prompted to make a new Pull Request. If the repo has been forked, make sure you&#39;re making a pull request for the correct repo: your master branch&#39;s repo. Here is the official github page for creating a pull request: [https://help.github.com/articles/creating-a-pull-request/](https://help.github.com/articles/creating-a-pull-request/)

As you work through making a Pull Request, there will be a place for you to make a comment on what the Pull Request does. In this place here, if there were any Issues you&#39;re fixing, include the number here with a # before the number. It&#39;ll show a small drop down with the number of the Issue and the title of the Issue.

After the Pull Request is made, let your teammates know. Github doesn&#39;t notify people when a Pull Request is made. Also, github will let you know if there are any merge issues. If there are, you&#39;ll have to go through a rebase, which will be explained later. Assuming there are no problems with merging, Github will give you permission. But don&#39;t merge your own Pull Requests! This is a chance for your teammates to review your code and ensure that master won&#39;t break when the code is merged.

After the code has been reviewed and merged, your teammates will need to

**$ git pull** to get the latest form of the repo

