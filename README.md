# Documentation as Code

This project is a skeleton for writing technical documentation and publishing it to Confluence.

## How to Contribute

As a contributor, here are the guidelines we would like you to follow:

- [Development Workflow](#development-workflow)
- [Submitting a Pull Request](#submitting-a-pull-request)
- [Reviewing a Pull Request](#reviewing-a-pull-request)
- [Publishing to Confluence](#publishing-to-confluence)
- [Commit Messages Convention](#commit-messages-convention)
- [Further Help](#further-help)

## Development Workflow

After cloning the project, run `npm install` to fetch its dependencies.

The project uses [texting](https://textlint.github.io/) and [EditorConfig](https://editorconfig.org/).
It is recommend running `npm run lint` to make sure you don’t introduce any regressions as you work on your change.
To ensure all files committed to git don’t have any linting or formatting errors, markdownlint is executed on each commit.
Besides that, you can run `npm run lint:fix` after making any changes to the code.

This project follows [semantic versioning](https://semver.org/) and [conventional commits](https://www.conventionalcommits.org/).
It is recommended to follow these guidelines when creating your branch and submitting your changes.

## Submitting a Pull Request

Before submitting a pull request, please make sure the following is done:

- Fork the repository and create your branch from **master**.
- Make sure your code lints (`npm run lint`).
- Make sure your changes use a descriptive commit message that follows the [Commit Message Convention](#commit-messages-convention).
- You must [squash and rebase](https://levelup.gitconnected.com/squash-and-rebase-my-method-for-merging-git-branches-3b43c52675b6) your commits.
- Finally, submit all changes directly to the **master** branch.

## Reviewing a Pull Request

The project maintainer will review your pull request.
He will review your pull request and either merge it, request changes to it, or close it with an explanation.
After your pull request is merged, you can safely delete your branch.

## Publishing to Confluence

Publishing in Confluence means making your versioned content available to its audience within Confluence.

This project allows documentation written in Markdown and Confluence Wiki, and versioned directly with the documented code base to be published to a Confluence space.
It converts the resulting HTML output to HTML compatible with Confluence, manages included resources as Confluence attachments and ensures that only content modified since the last publication is again re-published.

To publish all Confluence pages, you can use `npm run publish` command.
All pages described in the [Site Map](./docs/site-map.yaml) will be publish in Confluence.
For more details, you can read [Confluence Site Publisher](https://github.com/bsorrentino/confluence-site-publisher) documentation.

Alternatively, you can use a local instance of Confluence.
You can use `docker-compose up -d` command to start a local instance of Confluence Server.
Please note that you need to subscribe to a free trial plan to use Confluence Server.


## Commit Messages Convention

To have a consistent git history every commit must follow a specific template.

Here’s the template:

```bash
<type>(<ITEM ID>?): <subject>
```

### Type

Must be one of the following:

- **build**: Changes that affect the build system or external dependencies (example scopes: gulp, npm)
- **ci**: Changes to our CI configuration files and scripts (example scopes: Jenkins, GitHub Actions, etc.)
- **chore**: Changes to the build process or auxiliary tools and libraries such as documentation generation
- **docs**: Documentation only changes
- **feat**: A new feature
- **fix**: A bug fix
- **perf**: A code change that improves performance
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **revert**: A commit that reverts a previous one
- **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc.)
- **test**: Adding missing tests or correcting existing tests

### ITEM ID

The related **issue** or **user story** or even **defect**.

- For **user stories**, you shoud use `US-` as prefix. Example: `feat(US-4321): ...`
- For **no related issues** or **defects** you should leave it blank. Example: `feat: ...`

### Subject

The subject contains a succinct description of the change.

## Further Help

If you need help, contact the [project maintainer](mailto:asousafilipe@hotmail.com).
