# Forge Workshop — Codespaces Quick Start

Welcome! This repo is preconfigured with a Dev Container for Atlassian Forge development. No local installs required—just launch a Codespace and start building.

## Prerequisites (2 minutes)
- Free GitHub account.
- Atlassian account.
- An API token from https://id.atlassian.com/manage/api-tokens.
- Your Atlassian login email.

## Start (2–5 minutes)
1. Log in to your GitHub account.
2. Open this repo on GitHub.
3. Click the green **Code** button → Switch to **Codespaces** tab → Click **three dots "..."** → Select **New with options...**.
4. In the Codespace creation UI, enter the Codespace Secrets:
   - **FORGE_EMAIL** = your Atlassian login email
   - **FORGE_API_TOKEN** = your Atlassian API token
5. Select the **Create codespace** button.
6. Wait for setup to complete. The container installs the Forge CLI automatically.

## Verify and Log In
In the terminal (already open in your Codespace):
```bash
forge --version
forge login --email "$FORGE_EMAIL" --token "$FORGE_API_TOKEN"
```

**Note:** The `forge login` command may display an error message like this, but it actually worked:
```
✕ Logging you in...

Error: The CLI couldn't securely store your login credentials in a local keychain. Ensure you have libsecret installed. If a local keychain is not available, use environment variables before trying again. See https://go.atlassian.com/dac/platform/forge/getting-started/#log-in-with-an-atlassian-api-token for more.
```

```bash
forge whoami
```

## Create and Run a Sample App
If you don’t have a project yet:
```bash
forge create
# Answer prompts to choose a template
forge deploy
forge install
```
After install, follow the CLI’s instructions to open your app or test it in your Atlassian site.

## Common Commands
```bash
# Rebuild the dev container if something goes wrong
Dev Containers: Rebuild Container

# Deploy changes
forge deploy

# View currently logged-in account
forge whoami

# Help
forge help
```

## Troubleshooting
- Login errors: Double-check `FORGE_EMAIL` and `FORGE_API_TOKEN` in Codespaces Secrets.
- CLI not found: Run `npm i -g @forge/cli` then `forge --version`.
- Build issues: Use the command palette → “Codespaces: Rebuild Container”.
- Network hiccups: Retry the command; Codespaces can briefly throttle during heavy workshop usage.

## How this works
- This repo contains `.devcontainer/devcontainer.json` using the official `atlassian/forge-devcontainer` image.
- VS Code extensions and shell are preconfigured.
- Secrets stay in your Codespace and are never committed to the repo.

## Privacy & Security
- Never commit secrets to the repository.
- Remove secrets from your Codespace after the workshop if desired.
- API tokens can be revoked anytime at https://id.atlassian.com/manage/api-tokens.
