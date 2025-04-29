# Task 6: Copilot Extension Practice

## Use case:
- Practice using GitHub Copilot's Extension.

- **This practice uses Node.js.**
  - [Node.js installation](https://nodejs.org/en/download) is required.

## Goal:
- Practice utilizing GitHub Copilot's Extension.
- Understand and practice the two ways to create GitHub Copilot Extensions (Skillset, Agent).

## Step 1: Practice Creating a Skillset Extension Using Internal Document API
- Reference repository: https://github.com/Kor-GHCPWorkshop/kordocserver_demo

- Use Node.js to build an Express server and provide an API for two Markdown files in the docs directory.
  - Use Copilot to write code when building the server.
  - Create a server.js file and implement the Express server (using Copilot).
  - Use the two Markdown files in the docs directory to provide them as APIs.
  - Once completed, run the server with npm start.<br>
  <img src="img/01.png" width="800">

- For practice, use Ngrok to expose your local server externally.<br>
  - [Download Ngrok](https://ngrok.com/download)<br>
  - [Ngrok installation and usage](https://ngrok.com/docs)<br>
  <img src="img/02.png" width="800">

- Create a GitHub app in your personal account on GitHub.com and create an app in Copilot 'Skillset' mode.
  - In your personal account, go to 'Settings' > 'Developer settings' > 'GitHub Apps > New GitHub App' to create a new app.<br>
   <img src="img/03.png" width="800">
  
  - In General, enter the App name, Homepage URL, and Callback URL (use the Ngrok URL).<br>
   <img src="img/09.png" width="800"><br>

  - In Account permission, set the two Copilot-related permissions to 'read-only'.<br>
   <img src="img/04.png" width="800"><br>

  - Set the App Type to Skillset.<br>
   <img src="img/05.png" width="400"><br>
   
  - Add Skill definitions.<br>
   <img src="img/06.png" width="600"><br>

  - For copilot-standalone, add the 'Inference description' and 'Parameter' as below, and set the URL to the Ngrok-exposed address.<br>    
    
    - Inference description:
    ```
    Description of Copilot Standalone
    Purchase procedure for Copilot Standalone
    Whether Copilot Standalone offers a free trial
    Description of Copilot Standalone authentication server integration
    ``` 

    - URL: `https://your-ngrok-url-here/copilotstandalone`

    - Parameters:
      
    ```
    {
    "type": "object"
    }
    ```
    
   <img src="img/07.png" width="500"> 

   <img src="img/10.png" width="500"><br>

- Save.

- On the left, go to the `Install App` menu and install.<br>
  <img src="img/08.png" width="600">

- For testing, open a separate VS Code, type @ in Copilot Chat, check the newly added Copilot Extension, and proceed with Authorization.<br>
  <img src="img/11.png" width="600">
  <img src="img/12.png" width="600">

- In `Ask` mode, select the **GPT-4o** model.<br>
  <img src="img/14.png" width="400"><br>

- After Authorization is complete, type `@extension-name` and ask questions such as "Explain Copilot Standalone" to check the operation of the Copilot Extension.<br>
  <img src="img/16.png" width="600"><br>
  <img src="img/13.png" width="600"><br>

  - Ngrok returns 200K.<br>
  <img src="img/15.png" width="600"><br>

- Try other questions as well.<br>
  <img src="img/17.png" width="600"><br>
  <img src="img/18.png" width="600"><br>

## Step 2: Practice Creating an Agent Extension
- Reference repository: https://github.com/Kor-GHCPWorkshop/gist_funcCall_demo

- This practice example uses [Function calling](https://help.openai.com/en/articles/8555517-function-calling-in-the-openai-api).
  - As in Step 1, run the server, but this time the LLM calls a function to execute an internal server function.
  - The function creates a Gist in the GitHub user account using the code snippet sent to Copilot.
  - This function requires three parameters:
    - File name, Code body, Gist description
  - The file name and code body use the content provided by Copilot, and the Gist description is summarized using the content provided by Copilot.

- To create an Agent Extension, follow these steps:
   - Run the server and forward externally with Ngrok.
   - As with the Skillset Extension, create an app but select 'Agent' mode.<br>
      <img src="img/05.png" width="300"><br>

   - Set the URL and Inference description.<br>
      <img src="img/19.png" width="600"><br>

   - Install the app.<br>

- For testing, open a separate VS Code, type @ in Copilot Chat, check the newly added Copilot Extension, and proceed with Authorization.

- After Authorization is complete, type `@extension-name` and make requests such as "create a gist" to check the operation of the Copilot Extension.<br>
  <img src="img/20.png" width="600"><br>
  <img src="img/21.png" width="600"><br>

- Check if the Gist was created.<br>
  <img src="img/22.png" width="800"><br>


## Additional Resources
- https://docs.github.com/en/copilot/building-copilot-extensions/building-a-copilot-agent-for-your-copilot-extension/using-copilots-llm-for-your-agent

- https://resources.github.com/learn/pathways/copilot/extensions/building-your-first-extension/
- https://docs.github.com/en/copilot/customizing-copilot/extending-the-capabilities-of-github-copilot-in-your-organization