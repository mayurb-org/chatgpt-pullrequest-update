# chatgpt-pullrequest-explanation-generator

This repository contains code that utilizes the OpenAI ChatGPT model to generate explanations for code changes in pull requests on GitHub. The generated explanations can be used to provide a clear understanding of the changes made in a pull request.

## Files

- `generate_explanation.py`: This Python script is responsible for generating explanations for code changes. It uses the OpenAI API to interact with the ChatGPT model and retrieve the explanations. The code takes the changes as input, retrieves the necessary information from the GitHub API, and generates the explanation using the ChatGPT model. The generated explanation is then printed or can be used as needed.

- `.github/workflows/chat-gpt-comment-update.yml`: This workflow file is used to automate the process of generating explanations and adding them as comments to pull requests. It listens for pull request events (opened, reopened, synchronize) and triggers the workflow. The workflow checks out the repository, sets up the Python environment, installs the required dependencies, generates the explanation using `generate_explanation.py`, and adds the explanation as a comment to the pull request.

## Usage

To use this code in your GitHub repository, follow these steps:

1. Create an OpenAI API key: You need to have an OpenAI API key to interact with the ChatGPT model. If you don't have one, sign up on the OpenAI website and obtain an API key.

2. Add the OpenAI API key as a secret: In your GitHub repository, go to the repository settings, and navigate to the "Secrets" tab. Add a new secret called `OPENAI_API_KEY` and paste your API key as the value.

3. Configure the workflow: In the `.github/workflows/chat-gpt-comment-update.yml` file, make sure to replace the placeholders in the `env` section with the appropriate values:
   - `${{ secrets.OPENAI_API_KEY }}`: Replace with `OPENAI_API_KEY`, which is the secret you added in step 2.
   - `${{ secrets.GITHUB_TOKEN }}`: This token is automatically provided by GitHub, and you don't need to make any changes.

4. Commit and push the changes: Save the modified workflow file and commit it to your repository. Push the changes to trigger the workflow.

5. Enjoy automated explanations: The workflow will now run whenever a pull request is opened, reopened, or synchronized. It will generate an explanation using the ChatGPT model and add it as a comment to the respective pull request.

Note: Make sure that the repository where you set up the workflow has the necessary permissions to add comments to pull requests.
