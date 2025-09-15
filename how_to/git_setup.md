---
title: Setting up Git for this Course
toc_sticky: true
---

I give you freedom in this course to set up your GitHub repository how you see fit.  I do, however, recommend that you use GitHub (or at least Git as a way to version control your code).

One way to organize your work in this class is to make a single top-level repository and then put individual assignment and project repositories below it.  Here is an example of how the sample solutions repository looks (after posting the day 4 solution).

```
├── Class01 (note: this is a project)
│   ├── .idea
│   │   ├── .gitignore
│   │   ├── encodings.xml
│   │   ├── kotlinc.xml
│   │   ├── misc.xml
│   │   └── vcs.xml
│   ├── src
│   │   ├── main
│   │   │   └── kotlin
│   │   │       └── Main.kt
│   │   └── test
│   │       └── kotlin
│   │           └── FindPeakTest.kt
│   ├── .gitignore
│   └── pom.xml
├── Class04 (note: this is a project, separate from Class01)
│   ├── .idea
│   │   ├── .gitignore
│   │   ├── encodings.xml
│   │   ├── kotlinc.xml
│   │   ├── misc.xml
│   │   └── vcs.xml
│   ├── src
│   │   ├── main
│   │   │   └── kotlin
│   │   │       ├── Main.kt
│   │   │       └── Stack.kt
│   │   └── test
│   │       └── kotlin
│   │           └── MyStackTest.kt
│   ├── .gitignore
│   └── pom.xml
├── Class04Optional (note: this is a project, separate from Class04)
│   ├── .idea
│   │   ├── .gitignore
│   │   ├── encodings.xml
│   │   ├── kotlinc.xml
│   │   ├── misc.xml
│   │   └── vcs.xml
│   ├── src
│   │   └── main
│   │       └── kotlin
│   │           ├── Main.kt
│   │           └── MutableStringList.kt
│   ├── .gitignore
│   └── pom.xml
```

## Steps to Achieve the Setup Above

1. Make sure you have git set up properly on your computer (meaning you can run git at a terminal, and it responds with some output)
2. Make sure you can clone your repos from GitHub with write permissions (e.g., by adding an ssh key to your account and to your machine)
3. Create a repo on GitHub for your class work.  You can initialize it with a README file.
4. Clone your repo on your machine with write access (e.g., using ssh).
5. When you create a new project, select the directory for your cloned repo as the root and give the project a name (this will become a subdirectory inside your repository). Make sure you uncheck the ``Create Git Repository`` checkbox (since the git repository is already associated with teh top-level directory)
6. Use git add, git commit, and git push as normal (these can also be done through the IntelliJ user interface).

