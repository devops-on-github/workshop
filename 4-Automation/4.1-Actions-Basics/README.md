# GitHub Actions Basics

[GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions) is a continuous integration and continuous delivery (CI/CD) platform that allows you to automate your build, test, and deployment pipeline. You can create workflows that build and test every pull request to your repository, or deploy merged pull requests to production.

GitHub Actions goes beyond just DevOps and lets you run workflows when other events happen in your repository. For example, you can run a workflow to automatically add the appropriate labels whenever someone creates a new issue in your repository.

GitHub provides Linux, Windows, and macOS virtual machines to run your workflows, or you can host your own self-hosted runners in your own data center or cloud infrastructure.

## Actions Components

You can configure a GitHub Actions **workflow** to be triggered when an **event** occurs in your repository, such as a pull request being opened or an issue being created. Your workflow contains one or more **jobs** which can run in sequential order or in parallel. Each job will run inside its own virtual machine **runner**, or inside a container, and has one or more steps that either **run** a script that you define or run an **action**, which is a reusable extension that can simplify your workflow.

![Workflow structure](../../images/actions-simple-overview.png)

## Creating a workflow

GitHub Actions uses YAML syntax to define the workflow. Each workflow is stored as a separate YAML file in your code repository, in a directory named `.github/workflows`. The [workflow syntax definition](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions) is _large_ and we won't cover all of it in this workshop (we'd need weeks to do it justice!).

### 👩‍💻 Guided Exercise 1

[▶️ Create a workflow](exercise-1.md)

In this guided exercise, we'll create a workflow from a template, watch it run, then examine it in detail.

Note that this exercise is a guided exercise mainly so we can examine what you'll see at various stages and ask questions. There's a lot to GitHub Actions and we want to make sure everyone is on the same page as we go!

## Runners

Runners are the machines that execute jobs in a GitHub Actions workflow. For example, a runner can clone your repository locally, install testing software, and then run commands that evaluate your code.

GitHub provides runners that you can use to run your jobs, or you can host your own runners. Each GitHub-hosted runner is a new virtual machine (VM) hosted by GitHub with the runner application [and other tools](https://docs.github.com/en/actions/using-github-hosted-runners/about-github-hosted-runners#supported-software) preinstalled, and is available with Ubuntu Linux, Windows, or macOS operating systems. When you use a GitHub-hosted runner, machine maintenance and upgrades are taken care of for you.

[Self-hosted runners](https://docs.github.com/en/actions/hosting-your-own-runners/about-self-hosted-runners) offer more control of hardware, operating system, and software tools than GitHub-hosted runners provide. With self-hosted runners, you can create custom hardware configurations that meet your needs with processing power or memory to run larger jobs, install software available on your local network, and choose an operating system not offered by GitHub-hosted runners. Self-hosted runners can be physical, virtual, in a container, on-premises, or in a cloud.

### Service Containers

If you need additional services running, you can use [service containers](https://docs.github.com/en/actions/using-containerized-services/about-service-containers) to connect databases, web services, memory caches, and other tools to your workflow. You can configure service containers for each job in a workflow. GitHub creates a fresh Docker container for each service configured in the workflow, and destroys the service container when the job completes.

## Secrets

Often, you'll need to use sensitive information during a workflow such as cloud credentials or API keys. While you could include them in configuration files in the repository, doing so presents a security risk and should be avoided.

To avoid this, GitHub lets you store [Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets). Secrets are encrypted environment variables that you create in an organization, repository, or repository environment. The secrets that you create are available to use in GitHub Actions workflows. Secrets are stored and used such that they're encrypted before they reach GitHub and remain encrypted until you use them in a workflow. During a workflow run, secrets are masked in the logs.

## Dependent Jobs

One feature core to effective CI/CD is dependent jobs. You can use the `needs` keyword to set dependencies between jobs so that one must finish prior to the other starting. By default, jobs will run concurrently (within concurrency limits), so having this control allows you to pass information between different phases of your workflow.

## Environments

When deploying with GitHub Actions, another useful feature is [Environments](https://docs.github.com/en/actions/deployment/about-deployments/deploying-with-github-actions#using-environments).

Environments are used to describe a general deployment target like production, staging, or development. You can use environments to require approval for a job to proceed, restrict which branches can trigger a workflow, or limit access to secrets.

We'll talk about Environments in more detail in the [Sofware Delivery](../4.3-Software-Delivery-CICD/) section.

## Putting it all together

### 👩‍💻 Exercise 2

[▶️ What we've learned so far](exercise-2.md)

Using what we've learned so far, we're going to modify the definition from exercise 1 to perform a multi-phase workflow to try out some of these ideas.

## Resources:
- [Understanding GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)
- [GitHub Actions Workflow Syntax](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)
- [GitHub-hosted runner definitions](https://docs.github.com/en/actions/using-github-hosted-runners/about-github-hosted-runners#supported-runners-and-hardware-resources)
- [Encrypted Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)