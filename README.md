# GitHub Copilot Workshop
Hello, this is the GitHub Copilot Workshop repository.
This repository contains various hands-on exercises, ranging from basic usage of GitHub Copilot for code suggestions to advanced workflows. Each project presents a different use case for GitHub Copilot and is completed as an individual exercise.

## Practice Environment
- Use VS Code.
  * There may be functional differences in other IDE tools (such as IntelliJ IDEA, Android Studio), so some exercises may not be supported.
  * The screenshots provided in this workshop may differ from the menus you see.
  * This is because the features or menu locations of GitHub Copilot or VS Code may have changed due to updates.
  * Also, depending on your organization's admin settings, the available features may vary according to company policy.

- You must have the GitHub Copilot plugin installed and be logged in with an account that has a GitHub Copilot Business license.
- Both VS Code and the GitHub Copilot plugin must be **updated to the latest version**.

  ### Language and Build
  C, CMake, SQLite
  [Install the C/C++ Extension Pack in VS Code.](https://code.visualstudio.com/docs/cpp/config-mingw)

## Description: GitHub Copilot Preview
 - An overview of GitHub Copilot will be provided through materials.
  - [Best practices for using GitHub Copilot](https://docs.github.com/ko/enterprise-cloud@latest/copilot/using-github-copilot/best-practices-for-using-github-copilot)
  - [GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/overview)
  - [Essential features of GitHub Copilot for beginners](https://github.blog/ai-and-ml/github-copilot/github-for-beginners-essential-features-of-github-copilot/)
  - [GitHub Copilot in VS Code Cheat Sheet](https://code.visualstudio.com/docs/copilot/reference/copilot-vscode-features#:~:text=Define%20shared%20instructions%20for%20code%20generation%20in%20a,common%20instructions%20supplement%20your%20own%20personal%20code-generation%20instructions.)

## [Task 1](/Task01/README.md): Get suggestions for simple functions and test code (code completion)
 - Practice receiving suggestions for simple functions and test code using GitHub Copilot. This helps you learn the basic features of Copilot.
 - Check the GitHub Copilot Log to see reference information if the code matches open source.
 - Try changing the basic settings in the Copilot menu in VS Code.

## [Task 2](/Task02/README.md): Create a Rock, Paper, Scissors game (using Copilot Chat)
 - Create a Rock, Paper, Scissors game with GitHub Copilot.
 - Write test code through Copilot.
 - Use various menus of Copilot chat.
 - Get a code review for your code through Copilot Code Review.
 - Provide images as context to Copilot Chat (Vision feature) and get code suggestions based on the images. (Vision)

## [Task 3](/Task03/README.md): Build a library loan management program (Part 1)
 - Learn how to use various features of GitHub Copilot by building a real library loan management program.
 - Try using models other than the default GPT-4o model.
 - Learn how to provide custom instructions to Copilot to get code suggestions in your desired format.
 - Use the 'Ask', 'Edit', and 'Agent' modes of Copilot chat to build modules and understand the differences.

## Description: GitHub Copilot Prompt Engineering
 - An explanation of prompt engineering methods when using GitHub Copilot.
 - [Best practices for using GitHub Copilot in VS Code](https://code.visualstudio.com/docs/copilot/prompt-crafting)
 - [Tips, tricks, and best practices for using GitHub Copilot in your IDE](https://github.blog/developer-skills/github/how-to-use-github-copilot-in-your-ide-tips-tricks-and-best-practices/)
 - [Developer guide to prompt engineering and LMM](https://github.blog/ai-and-ml/generative-ai/prompt-engineering-guide-generative-ai-llms/)
 - [Introduction to prompt engineering with GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Examples and best practices for writing better prompts for GitHub Copilot](https://github.blog/developer-skills/github/how-to-write-better-prompts-for-github-copilot/)

## [Task 4](/Task04/README.md): Build a library loan management program (Part 2)
  - Use Copilot to generate unit test code for the library loan management program created in Part 1, troubleshoot errors during testing, use Copilot from the CLI, and automatically generate commit messages.

## [Task 5](/Task05/README.md): Using Copilot for code review and refactoring
  - Get a code review and perform refactoring using Copilot.
  - Learn how to use custom instructions for code review by using a prompt file.
  - Try using questions with `@workspace`.
  - Create prompt files for code refactoring and new module creation, and request Copilot to refactor code and create new modules.

## Description: What is a Copilot Extension?
  - [Copilot Extension](https://github.com/features/copilot/extensions) is an extension that provides additional features to Copilot Chat.
  - Extensions available on the [GitHub Marketplace](https://github.com/marketplace?type=apps&copilot_app=true) can be installed and used by the organization's admin.
  - You can build your own extensions in various ways (API, RAG, using your own model, etc.).
  ** To use Copilot Extension at the organization level, an additional GitHub Enterprise license is required.

## [Task 6](/Task06/README.md): Copilot Extension Practice
  - Practice using GitHub Copilot's Extension.
  - Understand and practice the two ways to create GitHub Copilot Extensions (Skillset, Agent).




