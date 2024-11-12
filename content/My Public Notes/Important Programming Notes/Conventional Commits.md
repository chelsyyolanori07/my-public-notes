## Commit Message Guidelines

We have very precise rules over how our git commit messages can be formatted. This leads to **more readable messages** that are easy to follow when looking through the **project history**. But also, we use the git commit messages to **generate the Angular change log**.

### Commit Message Format

Each commit message consists of a **header**, a **body** and a **footer**. The header has a special format that includes a **type**, a **scope** and a **subject**:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The **header** is mandatory and the **scope** of the header is optional.

Any line of the commit message cannot be longer 100 characters! This allows the message to be easier to read on GitHub as well as in various git tools.

The footer should contain a [closing reference to an issue](https://help.github.com/articles/closing-issues-via-commit-messages/) if any.

Samples: (even more [samples](https://github.com/angular/angular/commits/master))

```
docs(changelog): update changelog to beta.5
```

```
fix(release): need to depend on latest rxjs and zone.js

The version in our package.json gets copied to the one we publish, and users need the latest of these.
```

### Revert

If the commit reverts a previous commit, it should begin with `revert:` , followed by the header of the reverted commit. In the body it should say: `This reverts commit <hash>.`, where the hash is the SHA of the commit being reverted.

### Type

Must be one of the following:

- **build**: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
- **ci**: Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs)
- **docs**: Documentation only changes
- **feat**: A new feature
- **fix**: A bug fix
- **perf**: A code change that improves performance
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- **test**: Adding missing tests or correcting existing tests

### Scope

The scope should be the name of the npm package affected (as perceived by the person reading the changelog generated from commit messages.

The following is the list of supported scopes:

- **animations**
- **common**
- **compiler**
- **compiler-cli**
- **core**
- **elements**
- **forms**
- **http**
- **language-service**
- **platform-browser**
- **platform-browser-dynamic**
- **platform-server**
- **platform-webworker**
- **platform-webworker-dynamic**
- **router**
- **service-worker**
- **upgrade**

There are currently a few exceptions to the "use package name" rule:

- **packaging**: used for changes that change the npm package layout in all of our packages, e.g. public path changes, package.json changes done to all packages, d.ts file/format changes, changes to bundles, etc.
- **changelog**: used for updating the release notes in CHANGELOG.md
- **aio**: used for docs-app (angular.io) related changes within the /aio directory of the repo
- none/empty string: useful for `style`, `test` and `refactor` changes that are done across all packages (e.g. `style: add missing semicolons`)

### Subject

The subject contains a succinct description of the change:

- use the imperative, present tense: "change" not "changed" nor "changes"
- don't capitalize the first letter
- no dot (.) at the end

### Body

Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes". The body should include the motivation for the change and contrast this with previous behavior.

### Footer

The footer should contain any information about **Breaking Changes** and is also the place to reference GitHub issues that this commit **Closes**.

**Breaking Changes** should start with the word `BREAKING CHANGE:` with a space or two newlines. The rest of the commit message is then used for this.

A detailed explanation can be found in this [document](https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#).


## Make sure you remember this when writing commits

Writing good commit messages is a skill that can be developed with practice. Here are some tips and best practices to help you write better commit messages:

### Tips for Writing Good Commit Messages

1. **Use the Imperative Mood**
   - Write your commit messages as if you are giving commands: "Fix bug" instead of "Fixed bug" or "Fixes bug."
   - This style is consistent with how commit messages are read in the context of code changes, e.g., "If applied, this commit will fix the bug."

2. **Be Brief but Descriptive**
   - The subject line should be concise and to the point, ideally 50 characters or less.
   - If needed, use the body of the commit message to provide more details.

3. **Separate Subject and Body with a Blank Line**
   - Start the body of the commit message after a blank line following the subject.
   - The body can include additional details, the motivation behind the change, and any background information that will help future readers understand the change.

4. **Explain the Why, Not Just the What**
   - The subject should describe what was changed.
   - The body should explain why the change was made and any relevant context.

5. **Use the Conventional Commits Specification**
   - Use the format `<type>(<scope>): <subject>` for consistency.
   - This helps automate tasks such as versioning and changelog generation.

6. **Use Scopes Consistently**
   - Choose meaningful scopes that correspond to modules, features, or components in your codebase.
   - Keep scope names consistent throughout the project.

7. **Capitalize the Subject Line**
   - Start the subject line with a capital letter for readability.

8. **Do Not End the Subject Line with a Period**
   - This is a convention to keep the subject clean and concise.

9. **Use Active Voice**
   - Write commit messages in active voice, e.g., "Update dependencies" instead of "Dependencies updated."

### Example Commit Messages

Here are some examples of good commit messages:

**Feature Addition:**
```
feat(auth): add OAuth2 login

Added support for OAuth2 login, allowing users to authenticate using their Google accounts.
```

**Bug Fix:**
```
fix(ui): resolve dropdown menu issue

Fixed the dropdown menu not appearing on mobile devices. The issue was caused by incorrect CSS z-index values.
```

**Documentation Update:**
```
docs(readme): update installation instructions

Clarified the steps needed to set up the development environment on Windows. Added notes on required dependencies and common pitfalls.
```

**Code Refactoring:**
```
refactor(api): simplify request validation logic

Refactored the request validation logic to reduce complexity and improve maintainability. Removed redundant checks and consolidated validation functions.
```

### Using Tools to Help

1. **Commitizen**
   - Commitizen is a tool that helps you write commit messages according to the Conventional Commits specification.
   - Install it globally with `npm install -g commitizen`.
   - Initialize it in your project with `commitizen init cz-conventional-changelog --save-dev --save-exact`.
   - Use `git cz` instead of `git commit` to be guided through the commit message process.

2. **Linting Commit Messages**
   - Use tools like `commitlint` to enforce commit message conventions.
   - Set up `commitlint` with the Conventional Commits configuration to automatically check commit messages.

### Practice and Review

1. **Review Commit History**
   - Look at commit histories in well-maintained open-source projects to see examples of good commit messages.
   - Review your own commit history and look for ways to improve.

2. **Get Feedback**
   - Ask team members or collaborators to review your commit messages and provide feedback.
   - Learn from the feedback and continuously improve your commit message writing skills.

By following these tips and practicing consistently, you'll become more confident in writing clear and effective commit messages.

## Scope?

The **scope** in a conventional commit message is not necessarily the name of a file but rather a context that gives an indication of what part of the codebase the change affects. It typically represents a logical grouping or module within the project rather than a specific file. The scope helps to provide additional clarity about what part of the system is being changed, making it easier to understand the impact of the commit at a glance.

### Examples of Scopes

Here are some examples to illustrate what could be used as a scope:

- **feat(parser):** Adding a new feature to the parsing module.
- **fix(auth):** Fixing a bug in the authentication system.
- **docs(api):** Updating documentation related to the API.
- **style(css):** Changes related to CSS styling.
- **refactor(core):** Refactoring code in the core functionality.
- **test(logging):** Adding or updating tests for the logging module.

### Example Commit Messages

1. **Feature Addition with Scope:**
   ```
   feat(auth): add support for OAuth2

   Added OAuth2 support to allow users to authenticate using their Google accounts. This includes new login routes and token handling.
   ```

2. **Bug Fix with Scope:**
   ```
   fix(ui): resolve dropdown menu issue

   Fixed the dropdown menu not appearing on mobile devices. The issue was caused by incorrect CSS z-index values.
   ```

3. **Documentation Update with Scope:**
   ```
   docs(readme): update installation instructions

   Clarified the steps needed to set up the development environment on Windows. Added notes on required dependencies and common pitfalls.
   ```

4. **Code Style Changes with Scope:**
   ```
   style(css): improve button hover effects

   Enhanced the hover effects for buttons to provide a more responsive feel. Updated CSS classes and variables.
   ```

### Choosing a Scope

When choosing a scope, consider the following guidelines:
- **Specificity:** Be specific enough to provide meaningful context but broad enough to cover related changes.
- **Consistency:** Use consistent naming for scopes across your project to maintain clarity.
- **Relevance:** The scope should be relevant to the area of the codebase affected by the changes.

### No Scope Example

Sometimes, you might have commits that don't need a scope. In such cases, you can omit the scope part.

```
docs: fix typo in README
```

In summary, the scope is a useful element in conventional commits that provides context about the part of the codebase affected by the commit, but it doesn't have to be the name of a specific file. It helps in maintaining a clearer and more organized project history.

## Short Notes Conventional Commits
Sure! Conventional Commits is a specification for writing standardized commit messages in Git. It helps in maintaining clear and consistent commit histories, which can be especially useful for projects with many contributors. Here’s a breakdown of how it works:

### Structure of a Conventional Commit

A conventional commit message follows this structure:
```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

#### 1. **Type**
The type describes the purpose of the commit. Common types include:
- **feat**: A new feature for the user.
- **fix**: A bug fix.
- **docs**: Documentation only changes.
- **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc).
- **refactor**: A code change that neither fixes a bug nor adds a feature.
- **perf**: A code change that improves performance.
- **test**: Adding missing tests or correcting existing tests.
- **chore**: Changes to the build process or auxiliary tools and libraries such as documentation generation.

#### 2. **Scope**
The scope is optional and indicates the section of the codebase affected by the commit. For example, `feat(parser): add new parsing logic` where `parser` is the scope.

#### 3. **Subject**
The subject is a brief summary of the changes, written in imperative mood (e.g., "add", "fix", "update").

#### 4. **Body**
The body is optional and provides a more detailed explanation of the commit, including the motivation for the change and contrasts with the previous behavior.

#### 5. **Footer**
The footer is optional and can include references to issues that this commit closes or affects. It’s also used for breaking changes.

### Examples of Conventional Commit Messages

**Feature Addition:**
```
feat(authentication): add OAuth2 login

Add support for OAuth2 login, allowing users to authenticate using their Google accounts.
```

**Bug Fix:**
```
fix(database): correct connection timeout issue

The connection timeout setting was previously too short, causing frequent timeouts. It has been extended to 30 seconds.
```

**Documentation Update:**
```
docs(readme): update installation instructions

Added more detailed steps for setting up the project on Windows systems.
```

### Benefits of Conventional Commits

1. **Automated Versioning**: Tools like Semantic Release can automatically determine the next version number based on the types of commits.
2. **Readable History**: Commit messages follow a consistent format, making it easier to understand the project history.
3. **Improved Collaboration**: Clear commit messages help team members understand the changes and their context.

### How to Write Conventional Commits

1. **Install Commitizen**: Commitizen is a tool that helps you write commit messages that follow the Conventional Commits standard.
   ```
   npm install -g commitizen
   ```
2. **Initialize Commitizen in Your Project**:
   ```
   commitizen init cz-conventional-changelog --save-dev --save-exact
   ```
3. **Use Commitizen to Commit**:
   ```
   git cz
   ```
   This will prompt you to fill in the type, scope, subject, body, and footer, ensuring your commit message adheres to the conventional commits standard.

### Conclusion

By following the Conventional Commits specification, you ensure that your commit messages are clear, consistent, and useful for both humans and automated tools. This practice helps maintain a high-quality project history and facilitates better collaboration among team members.

## Using Commitizen
When you follow the steps to install and use Commitizen, it helps you write commit messages that follow the Conventional Commits standard by providing a guided, interactive prompt. Here’s what happens step by step:

### Step-by-Step Breakdown

1. **Install Commitizen Globally**
   ```
   npm install -g commitizen
   ```
   - This command installs Commitizen globally on your system, making it available for use in any project.
   - Commitizen is a tool that assists in creating commit messages that follow predefined standards, such as the Conventional Commits specification.

2. **Initialize Commitizen in Your Project**
   ```
   commitizen init cz-conventional-changelog --save-dev --save-exact
   ```
   - This command sets up Commitizen in your project with the `cz-conventional-changelog` adapter.
   - The `--save-dev` flag adds Commitizen to your project's `devDependencies`.
   - The `--save-exact` flag ensures that the exact version specified is used.

3. **Use Commitizen to Commit**
   ```
   git cz
   ```
   - Instead of using `git commit`, you use `git cz` to create commits.
   - This command launches an interactive prompt that guides you through the process of writing a commit message.

### Interactive Prompt

When you run `git cz`, you'll be prompted to fill in various parts of the commit message:

1. **Type**
   - You'll be asked to choose the type of change you're committing (e.g., `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`).

2. **Scope**
   - You’ll specify the scope of the changes, which is the part of the codebase affected (e.g., `auth`, `api`, `ui`).

3. **Subject**
   - You'll write a short, imperative summary of the change (e.g., "add OAuth2 login support").

4. **Body**
   - You have the option to provide a more detailed description of the change, explaining what and why.

5. **Footer**
   - This section is for referencing issues closed by the commit or noting any breaking changes.

### Example of an Interactive Commitizen Session

Here's an example of what you might see and input during an interactive session:

```
$ git cz
? Select the type of change that you're committing: feat:     A new feature
? What is the scope of this change (e.g. component or file name): (press enter to skip) auth
? Write a short, imperative tense description of the change (max 94 chars):
 (24) add OAuth2 login support
? Provide a longer description of the change: (press enter to skip)
 Added support for OAuth2 login, allowing users to authenticate using their Google accounts.
? Are there any breaking changes? No
? Does this commit affect any open issues? No
```

### Resulting Commit Message

After completing the prompts, Commitizen will generate a commit message formatted according to the Conventional Commits specification. For the example above, the resulting commit message might look like this:

```
feat(auth): add OAuth2 login support

Added support for OAuth2 login, allowing users to authenticate using their Google accounts.
```

### Benefits

- **Consistency:** Ensures all commit messages follow a standardized format, making them easier to read and understand.
- **Automation:** Tools like Semantic Release can use these structured commit messages to automate versioning and changelog generation.
- **Clarity:** Provides clear context about the nature and scope of changes, aiding in better project maintenance and collaboration.

By using Commitizen, you make it easier to follow best practices for commit messages, enhancing the quality and maintainability of your project's commit history.

[[Git Important Notes]]
#git 
