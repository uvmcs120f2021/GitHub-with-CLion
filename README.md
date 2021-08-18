# GitHub with CLion
We will be using GitHub for all of the Guided Projects, Open-Ended Projects, and the Final Project this semester. You should bookmark the organization page on your preferred web browser: [https://github.com/uvmcs120f2021](https://github.com/uvmcs120f2021)

GitHub stores a master copy of your project files, which you will be able to edit, add to, remove from, and track the history. It's kind of like Google Docs for code.

# Typical Files in a GitHub Repository
There are certain files that most GitHub repositories have:
* README.md is the file that opens automatically under the list of files on a repository page (like the one you're reading right now!). It uses markdown (which is what the .md file extenstion stands for) to write a description of the project, any installation instructions, or in the case of Guided Projects, directions to follow.
    * This file will be provided for you in Guided Projects, but you may need to edit it to answer questions.
    * You will need to create and populate this file for Open-Ended Projects and the Final Project.
    * The first time you open a README.md file in CLion, it will suggest you install a CLion markdown extension. I recommend it.
* .gitignore specifies all of the files and folders that exist in your project folder on your machine and which should not be in the GitHub repository. For the purposes of this course, this will include the folders that CLion creates to compile and run the project and store your IDE settings:
    ```asm
    cmake-build-debug/
    .idea/
    ```
  These two lines in the .gitignore file are very important, especially once you start collaborating on projects. This file will be provided for you in Guided Projects, but you will need to create it for Open-Ended Projects and your Final Project.
* Source files (those with .cpp and .h extensions) are needed to run the project.
* In a larger project, you may have enough files to create folders for organization. For example, you may want a folder for all of your source files, one for images, and one for input and/or output data files.

# Creating a repository for a Guided Project
* From the Guided Project GitHub page, click the green "Use this template" button.
    * Alternatively, from the organization page ([https://github.com/uvmcs120f2021](https://github.com/uvmcs120f2021)), click the green "New" button and choose the appropriate Guided Project from the "Repository template" dropdown.
* The owner defaults to the organization. Do NOT change it.
* Choose a repository name, keeping with the required format in the Guided Project directions.
* You can optionally provide a description for the project. This is what shows up when the repositories are listed in the organization. You can also edit/complete it later.
* The repository defaults to private. Do NOT change it.
* There is a checkbox to include all branches. This shouldn't matter, because Guided Projects will typically only have a master branch.
* Click the green "Create repository from template" button.
* Now follow the directions below to clone the repo into CLion.

# Creating a repository for an Open-Ended Project
* Go to the organization page on GitHub: [https://github.com/uvmcs120f2021](https://github.com/uvmcs120f2021)
* Click the green "New" button.
* The repository template defaults to "No template". Do NOT change it.
* The owner defaults to the organization. Do NOT change it.
* Choose a repository name, keeping with the required format in the Open-Ended Project directions.
* You can optionally provide a description for the project. This is what shows up when the repositories are listed in the organization. You can also edit/complete it later.
* The repository defaults to private. Do NOT change it.
* You can check the box to create a README file if you want. It will create a README.md file with the name of the repository and the description.
* There is a checkbox to add a .gitignore file. I do NOT recommend this. CLion has a setup different from other C++ projects, so I suggest you create your own .gitignore file once the repository exists.
* There is a checkbox to add a license. I do NOT recommend this.
* Click the green "Create repository" button.
* Now follow the directions below to clone the repo into CLion.

# Access token
GitHub now requires access tokens (instead of passwords) for command line and third party use. This is something you will need to do once at the beginning of the semester.
## Create an access token
Following the directions through this GitHub webpage to [create a personal access token](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token)
* Set the expiration to at least 90 days (so that it lasts the entire semester).
* When selecting the permissions, check the options for `repo` and `delete_repo`.

## Saving the access token
If you have your github username and password saved on your keychain (or would like to), make sure you copy the token once you have created it and use that as the password.

## Connecting CLion to your GitHub account
In CLion, you will want to go to File -> Settings (Windows) or CLion -> Preferences (Mac), then choose Version Control and GitHub and add your GitHub account. It will pop up with an option to log in on the website, I recommend choosing that link.

# Clone a GitHub repository into CLion*
* Click the green "⤓ Code" button from the GitHub repository page and copy the HTTPS link.
    * Note that if the repository is empty, there will not be a green button and the HTTPS link will already be visible.
* You may need to install [Git](https://git-scm.com/downloads) on your machine (you should only have to do this once at the beginning of the semester).
* Now switch to CLion:
    * If you already have a project open in CLion, go to VCS -> Get from Version Control...
    * If you do not already have a project open in CLion, choose Get from Version Control from the main menu.
* In the window that pops up, choose Git from the dropdown menu.
* Paste the link from GitHub in the URL textbox.
* The Directory textbox is where CLion will create a folder for the project. Change it if the default directory is not where you want it.
* Click Clone.
    * You may be prompted to enter your GitHub username and password.
* It will ask you if you want to open the directory. Choose yes.
    * If you already have a project open in CLion, it will ask you if you want to open the project in a new window or this window. This choice is up to you.

\* Note that if you are comfortable cloning a repository via command line, you can do so. If you want to use CLion afterwards, choose "New CMake Project from Sources" and follow the directions.

# Mantra
* Work on the project. Add/modify files.
* When you finish a task, commit it and push it to the repository:
    * Click on one of the modified files in the left pane.
    * Choose VCS -> Git -> Commit.
    * Check all files that were added/changed in this commit.
    * Write commit message (something useful and not vulgar).
    * Click the arrow in the "Commit" button and choose "Commit and Push".
        * Alternatively, click Commit, then go to VCS -> Git -> Push.
    * Click "Push".
    * Wait for confirmation to appear in the lower right corner of CLion.
        * Once this happens, you can refresh the GitHub repository to see your changes.
    
# CLion colors
CLion colors the text of the file names according to their git status:
* Black (in light mode, white in dark mode) means the local file matches the one in the repository.
* Red means the file exists locally but is not tracked by Git.
* Green means the file is new and is ready to be pushed to the repository.
* Blue means the local file is different from the version in the repository (i.e. you made changes to the file that can be committed and pushed to the repository).
* Yellow means the file is in .gitignore.
