# Getting started with GitHub for startups

GitHub is the world's leading software development platform, supporting 90 million active global developers and 90% of the Fortune 100. To better support dynamic, early-stage startups like you that are growing on GitHub, we launched [GitHub for Startups(GFS)](https://startups.github.com). GFS includes friendly-pricing for our highest tier platform offering, GitHub Enterprise, in addition to other educational and community benefits. So you’re equipped with the tools and resources to scale from launch through IPO.

But having access to enterprise-grade tools is only helpful if you know what's available, how to use everything, and where to get started. This workshop is focused on guiding you through the initial onboarding process. We'll explore [DevOps](https://resources.github.com/devops/), from project management to managing code and pull requests to automation and [CI/CD](https://resources.github.com/ci-cd/).

## Prerequisites

We built this workshop to help startups onboard with GitHub and provide a guide for the first steps into the DevOps journey. As a result, we worked to minimize the amount of prerequisite knowledge. It will help if you are familiar with [core git concepts](https://docs.github.com/en/get-started/using-git/about-git), including [branches](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-branches) and [forks](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks). The code examples will use [Next.js](https://nextjs.org/) and [React](https://reactjs.org/) for the application, and [Cypress](https://www.cypress.io/) for testing, however **no coding experience** is required as all the necessary code will be provided.

## Getting the most out of the workshop

This workshop is designed to take approximately three hours. As a result, we won't be able to cover everything or dig too deep into each topic. The goal is to help you become familiar with the tools and services available to you and your organization, introduce concepts and best practices, and provide a jumping-off point to better implement DevOps processes.

During the workshop we will work through a series of exercises. You are welcome and encouraged to follow along using your own GitHub account and the templates and instructions provided. You can also follow along as the presenter demonstrates the various skills.

> **IMPORTANT** This is designed to be an interactive experience. Please ask all the questions you want. This is why we are here.

## Outline

1. Introductions and setup.
2. Project management with Projects and issues.
3. Streamlining the setup process with Codespaces.
4. Developing with the help of Copilot.
5. Managing changes with pull requests.
6. Securing the supply chain.
7. Automation, continuous integration and continuous delivery/deployment.

## Introduction and setup

For the workshop you will use a project based on the [Next.js/MongoDB example](https://github.com/vercel/next.js/tree/canary/examples/with-mongodb). You will start by creating a new repository based on the provided template, add a new component and test to the project, create a pull request to merge the code, automate testing, and finally explore deployment options.

### Get ready for the workshop

You will start by creating a new repository based on a provided template. You will use this repository for the workshop to explore GitHub and DevOps.

1. Navigate to the [template](https://github.com/GeekTrainer/pets-walkthrough/).
2. Select **Use this template** > **Create a new repository**.
3. Configure the new repository with the following settings:
    - **Owner**: *Your GitHub account*
    - **Repository name**: *pets-workshop*
    - **Visibility**: **Public**
4. Select **Create repository from template**.

## Project management with Projects and issues

DevOps is defined by the late Abel Wang as "the union of people, processes, and products to enable the continuous delivery of value to our end-users". Many of the processes development teams use are based on various agile methodologies, which organizations will typically customize. There are a variety of different approaches to project management; unfortunately, we won't have an opportunity to cover them all. Fortunately, GitHub Projects offers the flexibility needed to support the methodology your organization chooses to use.

Of course, regardless of the strategy your team decides to use, you will need the ability to track the tasks your developers are working on. GitHub Projects and issues allow you to manage these processes natively in GitHub. Projects is designed to be flexible, allowing you to make the customizations necessary to support your project management methodologies.

### Create a project

With the repository created, you will now setup a project and an issue to manage changes.

1. Return to the repository you created earlier
2. Select **Projects**.
3. Select **Add project** > **Go to your profile to create a new project**.
4. Select **New project**.
5. Select **Team backlog** and **Create**.
6. Select the title and rename the project to **Pet adoption website**.
7. In the **New** column, select **+ Add item**.
8. Title the item **Add welcome message** and press enter.
9. Select the link on the new **Add welcome message item**.
10. Select **Add assignees** and select your account to assign the item to yourself.
11. Select **Convert to issue**.
12. Select **pets-workshop** to add the issue to the repository.
13. Select **New** on the status and select **In progress**.
14. Select the **X** to exit the window.

### Projects resources

- [About Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)
- [Best practices for Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/best-practices-for-projects)
- [About issues](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues)

## Streamlining the setup process with Codespaces

Most organizations are keenly aware of the importance of developer velocity. With the shortage of developers and resources, more work typically exists than is able to be completed. Unfortunately, countless hours are lost as developers struggle with setup issues, versioning conflicts, and downloading tooling. Hours, and sometimes even days, can be lost to the setup process. With GitHub Codespaces, you can eliminate these issues and get your developers up and running quickly.

Codespaces allows you to configure a container for your project to use as a cloud-hosted development environment. Built upon Docker, you can incorporate different images, install the necessary libraries and services, and even specify Visual Studio Code extensions. Developers can then connect to the container using Visual Studio Code running locally, or in the browser without any local installation required! This eliminates the setup requirements, providing access to a completely configured development environment within seconds.

### Configure and open a Codespace

Let's setup our development environment with GitHub Codespaces. You'll start by creating a new Codespace, then adding some configuration to ensure everything runs successfully. Finally, you'll see how to run the project in the Codespace and connect to it from your local machine.

1. Return to your **pets-workshop** repository.
2. Select **Code** > **Codespaces** > **Create codespace on main**.
3. A new tab will open; return to the previous tab while the container is built.
4. Select **Settings**.
5. Select **Codespaces** and note the different options available for pre-building containers.
6. Select **Secrets and variables** > **Codespaces**.
7. Select **New repository secret** and configure the new secret with the following settings:
    - **Name**: **MONGODB_URI**
    - **Value**: **mongodb://localhost**
8. Select **Add secret** to create the secret.
9. Return to the tab with the codespace.
10. Select **Reload to apply** to reload the codespace with the updated environment variable.
11. Open a terminal window by pressing **Ctl-`**.
12. Use the command `npm install` in the terminal window to install the npm packages.
13. Use the command `npm run dev` to launch the website in the Codespace.
14. When prompted, select **Open in browser** to open the website.

> **NOTE:** If you wish to add a pet to the database, which is running on MongoDB inside the container, you can selet **Add Pet** and complete the form. You can use [this dog image](https://raw.githubusercontent.com/GeekTrainer/pets-walkthrough/main/pics/sammy.jpg). (If you were wondering if this is just a shameless excuse for the author of this workshop to showoff his dog you wouldn't be wrong.)

### Codespaces resources

- [GitHub Codespaces overview](https://docs.github.com/en/codespaces/overview)
- [Introduction to dev containers](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/introduction-to-dev-containers)
- [Add a dev container configuration to your repository](https://docs.github.com/en/codespaces/setting-up-your-project-for-codespaces/setting-up-your-project-for-codespaces)

## Developing with the help of Copilot

Developers have access to a host of frameworks and tools to streamline the process of writing code. However, even with these tools, developers still spend a significant amount of time writing code. With GitHub Copilot, you can now have a co-developer to help you write code. Copilot is an AI-powered code completion tool that can help you write code faster and more efficiently. Copilot can help you write code in a variety of languages, including JavaScript, TypeScript, Python, Java, and C#. (In fact, most of this paragraph was written with Copilot!)

Trained on publicly available text and code, Copilot understands both human and programming languages. Copilot will offer suggestions based on comments and context as the developer types. The suggested code can aid your developers by automatically creating repetitive code or model classes. Copilot can generate regular expressions or other syntax which frequently sends developers to the documentation or internet searches. Because Copilot looks at the surrounding context, the generated code will follow the patterns and practices you're using, including using the frameworks and libraries which are part of your project.

### Write code with the help of Copilot

With the 

1. Return to the Codespace.
2. Select the **Components** folder and select **New file** to create a new file named **Welcome.jsx**.
3. Follow along as we create a component to display a welcome message using Copilot.

    > **NOTE:** You can also copy/paste the [final code](./snippets.md#welcome-component)

4. Open **pages/index.js**.
5. At **line 6**, add the following code to import the component:

    ```javascript
    import Welcome from '../components/Welcome';
    ```

6. Add a new line after line 13 (which reads `<>`) and add the following to display the Welcome component:

    ```javascript
    <Welcome />
    ```

7. Return to the tab with the website and refresh it. Your update should display.

    > **NOTE:** If the update doesn't automatically appear, return to the Codespace and stop/start the dev server

8. Return to the tab with the codespace.
9. Open **cypress/e2e/app.cy.ts** and insert the following code after line 13 to add a test to check if the name textbox is displayed on the page:

    ```javascript
    // check if page has a textbox with id of name
    it('should have a textbox with id of name', () => {
        cy.visit('http://localhost:3000/')
        cy.get('#name').should('exist')
    })
    ```

10. Select **Source control**.
11. Select the ellipsis > **Branch** > **New branch**.
12. Name the new branch **add-welcome**.
13. Enter **Added welcome component and test** for **Message** and select **Commit**.
14. Select **Yes** to commit unstaged items.
15. Select **Publish branch** to push the new branch to the repository.

### Copilot resources

- [About GitHub Copilot](https://docs.github.com/en/copilot/overview-of-github-copilot/about-github-copilot)
- [Configuring GitHub Copilot settings on GitHub.com](https://docs.github.com/en/copilot/configuring-github-copilot/configuring-github-copilot-settings-on-githubcom)

## Managing changes with pull requests

The pull request (PR) is the heart of the development process at GitHub and [InnerSource](https://resources.github.com/innersource/fundamentals/). A pull request is exactly as the name implies, a request. It's a request to make changes, to introduce features, to add code to the codebase. When treated as such, a PR is a great opportunity to explore and discuss options, to experiment, to upskill developers.

> **NOTE:** While the focus for source control is often targeted at larger teams, it's importance remains for small teams and even individual developers. Ensuring good source control practices will help protect you, and your team, from accidental deletes, bad updates, and a host of other calamities.

GitHub offers many tools to control the PR process. At the most basic level, you can require PRs for certain branches to prevent direct commits/merges. You can also require a set number of reviewers, validation checks to pass, and even ensure rules are enforced for administrators. Through these rules you can safely use PRs as they were intended, knowing no code will be merged into your codebase without appropriate sign-off.

### Configure protected branches

With the code created we want to ensure rules are setup for the **main** branch, and the issue you is linked to the branch and PR.

1. Return to the repository.
2. Select **Issues** and open the issue titled **Add welcome message**.
3. Select the gear icon next to **Development** to link a branch to the issue.
4. Select the **pets-workshop** repository and the **add-welcome** branch to finish the link.
5. Select **Settings**.
6. Select **Branches**.
7. Select **Add branch protection rule** to create a new rule with the following configuration:
    - **Branch name pattern**: **main**
    - **Require a pull request before merging** selected
    - **Do not allow bypassing the above settings** selected
8. Select **Create** to enable the rule.
9. Select **Code**.
10. Select **Compare & pull request** to create a PR from the branch you created earlier.
11. Select **Create pull request**.
12. Notice the branch protection rule being enforce as the PR is unable to be merged.
13. Select **Files changed** to see the updates proposed by the PR.
14. Select **Review changes**, noticing **Approve** is disabled as the PR creator is unable to approve their own PRs.

> **NOTE:** For the time being we'll leave our branch protection rules in place. We'll make some updates later in the workshop.

### Managing changes resources

- [About pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)
- [About pull request reviews](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/about-pull-request-reviews)
- [Checking out pull requests locally](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/checking-out-pull-requests-locally)
- [About protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches)
- [Managing a branch protection rule](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/managing-a-branch-protection-rule)

## Securing the supply chain

Put simply, more code means more potential for vulnerabilities. Software remains the number one attack vector used by hackers. Ensuring the code we write and the libraries we use are safe and don't introduce security flaws is of the utmost importance. But at the same time we need to limit the addition of overhead on our developers, as learning new tools or introducing external processes will slow development and increase the chances the checks we put in place are bypassed.

GitHub Advanced Security (GHAS) provides the tools your organization needs and are built to seamlessly be incorporated into existing workflows. GHAS secures your software supply chain by analyzing the code your developers create and the libraries you use for vulnerabilities. GHAS is made of three components: Dependabot, code scanning and secret scanning. These tools will provide security checks both for existing code and novell code added to the repository.

> **NOTE:** While Dependabot is covered in this section as part of GHAS, it is built into the core GitHub experience.

Dependabot examines the packages and libraries your projects use looking for ones which have known vulnerabilities. When one is detected an alert is raised with information about the issue and remedy options. You can also configure Dependabot to generate PRs to upgrade to a safe version of the package.

Code scanning is built on top of CodeQL, a tool to query code. Code scanning incorporates a large collection of queries written by security experts searching for suspect patterns. When enabled on a repository, code scanning will run on PRs and highlight code with potential vulnerabilities. This is done by adding comments to the PR which highlight the problematic line and provides resolution options to aid the developer.

Finally secret scanning looks for tokens and passwords in code. Secret scanning can identify issues after the code has been pushed, or in the case of well-known tokens for different vendors on push blocking the key from ever being published in your repository.

GHAS also includes reporting to help you get a picture of all repositories in your organization, including vulnerabilities and issues which currently exist, and the status of your codebase.

### Secure the supply chain

Let's enable code scanning to check the code in our PR to ensure everything is secure. You'll start by removing the branch protection to help streamline this exercise. Then you'll enable code scanning. Finally, you'll recreate the branch protection to require code scanning.

1. Navigate to your repository.
2. Select **Settings**.
3. Select **Branches**.
4. Next to the branch protection rule for **main**, select **Delete**.
5. Select **I understand, delete this rule** to confirm the deletion of the rule.
6. Select **Code security and analysis** to access the security settings for your repository.
7. Next to **Code scanning** select **Set up**.
8. Select **Configure scanning tool**.

    > Notice the GitHub Actions configuration screen is displayed. This is because code scanning is automated as part of GitHub Actions. We will explore GitHub Actions in the next section.

9. Under **CodeQL Analysis**, select **Configure**.
10. Select **Start commit** and **Commit new file** to accept the defaults and commit the workflow to your repository.

    > **NOTE:** The workflow will be automatically configured to scan for the languages currently used in the repository, and will run whenever a PR or merge is made into main and on a schedule. You can modify these options by updating the YML file.

11. Select **Actions**. Notice the CodeQL action is running for the merge we just made.

    > **NOTE:** The action will run for **new** pull requests, but not for existing ones. One quick way to run the action for a pull request is to close and reopen it.

### GitHub Advanced Security resources

- [About GitHub Advanced Security](https://docs.github.com/en/get-started/learning-about-github/about-github-advanced-security)
- [About supply chain security](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-supply-chain-security)
- [About code scanning](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/about-code-scanning)
- [Code scanning in a container](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/running-codeql-code-scanning-in-a-container)
- [Managing code security alerts for your repository](https://docs.github.com/en/code-security/code-scanning/automatically-scanning-your-code-for-vulnerabilities-and-errors/managing-code-scanning-alerts-for-your-repository)
- [About secret scanning](https://docs.github.com/en/code-security/secret-scanning/about-secret-scanning)
- [Secret scanning patterns](https://docs.github.com/en/code-security/secret-scanning/secret-scanning-patterns)
- [About Dependabot alerts](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/about-dependabot-alerts)
- [About Dependabot security alerts](https://docs.github.com/en/code-security/dependabot/dependabot-security-updates/about-dependabot-security-updates)

## Automation, continuous integration and continuous delivery/deployment

Automating manual tasks is key to enhancing developer velocity. Automation allows your developers to focus on their code rather than external processes while ensuring consistency and compliance with defined practices. When combined with continuous integration and continuous delivery/deployment, automation can help you deliver software faster and more reliably.

GitHub Actions is a workflow automation tool built into GitHub. Actions are small pieces of code which can be combined to create a workflow. Workflows are triggered by events, such as a push to a branch or a pull request. Workflows can be configured to run on a schedule, or when a specific label is added to a PR. Workflows can also be triggered by an external event, such as a comment on a PR.

There are over 15,000 actions available in the GitHub Marketplace, and you can create your own actions. Actions can be written in JavaScript, Python, Ruby, Java, Go, PowerShell, and more. Actions can be used to automate a wide variety of tasks, such as:

- Building and testing code
- Deploying to a cloud provider
- Resizing images
- Validating machine learning models

### Automate testing

Let's automate the testing of our code. You'll start by creating a workflow to run the tests when a PR is created. Because Cypress runs end-to-end tests, you'll also need to setup an environment variable to store the connection string to the database. You'll close by creating a branch protection rule to enforce code scanning and tests passing before a PR can be merged.

1. Navigate to your repository.
2. Select **Settings** > **Secrets and variables** > **Actions**.
3. Select **New repository secret** and create a new secret with the following settings:
    - **Name**: `MONGODB_URI`
    - **Secret**: `test`
4. Select **Add secret** to save the secret.
5. Select **Actions**.
6. Select **New workflow** to create an empty workflow.
7. Name the file **cypress.yml**.
8. Add the following YML to run the Cypress tests on a PR:

    ```yml
    name: End-to-end tests
    on:
        push:
            branches: ["main"]
        pull_request:
            branches: ["main"]
    jobs:
    cypress-run:
        runs-on: ubuntu-20.04
        steps:
        - name: Checkout
            uses: actions/checkout@v2
        - name: Cypress run
            uses: cypress-io/github-action@v4
            with:
            build: npm run build
            start: npm run start
            env:
            MONGODB_URI: ${{ secrets.MONGODB_URI }}
    ```

9. Select **Start commit** and **Commit new file** to accept the defaults and commit the workflow to your repository.
10. Select **Actions** and notice the Cypress action is running for the merge you just made.
11. When the action completes, select **Settings** > **Branches**.
12. Select **Add branch protection rule** with the following settings to enforce testing and security requirements;:
    - **Branch name pattern**: **main**
    - **Require a pull request before merging** selected
    - **Do not allow bypassing the above settings** selected
    - **Require status checks to pass before merging** selected
    - Search for and select each of the following:
        - **cypress-run**
        - **CodeQL**
13. Select **Create** to enable the rule.

    > **NOTE:** Actions need to run once before they can be used as a branch protection rule.

### Automation resources

## Closing and next steps

Congratulations! You have explored the core concepts of DevOps and learned now to implement them on GitHub. You saw how to use GitHub to manage your code, automate your workflow, and secure your code. You also saw how to use GitHub to collaborate with your team and manage your project.

Depending on your role and where your team is in their DevOps journey, there are many ways to continue learning. There are numerous resources provided in this course which you can use to continue exploring and learning. You will also find it helpful to begin piloting DevOps practices in your team and on specific projects.

If you haven't already done so, visit [startups.github.com](https://startups.github.com/) to gain access to the resources provided by GitHub for Startups. Also be on the lookout for future courses and workshops from GitHub.
