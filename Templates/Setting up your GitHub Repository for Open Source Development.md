---
created: 2024-03-15T09:38:28 (UTC -05:00)
tags: []
source: https://getpocket.com/read/3755691939
author: 
---

# Pocket - Setting up your GitHub Repository for Open Source Development

> ## Excerpt
> Contributing to open source can be an awesome experience to help you learn, get job opportunities, network with people and also help others at the same time. Kent C. Dodds talks about how open source has been awesome to him here.

---
Contributing to open source can be an awesome experience to help you learn, get job opportunities, network with people and also help others at the same time. [Kent C. Dodds](https://twitter.com/kentcdodds?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) talks about how open source has been awesome to him [here](https://kentcdodds.com/blog/how-getting-into-open-source-has-been-awesome-for-me).

This article would provide tips for preparing your GitHub repository for open-source contributions.

> It is assumed that you have basic experience with markdown syntax to work with most of the files needed in this article.

## Tips and Tricks

### Creating your README

The `README.md` is the entry point to your project when people visit your repository. It should contain:

-   the description of the project.
-   why the project is useful.
-   how to get started.
-   relevant information on using the project etc.

> Most projects with short documentation would have the README. I’d recommend the same except the documentation is huge, you need to have it somewhere else that can support search, pagination etc.

### Writing your Contribution Guideline

To create a contribution guideline, create a `[CONTRIBUTING.md](http://CONTRIBUTING.md)` at the root of your project and provide information that is necessary for new and old contributors to contribute to your project.

It can include information like:

-   the different ways contributors can contribute to the project.
-   how contributors can clone the repository on their local machine.
-   how contributors can set up the code on their machine for development.
-   how contributors can report bugs.

### Defining the Code of Conduct

Working with people can be trivial in some cases. Open-source projects are not protected from people with abusive intent. Creating a code of conduct sets a foundation for creating a positive environment for people to contribute without disruption by negative behaviours like sexual harassment, abuse etc.

Create a `CODE_OF_CONDUCT.md` at the root of your project. Using markdown syntax, the file can contain information about:

-   the project community pledge,
-   the project community standards,
-   enforcement guidelines.

You can adapt the guidelines provided by [https://www.contributor-covenant.org/](https://www.contributor-covenant.org/) to create your guideline.

### Creating Status Checks

To enforce good development, you can include a form of status check each time a pull request is made to your project. Status check let you know if commits meet the conditions set for the repository. The checks can include continuous integration like:

-   units tests
-   code coverage
-   code quality checks like [DeepSource](https://deepsource.io/), [SonarCloud](https://sonarcloud.io/) etc.

[GitHub Actions](https://docs.github.com/en/actions) is recommended to trigger jobs or workflow by certain events on your repository.

### Protect your Main Branch

Using GitHub, you need to protect your main branch to enforce that certain requirements are met before pushing to the branch. Protecting the branch can also prevent deletion or force pushes to the branch.

To set up protection rules for the main/default branch, ensure you have admin access to the repository then click on **Settings** > **Branches** and click on **Add branch protection rule:**

![](Pocket%20-%20Setting%20up%20your%20GitHub%20Repository%20for%20Open%20Source%20Development/https%253A%252F%252Fcdn.hashnode.com%252Fres%252Fhashnode%252Fimage%252Fupload%252Fv1669736004199%252Fh37g4G6Wx.png%253Fauto%253Dcompress%252Cformat%2526format%253Dwebp)

Then you can configure or select the rules you want active:

![](Pocket%20-%20Setting%20up%20your%20GitHub%20Repository%20for%20Open%20Source%20Development/https%253A%252F%252Fcdn.hashnode.com%252Fres%252Fhashnode%252Fimage%252Fupload%252Fv1669736038562%252FO5AGpf1oW.png%253Fauto%253Dcompress%252Cformat%2526format%253Dwebp)

To read more about GitHub branch protection rules, you can visit [here](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches).

### Create Pull Request Templates

To set a foundation for code reviews, you can create a pull request template with sets of required information that you feel is necessary for code review.

To create the template, create a new directory, called `.github`, and create a new file in the directory called `PULL_REQUEST_TEMPLATE.md`.

A sample template could look like this:

```
<span>## Description</span>

Issue closed #(issue)

<span>## Change Type</span>

<span>&lt;!--- This is a comment, you can leave this to give information to the contributor --&gt;</span>

<span>-</span> [ ] Bug fix 
<span>-</span> [ ] New feature
<span>-</span> [ ] Breaking change
<span>-</span> [ ] Minor changes in old functionality

<span>## Checklist</span>

<span>-</span> [ ] My changes are well-tested and commented
<span>-</span> [ ] I reviewed my changes
<span>-</span> [ ] My changes generate no new warnings
```

### Make Use of GitHub Labels

You can utilize GitHub Labels to help create a standard workflow in a repository. You can use labels to categorize issues, pull requests and discussions. GitHub provides defaults labels with their description, some of which includes:

-   `bug`: indicates an unexpected problem or unintended behaviours.
-   `documentation`: indicates a need for improvements or additions to documentation.
-   `duplicate`: indicates similar issues, pull requests, or discussions.
-   `enhancement`: indicates a new feature request
-   `good first issue`: indicates a good issue for first-time contributors
-   `help wanted`: indicates that a maintainer wants help on an issue or a pull request. etc

To read more about GitHub Labels, you can visit this [documentation](https://docs.github.com/en/issues/using-labels-and-milestones-to-track-work/managing-labels).

### Create Templates for Issues

Once contributors start noticing and using your project, it is very likely for a number of issues to be created on your repository.

At the time of writing this article, Typescript has over 5000 issues in its repository.

![](Pocket%20-%20Setting%20up%20your%20GitHub%20Repository%20for%20Open%20Source%20Development/https%253A%252F%252Fcdn.hashnode.com%252Fres%252Fhashnode%252Fimage%252Fupload%252Fv1669736081974%252FRTU51zfiX.png%253Fauto%253Dcompress%252Cformat%2526format%253Dwebp)

Creating templates for issues is a great way to organize issues on your repository.

To create these templates, create a directory named, `ISSUE_TEMPLATE`, in the `.github` directory which is at the root of your project. Then create new markdown files directly to create separate templates.

I will create a sample feature request template in a file called `feature_template.md`:

```
<span><span>&lt;!-- .github/ISSUE_TEMPLATE/feature_template.md --&gt;</span>
---</span>
name: Feature Request
about: Suggest a new idea for this project
<span>labels: enhancement
---</span>

<span>&lt;!-- please fill each section completely --&gt;</span>
<span>## Viability Checklist</span>
<span>-</span> [ ] this wouldn't be breaking change in existing JavaScript
<span>-</span> [ ] this will not change the runtime environment
<span>-</span> [ ] this feature can be implemented with JavaScript

<span>## Suggestion</span>
<span>&lt;!-- A summary of what you are suggesting --&gt;</span>

<span>## Use Case</span>
<span>&lt;!-- How do you think this feature would be useful --&gt;</span>
```

## Conclusion

Open source is not restricted to writing codes alone. You can help with documentation, help share and talk about the project with your friends, help with product designs and many more. I hope this article is able to get some guidelines that can help you get started in your next open-source project.

I am currently building a newsletter to share informative articles and news, my progress in creating startups with little experience and how you can learn from my experience.

Please subscribe via this [link](https://open.substack.com/pub/zt4ff/p/coming-soon?r=8n8jt&utm_campaign=post&utm_medium=web).
