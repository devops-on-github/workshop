# The Inner Loop

DevOps is about the whole end-to-end lifecycle from an idea through to production. That includes actually writing the code, debugging, and running tests.

Often, discussions of DevOps concentrate on the "outer" loop - the larger team processes that take your committed code into production. But the inner loop is just as important! Gene Kim's first "way" of DevOps talks about systems thinking - considering every part of the system when it comes to software delivery - not just the outer loop.

Writing the code should be as efficient a process as possible, and while solving the core problem is the domain of the coder/engineer/programmer, the tools and practices that expert wields need to be efficient and effective.

That's what this section of the workshop is about. Tools to help your team with that inner loop.

GitHub has two related features that enable you to code in the cloud. They are the web-based editor, and Codespaces. Both are built upon Visual Studio Code to give you a powerful editor without needing a powerful machine.

_Fun Fact: This entire workshop was built with the web-based editor and Codespaces. The author doesn't even have a local clone of the repository!_

## 🕸️ The Web-Based Editor

The [GitHub.dev web-based editor](https://docs.github.com/en/codespaces/the-githubdev-web-based-editor) is a free, always-available editor for repositories that runs entirely in your browser. It's easy to access and integrates closely with GitHub. It's a great way to make simple changes that don't need compiling or debugging (for example a set of markdown files for a workshop!). It's also great for working with pull requests.

[➡️ Go to the Web-Based Editor content](3.1-Web-Editor/)

## 👩‍💻 Codespaces

[GitHub Codespaces]() takes this idea further, giving you Visual Studio Code backed by high performance VMs that start in seconds. Unlike the web-based editor, Codespaces are backed by VMs so you can compile and debug as if you were on a local machine.

The advantages of using Codespaces over local development are many. You can standardize on a set of dependencies for a project, onboard a new developer in seconds rather than days, and spin up and tear down context-aware Codespaces at a moment's notice.

_Fun Fact: GitHub itself uses Codespaces to develop GitHub! New engineers can go from zero to ready to code in about 10 seconds. And that's on an 11GB codebase!_

[➡️ Go to Codespaces content](3.2-Codespaces/)