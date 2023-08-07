# Requirements

In order to fully engage with the course material and complete the exercises, it is essential to have the necessary software installed on your system. Follow these step-by-step tutorials, to ensure you have the foundation to succeed in the course.

The required tools encompass:

:simple-github: **GitHub account**  
:simple-google: **Google Colab**  
:simple-anaconda: **Anaconda distribution **  
:simple-visualstudiocode: **Visual Studio Code (optionally)**

!!! danger ":octicons-markdown-16: **Markdown knowledge is required**"

    Markdown knowledge is essential for the program. While not covered in the course, it's vital for creating clear documentation. Please refer to the [Markdown cheatsheet](https://www.markdownguide.org/cheat-sheet/) to learn the basics.


## :simple-github: Github 

<div class="highlighted" markdown>
**GitHub is a platform that helps you colaborate and work on projects. It's like a digital space where people can store, share, and manage their code and project files.**
</div>

GitHub allows you to create repositories (folders) to store your projects. Each repository contains all the files, code, and resources related to a specific project. It's a great place to keep track of your work and colaborate with others.

### 1.1 Create an account

To create a github account go to [Github.com](www.github.com), and press `Sign up`.

![github-sign-up](/ai-applied-education\assets\images\requirements-github-sign-up.jpg)

### 1.2 Create a profile README repository

A repository in GitHub is like a digital folder where you can store and manage your projects, including code, files, and resources. It's a space to colaborate, keep track of changes, and showcase your work. To create a repository you can follow [the official documentation](https://docs.github.com/es/get-started/quickstart/create-a-repo).

The profile README is a [github-profile-readme](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/customizing-your-profile/managing-your-profile-readme)

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

## :simple-google: Google colab

<div class="highlighted" markdown>
Google Colab is an online platform that allows you to write and execute Python code in a colaborative and interactive environment.
</div>

It's especially useful for data analysis, machine learning, and research projects. You can create and share notebooks that contain code, text, images, and more.

!!! info "Gmail account"
    To use Google Colab, **you need a Google account** (such as a Gmail account). You can access Colab through a web browser without any installation. It provides a virtual machine with necessary libraries pre-installed, eliminating the need for local setup.


### 2.1 Create a new notebook

<div class="steps" markdown>
- **Create a New Notebook:** Click [here](https://colab.research.google.com/?hl=es#create=true) to create a new notebook and start coding.

- **Connect the Notebook:** A new notebook will be created with an empty code cell. Make sure you connect the notebook to a running environment. You can start running the code once you have a machine assigned.  
    ![colab-connect](/ai-applied-education\assets\images\requirements-colab-connect.jpg)

- **Adding Code:** You can add code cells by clicking the "+ Code" button above the notebook or pressing the "+ Code" option in the "Insert" menu.

- **Adding Text:** You can add text cells by clicking the "+ Text" button above the notebook or pressing the "+ Text" option in the "Insert" menu. Text cells allow you to add explanations, notes, and Markdown-formatted text.

- **Running Code:** To run a code cell, click the play button ("Run") next to the cell, or press Shift + Enter. The output of the code will be displayed below the cell.

- **Saving and Renaming:** Your notebook will be automatically saved to your Google Drive. To rename the notebook, click on the notebook name at the top-left corner and provide a new name.

- **Sharing and colaboration:** You can share the notebook with others by clicking the "Share" button at the top-right corner. You can provide view or edit access, and others can colaborate in real-time.

- **Closing and Exiting:** When you're done working on the notebook, you can close the browser tab or go to "File" > "Close" to close the notebook.

</div>

### 2.2 Access to a github repository

<div class="steps" markdown>
- **Open Google Colab:** Go to the Google [Colab website](https://colab.research.google.com/?hl=es)  .

- **Choose GitHub Tab:** Click on the "GitHub" tab on the "Welcome to Colaboratory" screen.

    ![colab-connect](/ai-applied-education\assets\images\requirements-colab-connect.jpg)

- **Enter Repository URL:**
In the "Enter a GitHub URL or search by organization or user" field, paste the URL of the GitHub repository that contains the notebook you want to open.

- **Search and Select Notebook:** Google Colab will display a list of notebooks available in the repository. Search for the notebook you want to open and click on it.

- **Open the Notebook:** The selected notebook will be opened in Google Colab. You can now view, edit, and run the notebook as needed.

- **Connect to a Runtime:** If necessary, connect the notebook to a runtime by clicking the "Connect" button at the top-right corner of the notebook. This will allow you to run the code cells.

- **Run and Modify Code:** You can now run code cells, modify the notebook, and work on the content as if it were a regular Google Colab notebook.

- **Save to Drive:** Any changes you make to the notebook will be saved to your Google Drive.

</div>


## :simple-anaconda: Anaconda distribution

<div class="highlighted" markdown>
Anaconda is a platform that simplifies Python programming by providing tools and libraries for data science, analysis, and coding tasks.
</div>

*You can follow the official instructions at [Anaconda documentation](https://docs.anaconda.com/free/anaconda/install/windows/).*

<div class="steps" markdown>
- **Download Anaconda:** go to the [Anaconda website](https://www.anaconda.com/). Click on the "Download" for windows button.

- **Run Installer:** locate the downloaded installer file (usually named something like "Anaconda3-2023.07-1-Windows-x86_64.exe") and double-click on it to run the installer.

- **Setup Wizard:** follow the prompts in the setup wizard. You can leave most of the default settings as they are. However, make sure to **check the box that says "Add Anaconda to my PATH environment variable."** This will allow you to use Anaconda from the command line.

- **Install Anaconda:** click the "Install" button to start the installation process. The installer will copy files to your computer.

- **Start Anaconda Navigator:** after the installation, you can start Anaconda Navigator by clicking the "Next" button on the completion screen. This will open the Anaconda Navigator app, which provides a graphical interface for managing environments and packages.

- **Start Using Anaconda:** you're now ready to start using Anaconda. You can open Anaconda Navigator to manage environments, launch Jupyter notebooks, and install packages.
</div>

Congratulations! You've successfully installed Anaconda on your Windows computer. 


## :simple-visualstudiocode: VS Code (Optional)

<div class="highlighted" markdown>
Visual Studio Code is a free code editor developed by Microsoft. It's widely used for coding and programming tasks.
</div>

<div class="steps" markdown>
- **Download VS Code:** go to the [Visual Studio Code website](https://code.visualstudio.com/download). Click on the "Download for Windows" button.

- **Run Installer:** locate the downloaded installer file (usually named something like "VSCodeSetup.exe") and double-click on it to run the installer.

- **Choose Additional Tasks:** during the installation, you'll be prompted to choose additional tasks. You can choose to associate file types with VS Code, create a desktop icon, and more.

- **Start VS Code:** after the installation, you can start Visual Studio Code by clicking the "Start" button on your Windows taskbar and searching for "Visual Studio Code" in the search bar. Click on the application to launch it.

- **Start Coding:** you're now ready to start coding with Visual Studio Code. You can open files, create new projects, and install extensions to enhance your coding experience.

</div>

Congratulations! You've successfully installed Visual Studio Code on your Windows computer.
