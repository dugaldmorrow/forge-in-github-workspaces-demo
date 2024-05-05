# Forge in GitHib workspaces demo

## Introduction

TBD

Note: Terminal commands in GitHub workspaces are generally quite slow. For the best Forge development experience, set up and run the developement tools on your computer.

## Getting started

### Setting up the Forge CLI

1. Log in to GitHub if not already
2. Visit https://github.com/dugaldmorrow/forge-in-github-workspaces-demo.
3. Press the period (.) button on your keyboard to open the project in GitHub workspaces.
4. Click the hambuger menu at the top left and select Terminal -> New Terminal.
5. Check a new Terminal window opens at the bottom.
6. Click the "Continue Working in GitHub Codespaces" button.
7. Select the "2 Cores, 8 GB RAM, 32 GB Storage" at the top.
8.  Check the browser opens a new tab/window.
9.  Wait for the Terminal to finish initialising and type/copy `node --version` into it to check node is installed (you may need to approve the browser allowing clipboard pastes).
10. Install the Forge CLI by entering `npm install -g @forge/cli` into the Terminal.
11. Enter `read FORGE_EMAIL` and type your Atlassian Account email address.
12. Enter `read -s FORGE_API_TOKEN` and enter one of your Atlassian Account access tokens.
13. Enter `export FORGE_EMAIL FORGE_API_TOKEN` to create environment variables required by Forge.
14. Enter `forge whoami` to check the Forge CLI knows who you are.

### Basic Forge operations

1. Enter `forge register` to register the app as yours.
2. Enter `forge deploy` to deploy the app.
3. Enter `forge install` to install the app in a Confluence site (tenant).
4. Visit the Confluence site you installed the app in and select Apps -> Forge in GituHub Workspaces (Development).
5. Check the page shows "Hello world!" twice (the second one with a delay).
6. Edit `src/index.js` and modify the returned message to say `Hello, from the resolver`.
7. In the Terminal, run `froge deploy`.
8. Reload the Confluence window showing the app and verify the second message changes to `Hello, from the resolver`.

### Setting up Forge tunnelling

1. Install ngrok running the following command:

```
curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list && sudo apt update && sudo apt install ngrok
```

2. Run `ngrok config add-authtoken *****`.
3. Run `ngrok config check` and check the output is `Valid configuration file at /home/codespace/.config/ngrok/ngrok.yml`.
4. Run `forge settings set ngrok-config-path /home/codespace/.config/ngrok/ngrok.yml`.
5. NOT WORKING -> You should now be able to run `forge tunnel`.

