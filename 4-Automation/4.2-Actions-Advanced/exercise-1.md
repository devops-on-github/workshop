# Exercise 1 - Explore some Advanced Actions

_Note: This is a self-driven exercise, but don't be afraid to ask for help. The documentation for Actions is comprehensive, but it can sometimes be hard to find exactly what you need._

_Further note: This exercise is deliberately tricky (the author needed about 8 attempts!) I'd encourage you to try it yourself, but if you get stuck or just want the answer, the completed workflow is [here](advanced-actions.yml)_

1. Create a new workflow for your repository
2. Set the workflow to only run on `workflow_dispatch` ([learn about it here](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#workflow_dispatch))
3. This workflow should have 3 jobs:

## Job 1 - what's our runner?:
Job 1 should echo a json output of the `runner` context.

[See this doc for a _big_ hint!](https://docs.github.com/en/actions/learn-github-actions/contexts#example-printing-context-information-to-the-log)

This is an extremely useful technique for debugging!

## Job 2 - output the GitHub username of the person who triggered the run: 
Job 2 should set an output variable to the GitHub username of the person who triggered the run

You can get this detail from [the `github` context](https://docs.github.com/en/actions/learn-github-actions/contexts#github-context) - `github.triggering_actor`.

[See docs on output variables](https://docs.github.com/en/actions/using-jobs/defining-outputs-for-jobs) for help.

## Job 3 - conditional running and artifacts:
Job 3 should only run if the run attempt is greater than 1.

If it runs, it should write the username of the person who triggered the run to a file and upload it as an artifact.

You can write text to a file in bash using:

```bash
echo "some text" > artifact.txt
```

4. When you're done, run the workflow!