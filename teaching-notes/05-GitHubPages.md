## Episode 5: GitHub Pages

https://uwm-libraries.github.io/lc-git/05-github-pages/index.html

https://jamboard.google.com/d/19dL_esijZW5_t4cBb8iCFB1gLJO_wIgHbohNc8sWop4/viewer?pli=1

***************************************
### 10:55 for 45 minutes

In this section:
- What is GitHub Pages?
- How can I use GitHub Pages to collaborate and share my work?
- Set up GitHub Pages in a repository and view the resulting website
- Experiment with contributing to a GitHub Pages website

Documentation for later: https://pages.github.com/

***************************************
### What is GitHub Pages?

Poll in Reactions:

- Who has struggled to make a web page for something you are working on? (whether the struggle was knowledge, technology, or policy related)
- Who has heard of GitHub Pages?

- A service that publishes a website on GitHub from a Git repository
  - Uses the files and folders in the repository as the website content
- An option built in to every GitHub repository

#### Advantages

- Free for open source repositories
- Use Markdown or HTML
- No need to purchase web hosting or a domain name
- Minimize security risks of a database-driven site such as WordPress
  - also no ads, as happens on a free WordPress site

***************************************
### Why Should I Bother with GitHub Pages?

Besides the advantages above:
- Version control for your website, which means:
  - Record of changes over time for you and co-authors, if any
  - Access to past versions of your site for readers - helpful for accurate citation of your work at a point in time
- Collaborate with co-authors without endless email, because:
  - GitHub repositories include features that wrap project communication and planning into the repository and text/code:
    - Issues to list things that need discussing, fixing, or creating
    - Labels and milestones to map plans for future work
    - Allow suggestions and improvements from your audience and new contributors in the form of pull requests
    - Automatically track contributions - important for documenting authorship and credit

In this section we are focusing on publishing a new website on GitHub and contributing to a website that we don't have authorship access to.

*To Jamboard*
Lesson material from the Carpentries Lesson Development training focuses on using Issues, Labels, and Milestones in GitHub to plan and manage a collaborative project: https://carpentries.github.io/lesson-development-training/26-collaborating.html

***************************************
### Using GitHub Pages

We have a repository on GitHub now, so let's use it to explore GitHub pages.

*Share GitHub screen with `hello-world` repo visible*

Any repository on GitHub can use GitHub pages. First, we need to turn it on:

- Settings
- Pages (under Code and automation)
  - Pages needs to know where you want to serve the site from:
    - Source: Deploy from a branch
    - Branch: can do this from any branch in the repo; we will use `main`
      - Brief aside on branches - we will briefly use branches in the next section. They are a way to allow multiple versions of a project to exist simulaneously in one repository. Sometimes a GH Pages site is hosted from a branch called `gh-pages`
    - Directory: can serve the site from `/` (root) or from a directory called `/docs`; we will choose `/` (root) - this is the most general location in our repository's file structure.
  - Save
  - Link beneath Save to learn about adding a Jekyll theme
    - we will not add a theme now; this is a way to add a style to your site without writing custom CSS
  - Skip custom domain - but you could do this if you wanted or needed to

Now we can view our site. Since we didn't use a custom domain, our site is at:
https://jbkieffer.github.io/hello-world/ 

*to Jamboard*
This is the standard pattern for a GitHub pages site using the default domain name:

  - https://
  - the account name, either a person or an organization
  - .github.io/
  - the name of the repository
    - This is one reason why you can't put spaces in a repository name!

- Only the contents of `index.md` are served.
- `README.md` is only visible in the code side. 
- If we did not have an `index.md` file, GHPages would use the `README.md` file as the site's home page.

Now that we know our URL, it's good practice to put it into the metadata about the repository:

- Copy your URL from your site
- Back in the code side of the repository
- Code view
- About right sidebar, click the gear
  - Description: A repository for learning about Git and GitHub
  - Website: Paste in your URL. It's ghosted in the field but it won't autopopulate
  - Leave everything else alone for now
  - Save changes 

#### What questions do you have at this point?

***************************************
### Collaborating and Contributing

Part of the advantage of using GitHub is being able to collaborate with co-authors and interact with contributors without endless email threads and documents infested with Track Changes and comments. 

This is also true for websites served using GH Pages.

Define terms:

- *Collaborator* or *Co-author*: someone who has write access to your repository
  - Can edit files without additional permission
  - All changes are still controlled with Git, so no changes are ever lost
- *Contributor*: Someone who does not have write access to your repository
  - Cannot edit files in your repository
  - May still have valuable contributions to the work

We are going to practice the workflow that a *Contributor* would use to suggest changes to your website (or whatever your project repository contains).

This workflow is called fork/branch/pull-request, and it's a standard process for interacting with and contributing to open source projects.

I'm going to demonstrate by contributing to Stephen's `hello-world` repository. You can follow along by contributing to my `hello-world` repository:
https://github.com/jbkieffer/hello-world

*Paste jbk repo into Zoom chat*

Here's some incentive for you to follow along - when you fork my `hello-world` repository, it will come with a copy of my teaching notes for this session.

Let's open the repository we're going to contribute to in a new browser tab:
https://github.com/srappel/hello-world

#### Contribution scenario

Stephen is working on a website and has asked some colleagues to take a look and offer suggestions. He shares links to the rendered site and his GitHub repository. Maybe I find typos or see some information I can enhance. I can't directly edit his site, but I can still contribute without sending him an email.

This process is intimidating the first (or tenth) time you do it. It's important to remember that **you can't break it**. Really. If something goes wrong you'll have a commit in a place you didn't expect. Since Git means unlimited undo, any error is recoverable.

**Fork**

First, I need to `fork`, or copy, Stephen's repository:

- Repository home page, upper right, click `Fork`
- Owner: Should be your own username (mine may not be; change)
- Repository name: In the real world, it's good practice to keep the same repository name
  - GH won't allow this here because I already have a repo named `hello-world` (you do, too)
  - I will use Stephen's initials to differentiate his repo from mine: `hello-world-sra`
    - You can do the same with `hello-world-jbk` or whatever name you want
  - Click Create fork
- GH will place a copy of this repo into your account
- Inside the copy, GH puts a note at the top left to help you remember where the repo came from

**Edit**

Inside my copy of Stephen's repository, I can make those edits I spotted. For our workshop, I'm going to edit `index.md` and add a few more Markdown examples. To follow along, open your copy of my `index.md`

*Paste Markdown resources into Jamboard*
Markdown resource: https://guides.github.com/features/mastering-markdown/

- Click the pencil in the upper right to edit the file directly in GH
- Add some more header levels and unordered list items
- Save changes in the Commit section
  - I need to write a commit message that tells Stephen what I did
    - Added more Markdown to index.md
    - If desired, extended description can give more context: "I noticed that the Markdown cheat sheet was missing some elements." 

**Branch**

Because I want to send my changes back to Stephen, I DON'T commit directly to the `main` branch. Choose "Create a new branch for this commit and start a pull request"

What are we doing?

I mentioned that branches are a way to allow multiple versions of a project to exist simulaneously in one repository. When you suggest changes to someone else's content, it's good practice to enclose your changes in a separate branch. That way, the content owner can inspect your changes in a container (a separate branch) before adding them to their repository. The branch is also a record for you to show what contributions you've made.

We need a new branch name that tells us what the branch is for: `add-markdown`

Click Propose File Change

**Pull Request**

*Comparing changes:*

- base: `main`
- compare: your-branch-name (here `add-markdown`)
  - The repository you're contributing to should be on the left
  - The forked repository you've changed should be on the right
  - You may need to click "Compare across forks" to be sure that the base repository is the content owner's:
    - Base repository: `jbkieffer/hello-world` base: `main`
    - Head repository: `yourGHname/hello-world-jbk` compare: `add-markdown`
- See your commit message and description if you added one
- Do a visual comparison that shows line-by-line changes
  - This is a good way to make sure that the changes you're suggesting and the original material are in the right place
  - The changes are usually on the right in the comparison view
- Click Create Pull Request at the top right - big green button

*Open a pull request*

- GH says whether these two versions can merge without conflicts
- We see our commit message
- Below that, we can add a comment - maybe this is information for the content owner about what the pull request is addressing -
  - may be an Issue that was listed in the project planning
  - may be something you identified on your own
  - not mandatory, but good practice when contributing to a project
- Click Create Pull Request in the middle right of the screen - big green button

*Pull request progress*

- Title is usually the commit message
- Again, GH shows whether there are conflicts with the original material
- If we had other changes, we could add more commits to this pull request
- Now that we have created the pull request, the next step is in the repository owner's hands.
  - they will get a notification from GH, and the PR will appear in their list of PRs for the repository

*Demo accepting a PR*

Stephen will be able to view my PR and decide if he wants to accept the changes, ignore or decline the changes, or reply and ask me to modify what I changed.

We can't see Stephen's repo, so I'm going to demo accepting a PR using my `hello-world` repository, hoping that one of you has sent me a PR.

- Navigate back to own `hello-world` repository
- Open Pull Requests - shows how many are open
- Click on a PR
- Review the changes
- Owner can accept, reject, or comment and ask for changes
- Click Merge Pull Request
- The owner can leave comments about the PR - basically a form of commit message
- Click Confirm merge
- The entire process is visible in the history of the original repository
- In a project where documenting contributions is important, GH is doing this for me in this history.

***************************************
### Key points

#### This process seems clumsy - why do it?

- Transparency in project development
- Unlimited undo in a group project
- Compare to co-editing a document in Word or Google Docs - you're probably already familiar with the concepts of what's going on - it's the language that's weird:
  - track changes (fork/branch/PR - granular view of who is contributing what, and how does that change the original?)
  - comments (commit messages and sometimes issues, although we didn't look at issues today - what are people thinking about the progress of the document; where do they want it to change or develop?)
  - sometimes a new copy of the document if things are going in a new direction (a branch, but unlike a Word doc, merging back into the original while keeping a robust record of everything that happened is a built-in function)

*Into Jamboard*
Detailed instructions, with screenshots, for the process we just completed are at https://github.com/carpentries-incubator/swc_github_flow/blob/main/for_novice_contributors.md

Additional lesson material on Pull Requests: https://carpentries-incubator.github.io/git-novice-branch-pr/10-pull-requests/

A real-life use case and lesson: https://programminghistorian.org/en/lessons/collaborative-blog-with-jekyll-github

#### What questions do you have at this point?

***************************************
### Useful info that doesn't have a home

- Branches
  - Offer example of writing cover letters for job applications - template letter may exist in `main`, then create a new branch for each time you customize the letter for a specific application.
  - More lesson material about Git branches: https://carpentries-incubator.github.io/git-novice-branch-pr/07-branches/

- Jekyll
  - Software that takes files written in Markdown, HTML, and CSS and turns them into a web page or web site.
  - Jekyll is one of the ways to produce a website from a set of files and directories (folders) just like the ones you see in Windows File Explorer or Mac Finder
  - These software packages are called "static site generators" because they use information from files, not from databases (database-driven sites are "dynamic" sites, e.g., sites created using WordPress or Drupal).
  - Static sites are more sustainable than dynamic sites because files written in plain text are easier to preserve than database-driven sites where much of the content is housed in a relational database.
  - The files that make up a static site are mostly human readable, so if the website ever needs to be taken down, the archived information can still be read by humans using a text editor.
  - If you work at all with Digital Humanities or Digital Scholarship, static sites are going to come up, and now you've played with them!