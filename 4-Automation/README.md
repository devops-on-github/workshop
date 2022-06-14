# Automation

Often when people talk about DevOps, they're talking about CI/CD - Continuous Integration and Continuous Delivery/Deployment.

As we've discussed, DevOps is much more than just CI/CD, but effective automation is an important part of successful DevOps - arguably the most important (technical) part.

GitHub's solution for automation is [GitHub Actions](https://github.com/features/actions), and it's an extremely flexible and powerful tool, going far beyond simple CI/CD. GitHub Actions makes it easy to automate all your software workflows. You can build, test, and deploy your code right from GitHub, but you can also make code reviews, branch management, and issue triaging work the way you want.

In this section we're going to explore GitHub Actions in depth. We'll look at how to use it in terms of the syntax and features, but more importantly we'll look at how you _should_ use it for CI/CD and non-CI/CD automations.

## 🛖 Actions Basics
GitHub Actions is extremely customizable, but there are fundamentals that are important to know. From the structure of a workflow definition to managing secrets, to understanding the way runners work, these fundamentals are where we'll start.

[➡️ Go to Actions Basics Content](4.1-Actions-Basics/)

## 🏢 Actions Advanced
Once you understand the fundamentals, you'll be able to see how GitHub Actions can perform nearly _any_ task in response to _any_ trigger. The possibilities are endless. But to effectively make use of these possibilities, we have to go deeper.

In this section we'll look at ways to work with context-specific information to control workflow behaviour. We'll look at saving artifacts and passing variables around as well as reusability.

[➡️ Go to Actions Advanced Content](4.2-Actions-Advanced/)

## 🚀 Software Delivery and CI/CD with Actions
Understanding how to perform tasks with GitHub Actions is one thing, but it's important to be automating the _right_ patterns. In this section we'll talk about how you _should_ use GitHub Actions for your CI/CD workflows.

We'll implement some practical CI/CD, and use Actions for pull request checks.

Note that due to complexities and costs around cloud services, we won't actually be deploying our code (officially). That said, there will be plenty of opportunity to ask questions about how to do your own deployments if you have cloud services configured.

[➡️ Go to Sofware Delivery Content](4.3-Software-Delivery-CICD/)

## 🎪 Non-CI/CD Actions
GitHub Actions is not just for CI/CD. As we discussed, automations can be configured for any number of triggers, and can perform a limitless set of tasks.

In this section, we'll take a brief look at some scenarios that GitHub Actions can help with.

[➡️ Go to Non-CI/CD Actions Content](4.4-Non-CICD/)