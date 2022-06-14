# Actions Advanced

As the trainer has no doubt mentioned several times - there is a **LOT** in GitHub Actions.

In this section we're going to go a bit deeper and examine some of the features and capabilities you're likely to find useful in your own projects. We won't cover everything, but we will try to hit the highlights.

_Note: There are a lot of links to documentation in this section. You can read through them during this workshop or when you have more time._

## Contexts

We got a taste of contexts in the Actions Basics section, using both the `secrets` context and the `matrix` context.

In short, [contexts](https://docs.github.com/en/actions/learn-github-actions/contexts) are a way to access information about workflow runs, runner environments, jobs, and steps. Each context is an object that contains properties, which can be strings or other objects.

Contexts, objects, and properties will vary significantly under different workflow run conditions. For example, the matrix context is only populated for jobs in a matrix.

You can access contexts using the expression syntax.

## Expressions

Which brings us to [expressions](https://docs.github.com/en/actions/learn-github-actions/expressions)!

You can use expressions to programmatically set environment variables in workflow files and access contexts. An expression can be any combination of literal values, references to a context, or functions. You can combine literals, context references, and functions using operators.

## Reusable workflows

Rather than copying and pasting from one workflow to another, [you can make workflows reusable](https://docs.github.com/en/actions/using-workflows/reusing-workflows). You and anyone with access to the reusable workflow can then call the reusable workflow from another workflow.

Reusing workflows avoids duplication. This makes workflows easier to maintain and allows you to create new workflows more quickly by building on the work of others, just as you do with actions. Workflow reuse also promotes best practice by helping you to use workflows that are well designed, have already been tested, and have been proved to be effective. Your organization can build up a library of reusable workflows that can be centrally maintained.

A reusable workflow can be used by another workflow if either of the following is true:
- Both workflows are in the same repository.
- The called workflow is stored in a public repository, and your organization allows you to use public reusable workflows.

## Passing information and artifacts

There are four main ways to pass information, dependent on where you're trying to pass it to. The links below take you to documentation with explanations and examples:

- To [pass values between steps within a job](https://docs.github.com/en/actions/learn-github-actions/environment-variables#passing-values-between-steps-and-jobs-in-a-workflow), you can just set an environment variable.
- To pass values between jobs, you'll need to use [output variables](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idoutputs).
- To [pass values to a reusable workflow](https://docs.github.com/en/actions/using-workflows/reusing-workflows#passing-inputs-and-secrets-to-a-reusable-workflow), you'll need to use the `with` and `secrets` keywords when calling it. In the reusable workflow, use the `inputs` and `secrets` keywords to define inputs or secrets that will be passed from the caller.
- To store outputs and workflow data from jobs, [you can use artifacts](https://docs.github.com/en/actions/using-workflows/storing-workflow-data-as-artifacts). The `actions/upload-artifact` and `actions/download-artifact` let you upload and download artifacts from within jobs.

## Let's try some things!

### 👩‍💻 Exercise 1

[▶️ Explore some advanced Actions](exercise-1.md)

In this exercise, we'll try out some of the techniques and capabilities listed above. We'll use contexts, expressions, and some methods to pass data around.

## Permissions

At the start of each workflow run, GitHub automatically creates a unique [GITHUB_TOKEN secret](https://docs.github.com/en/actions/security-guides/automatic-token-authentication#about-the-github_token-secret) to use in your workflow. You can use the GITHUB_TOKEN to authenticate in a workflow run.

You can [change the permissions for a job](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idpermissions) or [for a whole workflow](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#permissions).

## Writing your own Actions

You can [create your own custom actions](https://docs.github.com/en/actions/creating-actions/about-custom-actions) by writing custom code that interacts with your repository in any way you'd like, including integrating with GitHub's APIs and any publicly available third-party API. For example, an action can publish npm modules, send SMS alerts when urgent issues are created, or deploy production-ready code.

You can write your own actions to use in your workflow or share the actions you build with the GitHub community. To share actions you've built with everyone, your repository must be public.

Actions can run directly on a machine or in a Docker container. You can define an action's inputs, outputs, and environment variables.

All actions in the GitHub Marketplace (over 13,600 at time of writing) [must be in a public repository](https://docs.github.com/en/actions/creating-actions/publishing-actions-in-github-marketplace). This means there are plenty of examples on how to put them together. Just find the repo and explore the code!