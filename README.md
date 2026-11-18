# Community Garden Festival: Git Practice

A beginner-friendly Git workshop for people who have never coded. You will edit a
plain-text festival plan and use Git to save versions, try an idea on a branch,
and bring it back to the main plan. **No programming is involved.**

Keep the **progress checker** open in your browser while you work (the organiser
will share the link). Sign in with GitHub, and it ticks off each step as you finish it.

## What you'll need

- A free GitHub account
- Git installed on your computer
- A plain-text editor (for example, Notepad, TextEdit in plain-text mode, or VS Code)

**Git** is a tool on your computer that keeps a history of changes. **GitHub** is a
website where a copy of that history can be shared.

## Step 1: Fork the repo

On this repository's GitHub page, click **Fork** (top right), then **Create fork**.
You now have your own copy at `github.com/YOUR-USERNAME/community-garden-git-practice`.

## Step 2: Star the repo

Come back to this page and click **☆ Star** (top right). Stars are how people
bookmark and show appreciation for projects.

## Step 3: Make a commit

On **your fork's** page, click the green **Code** button and copy the HTTPS link.
Open a terminal in the folder where you want to keep workshop files, then run:

```text
git clone PASTE-YOUR-FORK-LINK-HERE
cd community-garden-git-practice
```

If Git asks who you are, set a name and the email you use on GitHub:

```text
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Open `festival-plan.txt` in your text editor and fill in the festival location.
Save the file, then run:

```text
git status
git diff
```

- `git status` is your “what has changed?” check. Use it often.
- `git diff` shows the exact edits Git has noticed.

Now stage, commit, and upload your change:

```text
git add festival-plan.txt
git commit -m "Add the festival location"
git log --oneline
git push
```

Think of **stage** as choosing what goes into a save, **commit** as making that
save in the project history, and **push** as uploading your saves to GitHub.
The first time you push, GitHub may ask you to sign in through a browser.
Never type your password into the terminal.

## Steps 4 and 5: Create a branch and open a pull request

A **branch** is a separate line of work. It lets you try an idea without
changing the main version straight away.

Create and move to a branch:

```text
git switch -c improve-accessibility
```

Add an accessibility detail to the plan, save, then commit and upload the branch:

```text
git add festival-plan.txt
git commit -m "Add an accessibility detail"
git push -u origin improve-accessibility
```

A **pull request** asks for your branch to be added to the main version, so
others can review it first. On your fork's GitHub page:

1. Click **Compare & pull request** (or go to **Pull requests > New pull request**).
2. ⚠️ Set **base repository** to **your fork** (`YOUR-USERNAME/community-garden-git-practice`),
   base `main`, and compare `improve-accessibility`.
3. Write a short title and click **Create pull request**.

## Step 6: Merge your work

On your pull request page, click **Merge pull request**, then **Confirm merge**.
Your branch is now part of `main` on GitHub. Bring that change to your computer:

```text
git switch main
git pull
```

Open `festival-plan.txt` and see that the accessibility detail is now in the main
plan. Check the progress checker: all six steps should be ticked. 🎉

## Bonus: merge on your own computer

You can also merge without GitHub:

```text
git switch -c add-food
```

Add a food stall idea, save, and commit it. Then:

```text
git switch main
git merge add-food
git push
```

## Quick reference

| Command | In everyday language |
|---|---|
| `git status` | What has changed? |
| `git diff` | Show me the edits |
| `git add festival-plan.txt` | Choose this file for the next save |
| `git commit -m "Describe the change"` | Save a version in the history |
| `git log --oneline` | Show the saved versions |
| `git push` | Upload my saves to GitHub |
| `git pull` | Download and combine the latest saves from GitHub |
| `git switch -c name` | Create a branch and move to it |
| `git switch main` | Go back to the main branch |
| `git merge name` | Bring that branch's changes into this one |

## If something goes wrong

- **“not a git repository”**: In the terminal, move into the folder created by
  `git clone` and try again.
- **“nothing to commit”**: Save your file, then check `git status`. Make sure
  you changed a file inside the cloned folder.
- **Git says your name or email is unknown**: Follow the setup commands in step 3.
- **The checker hasn't ticked a step**: Did you `git push`? The checker can only
  see what's on GitHub. It refreshes every 30 seconds.
- **You see a conflict or an unfamiliar message**: Pause and ask the organiser.
  Your files are usually still safe; don't run a command you don't understand.

## Organiser notes

1. Publish `.gitignore`, `README.md`, and `festival-plan.txt` as a **public**
   GitHub repository named `JayNightmare/community-garden-git-practice`.
2. Run the progress checker site (see its own README) and share its link.
3. Ask participants to create a GitHub account and install Git in advance, or set
   aside time and helpers for setup.
4. Suggested 45-minute session: setup, fork and star (10 min), first commit and
   push (15 min), branch, pull request and merge (15 min), recap (5 min).
5. Avoid destructive commands in a beginner workshop; if someone gets stuck, help
   them inspect `git status` before changing anything.
