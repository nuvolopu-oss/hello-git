## GitHub Flow
## 🎯 Let’s start the day following the GitHub flow from the very beginning until deployment. We will deploy a very simple HTML page to focus our learning on git and GitHub.

In this challenge we will:

create a GitHub repo
create a feature branch and merge a pull request
create a static GitHub Pages site
Some Reading
GitHub Flow is a lightweight, branch-based workflow that was introduced in 2011. GitHub’s official documentation describes the workflow as follows:

- Anything in the master branch is deployable
- To work on something new, create a descriptively named branch from the master (ie: new-oauth2-scopes)
- Commit to that branch locally and regularly push your work to the same named branch on the server
- When you need feedback or help, or you think the branch is ready for merging, open a pull request
- After someone else has reviewed and signed off on the feature, you can merge it into master
- Once it is merged and pushed to `master`, you should deploy immediately
Create Your Repository
Before we actually do our first commit, we need to create a local repository and then publish it to GitHub.

In the terminal, create the local repository (run the lines one by one, and check the outputs):

cd ~/code/nuvolopu-oss
mkdir hello-git
cd hello-git
git init
touch README.md .gitignore
code .
Let’s look at some of the decisions we made when writing these commands:

The repo name:

We want to choose a name that is meaningful and unique, but maybe not too complex
For this repo, we are going to use it for a simple “Hello world” example. So let’s call it hello-git

The path:

Keeps the repository outside your Documents folder, for example in ~/code/nuvolopu-oss/hello-git. The commands above create this folder.

README.md:

The command above creates README.md locally; we will add its content before the first commit.

The repository README gives you an opportunity to expand on your Description and share more context with other developers. As such, they are a valuable resource and should be kept updated with any major changes you make to the repo.

.gitignore:

There are often files you work with locally that shouldn’t be stored on your remote repository.

A .gitignore file is how we tell git that we don’t want to track these files and they should not be flagged when we check our status or loaded if we ask it to add all our files at once.

Why would I want any files to be local-only?

Space: GitHub is not a storage space. A standard remote repository has a limited amount of GB available for you, we don’t want any files on our remote repository that take up space but are not relevant to other users. There are also size restrictions for each commit/push and going over can cause all sorts of problems. Images, videos, spreadsheets, datasets of any kind should ideally be stored elsewhere.

Security: Private keys and personal data should be kept off remote repositories. Other users have written bots that scan repositories for API keys and other important data so they can steal your information. Be cautious about what you push to GitHub and remember that because git tracks your changes, deleting locally and repushing will not protect your data as the original change will still be available.

We will create .gitignore ourselves so we can see exactly which files Git is asked to ignore.

Repository Created
The local folder now contains the repository metadata and an empty README:

git status
You should see two untracked files.

Open the repo folder
code .
The folder is open in VS Code, ready for you to edit README.md and .gitignore.

Complete the README.md
Let’s add some information to the README.md. Fill it with some markdown language, whatever you feel like, just get a feel for writing in markdown! Try something new like adding a logo, a sticker, an image - or even a gif!

Here is a markdown cheat sheet to get you started and here are some examples of impressive repo READMEs for inspiration! Check out this Pacman game README in particular.

Don’t forget to save your file when you’re done.

Create a .gitignore
Add a few lines to the file named .gitignore:

*.csv       # all csvs will be ignored by git
data/       # everything inside the data folder will be ignored by git
Don’t forget to save your file when you’re done.

Time to Commit
Let’s check the repository status in the terminal:

git status
❓ What do the colours of the filenames tell you about your repository?

Adding Files to a Commit
Git does not automatically select files for a commit. You explicitly stage the files you want to include.

Stage the README.md file:

git add README.md
git status
The colours will tell you that README.md is staged to be added; .gitignore is still untracked and will not be included. Stage it before committing both files.

git add .gitignore
Commit Messages
❗️ You should always write a meaningful commit message.❗️

Meaningful commit messages give other programmers context for what a commit was intended to do, which makes it easier to review your code. It also allows them (and you!) to easily identify which commit introduced an error.

💡 Three months from now, you will probably not remember why you made a given commit, so commit messages are also useful for understanding your own coding choices when you come back to fix something. Be kind to future you!

Keep commit messages present tense and think of what you would say following the words “This commit will…“ or This commit should…

Commit Message Examples
This commit will… add subtitles to the introduction video

This commit should… fix the bug deleting items in the checkout page

A useful commit message for this particular commit might read something like: Update README.md and add .gitignore

Commit Messages vs Bodies
Review the staged changes:

git diff --staged
Then commit:

git commit -m "Update README.md and add .gitignore"
If you want to add a longer description, you can just run git commit. This will open a file in your code editor (VS Code). The first line is the commit message, then leave a blank line, and then type the longer description. Finally, close the file (and say yes when prompted if you want to save it).

Publish Your Repository
Time to get your local work on to GitHub! Let’s create a public repository, then push your master branch:

gh repo create
Answer the questions:

You want to create a public repo
Description: “Practice repository for a Hello World example”
The source is the current folder (.): you can hit Enter to accept the default.
Your remote should be named origin: you can hit Enter to accept the default.
You want to push your repo: you can hit Enter to accept the default.
Private repositories can use GitHub Pages on eligible paid plans; this exercise uses a public repository so it works with free accounts. Check your repository on GitHub and make sure all your files are as expected. Your README.md will display on the main page.

Creating a Feature Branch
Until now, we only had one branch, the master branch.

We were creating a new commit directly on the master.

This is actually not a good practice! The master branch should always have the version in production that is fully functional. If you push bad code to your master branch, it can break your application.

That’s why, when we want to modify code, we create new branches called “feature branches”.

We test our code and when we are “sure” that it works, we merge it back into the master branch.

Naming Conventions
❗️ Name every branch something meaningful.❗️

Try to think of a name that will make it clear what work was done. Many programmers and companies stick to the following naming convention username-featurename-version#.

Something like sbrown-subtitles-1 or barbara-bugbash-0 will do nicely.

In this branch, we’re going to add an html file to our repository so we can play with GitHub pages!

Create this new branch and make sure to follow the above naming convention. Set the branch name in your terminal, then create and switch to it:

git checkout -b nuvolopu-oss-github-pages-1
You are now ready to code in this branch.

Adding an HTML file
👉 In VS Code, let’s add a new file called index.html.

💡 The .html at the end of the file tells us what (coding) language the file is written in.

Open the index.html file and copy-paste the following HTML code inside:

<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css" integrity="sha384-WskhaSGFgHYWDcbwN70/dfYBj47jz9qbsMId/iRN3ewGhXQFZCSftd1LZCfmhktB" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.3/umd/popper.min.js" integrity="sha384-ZMP7rVo3mIykV+2+9J3UJ46jBk0WLaUAdn689aCwoqbBJiSnjAK/l8WvCWPIPm49" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/js/bootstrap.min.js" integrity="sha384-smHYKdLADwkXOn1EmN1qk/HfnUcbVRZyYmZ4qpPea6sjB/pTJ0euyQp0Mk8ck+5T" crossorigin="anonymous"></script>
  </body>
</html>
Make sure you save that file. Check its status, stage it, review the staged changes, and commit it:

git status
git add index.html
git commit -m "Add GitHub Pages landing page"
To get our new branch up to our remote repo, push it and set its upstream:

git push -u origin nuvolopu-oss-github-pages-1
Check the repo on GitHub:

gh browse
❓ Can you see the new branch? How can you check which files have been changed?

GitHub Pages
Let’s check that our GitHub Pages site displays as expected.

On the GitHub web app, select the Settings tab and then Pages.

We’re going to keep the default Source Deploy from branch.

Then you will need to set the Branch dropdown to be your feature branch. We will change it back to master once we’ve merged our feature into the main branch.

Make sure to hit “Save”.

Now you can open your Pages site in your browser by using your github username below!

https://nuvolopu-oss.github.io/hello-git/

If you see “Hello, world!” then it worked! Feel free to play around with the html if you finish your challenges for the unit early, but for now let’s focus on getting this feature merged into the main branch!

😎 Every time a commit is pushed to this feature branch, GitHub Pages will automatically deploy the changes to this URL.

When we’re ready to merge this feature branch, we will reset the branch in Pages Settings to master. After the pull request is merged, Pages will deploy the master branch.

Create a Pull Request
Time to compare and pull request! When we open a pull request, git will compare your branch with the master and assess any potential conflicts between your changes and the master branch. We won’t have any conflicts right now, because no one else is working in our repository!

On GitHub.com, start a Pull Request: GitHub offers a “compare & pull request” button after you push your branch.

The base is the branch you are merging into (master) and the head is your feature branch.

PR Review
You now need someone to look at your code, give some feedback and eventually merge it (a rule when using the GitHub flow is that someone other than the author should merge a Pull Request).

Head over to https://github.com/nuvolopu-oss/hello-git/settings/collaboration (accessible through Settings > Collaborators) and add your buddy of the day to the repository by asking their GitHub nickname. They should receive an email invitation to opt-in. If you don’t have a buddy today for any reason, ask another student or even a TA

Once this setup is done, ask your buddy to review the pull request. If they have comments (indentation, errors, etc.), update the code in the same branch, then stage, commit, and push the changes. The pull request updates automatically:

git add index.html
git commit -m "Apply review feedback"
git push
In the end, if you and your reviewer agree on the code, the reviewer should merge the Pull Request. After merging, there is a button “Delete branch”. We advise that you click on it, because in the GitHub flow, a merged branch is a dead branch and no work should be pushed to it anymore.

What happens next?
Merging the Pull Request on GitHub created a merge commit on master. It means that your local repository on your laptop is not up to date anymore.

Just as we had to push our local code to update the remote code, now we have to pull the remote code to update the code in our local master branch.

Update your local master branch and remove the local feature branch:

git checkout master
git pull
git branch -d nuvolopu-oss-github-pages-1
That’s it! You’ve covered all of the basics of git and GitHub 🤯

Final thoughts
📚 Github summarized this flow in a guide that you may want to read now or bookmark for later.

The power of the GitHub flow comes from being accessible even to git beginners. git is a very powerful tool and can be intimidating if not introduced correctly. With that flow, anyone in the team can pick up the collaboration process with a little training (what you just did!).

If you learn to use Git from your terminal, a few commands get you far: status, diff, checkout -b, add, commit, push, pull, and branch -d.

If you talk with other developers about git, some advanced concepts might come up, like stash, cherry-pick, rebase, reset or reflog. There is plenty of time to learn about those topics and adapt your knowledge to your team. We won’t cover these topics but at least you have some keywords to Google!

🏁 Congratulations on finishing this reboot challenge! Don’t forget to select “I’m Done!” 🚀
