# Git, Github and Notebooks


## 1. Consoles

<div class="highlighted">
A console is similar to a file explorer, but instead of a visual interface, it's a text-based interface on a computer. It allows you to enter commands for tasks like navigating, copying, and moving files.
</div>

A file explorer offers a graphical interface for navigating files and folders using buttons and icons, while a console provides a text-based interface where commands are typed to interact with the file system. They serve distinct purposes, with a file explorer being visual and user-friendly, and a console offering command-driven control and automation.

### 1.2 Console commands

| Command | Example | Action |
| --- | --- | --- |
| ls | `ls`  {`-a`, `-l`} | List the current directory files |
| cd DIR | `cd "My documents"` | Change directory |
| cd .. | `cd ..` | Back to the upper directory one level |
| clear | `clear` | Clean console |
| history | `history` | Shows latest commands |
| tab | - | Show available options, autocomplete |
| Up Arrow | - | Extract last command |
| ctrl + l | - | Scroll to active line |
| ctrl + r | - | Search in the command history |
| ctrl + c | - | Stop & kill running command |

??? tip "Advanced commands"
    | Command | Example | Action |
    | --- | --- | --- |
    | pwd | `pwd` | Print working directory path |
    | cat FILE | `cat README.md` | Shows the contents of the file |
    | touch FILE | `touch README.md` | Creates an empty file |
    | mkdir FOLDER | `mkdir "My documents"` | Create a new folder on actual directory |
    | mv FILE DIR | `mv notebook.ipynb "My documents"` | Move file to a new directory |
    | cp FILE DIR | `cp notebook.ipynb "My documents"` | Move file to a new directory |
    | rm FILE | `rm notebook.ipynb` | Remove selected file |
    | rm -r FOLDER | `rm -r "My documents"` | Remove a folder and all the files inside |
    | find --name FILE | `find --name README.md"` | Search for a file in the directory and sublevels |

## 2. Git & Github

Think of **Git** like a notebook that **tracks all the changes you make to your writing**, letting you go back and see every draft. **GitHub** is like **a library where you can keep your notebooks**, and others can borrow them, read your writing, make suggestions, and even work on their own versions of the same story.

### 2.1 What is Git

<div class="highlighted">
Imagine Git as a time-traveling tool for your computer files. It keeps a record of every change you make, so if you accidentally mess something up, you can go back in time to fix it. It's like having an "undo" button for all your coding adventures.
</div>

![git](https://www.nobledesktop.com/image/blog/git-branches-merge.png)

### 2.2 What is Github

<div class="highlighted">
GitHub is like a library for your computer code. It lets you store your code online, so you can access it from anywhere. You can also invite friends to help you work on your code and keep track of all the changes you make.
</div>

GitHub is a platform where people store and colaborate on code for software projects. It's like a digital space where programmers can work together on coding projects.

A repository in GitHub is like a digital folder where you can store and manage your projects, including code, files, and resources. It's a space to colaborate, keep track of changes, and showcase your work. To create a repository you can follow [the official documentation](https://docs.github.com/es/get-started/quickstart/create-a-repo).

``` mermaid
graph TD
    G[Github] --> PP["📷\nDeveloper\nprofile"];
    G --> RP[("⌸ Your\nrepositories")];
    G --> PR[("⌸ Public\nrepositories")];
```

### 2.3 What is a repository

<div class="highlighted">
A repository is like a folder where you store files for a project. It holds your work, tracks changes, and allows others to colaborate on the project. It's like a digital toolbox.
</div>

A repository can be either **local, stored on your computer**, or **remote, stored on a server** like Github. They are linked by using version control systems like Git. Local repositories store your work offline, while remote repositories, often hosted on platforms like GitHub, enable colaboration and backup by syncing changes between local and remote versions.

``` mermaid
graph TD
    G["🅶\nGithub"] --> UR["👩‍💻User profile"];
    UR --> RR[("⧠ Remote\nrepository")];
    RR -->|pull| LG1["⧠\nLocal GIT"];
    LG1 -->|push| RR;
    LG1 -->|pull| WS1["👩‍💻\nLocal computer 1"];
    WS1 -->|commit| LG1;
    WS1 --> LR1[("🖿\nLocal\nrepository")];
    RR -->|pull| LG2["⧠\nLocal GIT"];
    LG2 -->|push| RR;
    LG2 -->|pull| WS2["👨‍💻\nLocal computer 2"];
    WS2 -->|commit| LG2;
    WS2 --> LR2[("🖿\nLocal\nrepository")];
    RR -->|pull| LG3["⧠\nLocal GIT"];
    LG3 -->|push| RR;
    LG3 -->|pull| WS3["👩‍💻\nLocal computer 3"];
    WS3 -->|commit| LG3;
    WS3 --> LR3[("🖿\nLocal\nrepository")]
```

### 2.4 What is a branch

<div class="highlighted">
A branch is like a separate copy of your repository where you can make changes without affecting the main version. It's like having a playground to experiment and work on new features before adding them to the main project.
</div>

``` mermaid
graph LR
    subgraph "Branch main"
    direction LR
    A(("#A")) -->|commit| B(("#B"));
    B -->|commit| C(("#C"));
    C -->|commit| D(("#D"));
    D -->|commit| E(("#E"));
    E -->|commit| F(("#F"));
    end
    C -->|"switch -c"| B2C;
    B2E -->|Pull request| E;
    subgraph "Branch dev-jorge"
    B1B(("#B")) -->|commit| B1C(("#C'"));
    end
    subgraph "Branch dev-marta"
    B2C(("#C")) -->|commit| B2D(("#D'"));
    B2D -->|commit| B2E(("#E'"));
    end
    B -->|"switch -c"| B1B;
    B1C -->|Pull request| D;
```

#### Example

This example shows a common workflow to create a new branch `dev-new-branch` from the original files of `main` branch.

<div class="steps" markdown>
- **Clone repository.** 
    ```sh
    git clone https://github.com/charlstown/ai-applied-education.git
    ```
- **Check branch.** By default it shows local branches, you can add the flag `-r` to show only remote branches or `-a` to show all.
    ```sh
    git branch -a
    ```
    ```output
    remotes/origin/dev-marta
    remotes/origin/dev-juan
    * main
    ```
- **Check dev-marta branch.**
    ```sh
    git switch dev-marta
    git pull
    ```
    ```output title="output"
    Switched to branch 'dev-marta'
    Your branch is behind 'origin/main' by 23 commits, and can be fast-forwarded.
    (use "git pull" to update your local branch)

    Already up to date.
    ```
- **New branch from main.** Change to main branch, then create a new branch with the files from main.
    ```sh
    git switch main
    git pull
    git switch -c dev-new-branch
    ```
- **Push new branch.** Push the new branch from local repository to remote repository.
    ```
    git push –set-upstream origin dev-new-branch
    ```
</div>

Now you can start working on your branch without iterfering the `main` branch.



### 2.5 Git commands

| Command | Example | Action |
| --- | --- | --- |
| **git clone REPO-NAME** | `git clone https://github.com/user/repo.git` | Clone a repository in the local computer |
| **git pull** | `git pull` | Description |
| git status | `git status` | Description |
| git fetch | `git fetch` | Description |
| **git add** | `git add .` ; `git add *` | Description |
| **git commit -m "MESSAGE"** | `git commit -m "update: new section readme"` | Description |
| **git push** | `git push`; `git push origin main` | Description |
| git reset --soft | `git reset --soft` | Keep files but destroy the commits staged |
| git reset --hard | `git reset --hard` | Destroy changes and go to the remote state |

??? tip "Git branching commands"
    | Command | Example | Action |
    | --- | --- | --- |
    | git switch BRANCH | `git switch dev-carlos` | Switch to the selected branch | 
    | git switch -c BRANCH | `git switch -c dev-carlos` | Create new branch and switch to that branch | 
    | git branch | `git branch` (-a- ; -r) | Shows local and remote branches | 
    | git remote prune origin | `git remote prune origin` | Update remote branchs in local memory | 



## 3. Notebooks

<div class="highlighted" makrdown>
A code notebook is like a digital Notepad or Word where you can write and run code. It's a place to mix text, code, and outputs, making it easier to learn and share. 
</div>

In this course, you'll use tools like Google Colab and Jupyter Notebooks to create these interactive notebooks for coding and learning.

#### Notebook Shortcuts

| Shortcut | Action |
| --- | --- |
| - | - |

### 3.1 Google colab

<div class="highlighted" makrdown>
Google Colab is an online platform that allows you to write and execute Python code in a colaborative and interactive environment.
</div>


#### Environments in collab

#### Installing new libraries

#### Open from Github

#### Save in Github


### 3.2 Jupyter notebooks

<div class="highlighted" makrdown>
Google Colab is an online platform that allows you to write and execute Python code in a colaborative and interactive environment.
</div>

#### Environments in Jupyter

Content


## 4. Test your skills

### 4.1 Create a profile repository

The profile README is a repository where you can share information about yourself with the community on GitHub.com by creating a profile README. GitHub shows your profile README at the top of your profile page. Check the oficial documentation of [Github profile README](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme).

<div class="steps" markdown>
- In the upper-right corner of any page, use the :material-plus-box: drop-down menu, and select New repository.

    ![github-repo-create](https://docs.github.com/assets/cb-31554/mw-1440/images/help/repository/repo-create.webp)

- Under "Repository name", type a repository name that matches your GitHub username. For example, if your username is "octocat", the repository name must be "octocat".
- Optionally, in the "Description" field, type a description of your repository. For example, "My personal repository."
- Select Public.
- Select Initialize this repository with a README.
- Click Create repository.
- Above the right sidebar, click Edit README.
</div>

??? tip "Add your repo stats to your README"
    You can add this line of markdown in your README file, to add stats about your work in Github.
    ```markdown
    [![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=charlstown&show_icons=true&theme=nightowl)](https://github.com/anuraghazra/github-readme-stats)
    ```

You can copy this structure to create your README easily.
```markdown
## Hello 👋

Welcome to my Github account! I'm YOUR NAME a ... enthusiast.
In this account, you'll find projects, and resources about ...
I hope you enjoy my content and find it useful.

</br>

### About me

- :computer: I’m currently studying ...
- :microscope: I’m currently learning `AI applied`.
- :v: I’m looking to colaborate on coding for ...


### My favorite repos

- :desktop_computer: **[My repo](#):**.
- :desktop_computer: **[My repo](#):**.
- :desktop_computer: **[My repo](#):**.


### Thank you!

If you have any questions, or comments, please get in touch.

Happy coding! :vulcan_salute:

-- @username
```

Congratulations! You've successfully created your profile README. 


### 4.2 Apply to the program

To request the application for this program you need to know how to fork (copy) the official course repository, modify the files by adding your name and email, and making a pull request to the original repository to add your student data.

#### Fork the course repository

<div class="steps" markdown>
- Go to the [ai-applied-repository](https://github.com/charlstown/ai-applied-education), that contains the files of this course.
- Fork the repository by pressing the fork button on the top right corner.
    ![github-fork-button](/ai-applied-education/assets/images/11-github-fork-button.jpg)
- Add you user as owner of the new copy of the repository, and make sure you only copy the main branch.
    ![github-fork-repo](/ai-applied-education/assets/images/11-github-fork-repository.jpg)
</div>

#### Clone the repository in your local computer

<div class="steps" markdown>
- Open your prefered console, git bash or anaconda and go to the directory where you want to clone the project.
    ```bash
    cd "E:\My PC\00_WIP"
    ```
- Make sure you are in the correct directory by running the `pwd` command and check if the folder is empty `ls`.
    ```bash
    pwd
    ls
    ```
- Copy the link of the repository by clicking the code button and the :octicons-copy-16:copy icon
    ![github-clone-repo](/ai-applied-education/assets/images/11-github-fork-repository.jpg)
- Now clone the repository locally by running the following.
    ```bash
    git clone THE-COPIED-REPOSITORY-LINK
    ```
</div>

#### Add yourself to the students list

<div class="steps" markdown>
- Locate the file `ai-applied-education/docs/program/students.md`, and add your name to the markdown table **under the example**. (Make sure you copy the same structure)
    ```markdown
    | Name | Email | Github |
    | --- | --- | --- |
    | name | email | github-link |
    | María Jimeno | mjimeno@email.com | https://github.com/mjimeno |
    ```
- Save and close the file.
</div>


#### Commit & Push to remote repository

<div class="steps" markdown>
- Open the git bash console again and navigate to the root path of the repository.
    ```bash
    cd "E:\My PC\00_WIP\AiAppliedEducation"
    ```

- Add the changes by `git add` command.
    ```bash
    git add .
    ```
- Commit the changes to local git by `git commit` command. Make sure you add your name to the command.
    ```
    git commit -m "update: María student added"
    ```
- Push changes to remote repository.
    ```bash
    git push
    ```
</div>


#### Pull request to the official repository

Work in progress.