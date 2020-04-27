# [`the-resources`](https://github.com/learninglab-dev/the-resources) Setup

Use this guide if you're looking to try out these CSS tutorials within `the-resources` project.

**Note:** Not every tutorial in this repo works seemlessly with `the-resources`-- *yet!* Some require that you have direct access to the HTML. You *could* put this HTML directly into your markdown file, but it might take a bit of practice to get exactly what you want. Tutorials that require you to edit HTML will say so at the top.

## Video Walkthrough

Watching this quick video may be enough to get you up and running:
[![Watch the video](https://img.youtube.com/vi/yMuQwsX-Q8g/hqdefault.jpg)](https://www.youtube.com/watch?v=yMuQwsX-Q8g)

## List of steps

But here are the steps, if you prefer the written word. :smile:

1. Open [`the-resources`](https://github.com/learninglab-dev/the-resources) repo and navigate into the `/public/stylesheets` folder.

  ![Add a gif of this step here](/path to my future gif)

2. Click `Create new file` and give your file an apt name. This could be your name or the name of your theme. Just make sure your filename has no spaces, capital letters, or other punctuation and that you add the extension `.css` when you create it.

  ![Add a gif of this step here](/path to my future gif)

3. Write your tutorial CSS directly in the new file editor! We'll commit it when you're finished.

  **Note**: Because `the-resources` is live on the internets, you won't be able to see your styles until someone on the LL staff approves your pull request. We know this is a bummer! But we want to make sure only things you're proud of end up online. If you'd like to have live previews of your styles and are willing to spend a bit of extra time setting up, you can follow the instructions under [Running a Local Server](#running-a-local-server) below.

4. When you've completed the tutorial, it's time to commit your CSS file. To do this, scroll down to the bottom until you see "Commit new file". In the top box there add a commit message explaining what you're adding to the repo. A good template is "Add new stylesheet [name of your styles]". Then select "Create a new branch for this commit" and name your branch. Again, a good name is something like "[your first name]-[your last initial]-styles". Remember there should be no spaces and no capital letters in the name of your branch. Finally click `Propose new file`.

  ![Add a gif of this step here](/path to my future gif)

5. That should have taken you to the "Open a pull request" screen. Here you can assign reviewers by clicking the little gear by Reviewers on the right, if you want someone specific to look at your PR. Otherwise, just click `Create pull request` to submit it. We'll check it out and get back to you shortly!

  ![Add a gif of this step here](/path to my future gif)

5. Once you're received word that your pull request has been approved and merged, check out [resources.learninglab.xyz/styled](https://resources.learninglab.xyz/styled) to view all the markdown pages with your new styles!

## Running a Local Server

When you're ready to do more with styling, you can run a local copy of `resources.learninglab.xyz`! This will allow you to view your changes immediately in the browser without submitting PRs or waiting for approval. Of course, you should still submit a PR when you've got something you're happy with, so your new styles can go live on the full site.

To setup a local server, follow these steps:

0. Make sure you have `node.js` and `npm` installed on your machine. You can do this with a package manager like Homebrew, or you can grab the installer for your operating system [here](https://nodejs.org/en/download/).

1. Open your command line interface app (on a Mac this is Terminal; on Windows you can download a similar program).

2. Decide where you'd like to save your local copy of the repo. Then use the command `cd` to navigate to that location. For example, if you want to put the copy on your desktop, you'd enter `cd desktop` in the command line.

3. Once you're in the right place, head over to `the-resources` repo on github. There you'll click the green button `Clone or download` and copy the url that pops up.

4. Back in your terminal, enter `git clone [paste url link]`. This should start the process of downloading the repo.

5. When the download finishes, enter `cd the-resources` to navigate into your new folder. Then install its dependencies by typing `npm i`. This might take a minute or two.

6. Finally, you can enter `npm run devstart` and then navigate to `localhost:3000` in your browser. You should see a copy of the resources! Now, when you make an save changes to your local copy of the repository, you updates should appear here in the browser right away.
