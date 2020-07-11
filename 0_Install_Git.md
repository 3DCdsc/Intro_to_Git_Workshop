# Intro to Git & GitHub Workshop
---
## Lesson 0 - Workshop Preparation: Git Installation

### For Windows User

- You will need to install [**Git Bash for Windows**](https://git-scm.com/download/win).
- Just follow the installation instructions and choose the default settings.

### For macOS User

- Open **Terminal** app on your macOS, use **Spotlight** to search for it if you can't find it from **Launchpad**.
- Just copy and paste the following command in your **terminal**, then hit `enter` key, to check your `git` version, it will prompt you to install `Git` if you don't have it.

    ```bash
    git --version
    ```

### For Linux (Ubuntu/Debian) User

- Check `Git` Installation
    ```bash
    git --version
    ```
- If it is not already installed, use the following command in shell / terminal
    ```bash
    sudo apt install git-all
    ```

### For Linux (Fedora) User

- Check `Git` Installation
    ```bash
    git --version
    ```
- If it is not already installed, use the following command in shell / terminal
    ```bash
    sudo yum install git
    ```


## Configure Git

>From now onwards, the commands used in this workshop will be done in a terminal window (Windows: Git Bash, macOS: Terminal or whatever shell, Linux: Bash or whatever shell)

#### Setting up Git username and email address
Just letting `Git` know who you are. If you already have a `GitHub` account, keep the email address for your `Git` at local same as your `GitHub` email address.

- To check current username and email address for Git.
- It returns nothing if no name/email has been set.

```
git config --global user.name
git config --global user.email

```

- To set username and email address for Git.
- `--global` means to set for all the repositories on your machine.
- If you only want to set for a single repository, do it without the `--global` flag.

```
git config --global user.name "Tom Cruise"
git config --global user.email "tom@example.com"

```

---

Reference:
 - [Getting Started - Installing Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
