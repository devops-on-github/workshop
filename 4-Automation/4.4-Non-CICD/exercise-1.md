# Exercise 1 - Add issues to our project

In this exercise, we'll set up some automation to automatically add any new Issue to our project.

When you add a new issue to a repository, your project board won't automatically have that issue added.

_Note: This exercise is self-driven. You should be able to piece together what's required!_

1. Create a new workflow file called `add-issue.yml`
2. The workflow should be triggered when a new issue is created in your repository.
3. Use the [`Add to GitHub Projects Beta`](https://github.com/marketplace/actions/add-to-github-projects-beta) action to add the new issue to the project you created on day 1.
4. Once you've saved the workflow, create a new issue and verify it works!

## Notes:

Make sure you read the documentation for this action! You'll need to create a personal access token and you can find the instructions in links in the action description.

Also remember you have branch protection on, so to add a workflow you'll need to use a pull request!