# Non-CI/CD Actions

The blurb on the [feature page for GitHub Actions](https://github.com/features/actions) highlights that it's for all your software workflows. While there's an emphasis on CI/CD, it also points at Actions for managing code reviews, branch management, and issue triaging.

The message is - GitHub Actions is great for non-CI/CD tasks as well. Your workflows can automate almost anything (as we've seen) in response to almost anything.

To understand why, you just need to look at all the [events that trigger workflows](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows).

You'll see events for nearly anything that happens in GitHub, but there are two event triggers that expand the limits - [`workflow_dispatch`](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#workflow_dispatch) and [`repository_dispatch`](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#repository_dispatch)

By adding the **Workflow Dispatch** trigger, you'll be able to manually start a workflow run. You can even include typed inputs that are required to start.

The **Repository Dispatch** is the same thing, but accessible via an HTTP endpoint. That means any external tool can fire off a workflow run provided it can hit a URL.

## Some useful possibilities

In practice, there are a number of scenarios where Actions can help. For example:
- Notifying the appropriate person or team when an Issue is created
- Performing a task when an comment with a specific command is added (like a bot)
- Ensuring all the correct information is present when someone submits a pull request
- Notifies a mailing list when you publish a new release

### 👩‍💻 Exercise 1

[▶️ Add new Issues to our project](exercise-1.md)

In this exercise, we'll set up some automation to automatically add any new Issue to our project.