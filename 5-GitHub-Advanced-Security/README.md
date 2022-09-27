# GitHub Advanced Security

[GitHub Advanced Security](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security) is a set of extra security features available to customers under an Advanced Security license. **These features are also enabled for public repositories on GitHub.com.**

Some of these features are included in all plans, such as the dependency graph and Dependabot alerts.

_Note: In this workshop, we're using a GitHub Enterprise account with Advanced Security licenses._

In this workshop we'll look three of these features.

## Dependabot

[Dependabot](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/about-dependabot-alerts) is a tool that alerts you to known security vulnerabilities in dependencies in your code. For example, if you're using a specific version of an npm package that's known to have a vulnerability, dependabot can alert you. 

It can even go further and submit pull requests to upgrade those dependencies. Or if you like, it can continuously submit pull requests to upgrade dependencies whether there's a known vulnerability or not!

### 👩‍💻 Exercise 1

[▶️ Turn on Dependabot](exercise-1.md)

In this exercise we'll turn on Dependabot and examine the results for our repository.

## Code Scanning with CodeQL

[Code scanning](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning) is a feature that you use to analyze the code in a GitHub repository to find security vulnerabilities and coding errors. Any problems identified by the analysis are shown in GitHub.

You can use code scanning to find, triage, and prioritize fixes for existing problems in your code. Code scanning also prevents developers from introducing new problems. You can schedule scans for specific days and times, or trigger scans when a specific event occurs in the repository, such as a push.

You can set up code scanning to use the CodeQL product maintained by GitHub or a third-party code scanning tool that supports the [SARIF output format](https://docs.github.com/en/github/finding-security-vulnerabilities-and-errors-in-your-code/sarif-support-for-code-scanning).

Code scanning is configured and runs using GitHub Actions. That means you can control when your code scanning runs and under what conditions.

## Secret Scanning

If your project communicates with an external service, you might use a token or private key for authentication. Tokens and private keys are examples of secrets that a service provider can issue. If you check a secret into a repository, anyone who has read access to the repository can use the secret to access the external service with your privileges. We recommend that you store secrets in a dedicated, secure location outside of the repository for your project.

[Secret scanning](https://docs.github.com/en/code-security/secret-scanning/about-secret-scanning) will scan your entire Git history on all branches present in your GitHub repository for secrets.

For public repositories, secret scanning looks for strings that match patterns that were provided by secret scanning partners are reported directly to the relevant partner. That may allow the partner to invalidate the token immediately which can be incredibly helpful!

If you have GitHub Advanced Security, you can enable and configure additional scanning for repositories owned by the organization. Any strings that match patterns provided by secret scanning partners, by other service providers, or defined by your organization, are reported as alerts in the "Security" tab of repositories. If a string in a public repository matches a partner pattern, it is also reported to the partner.

## Security Overview

The results of any of these security features can be found in the [`Security Overview`](https://docs.github.com/en/code-security/security-overview/about-the-security-overview) on the `Security` tab of your repository, organization, or team - scoped appropriately.
