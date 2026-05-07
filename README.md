[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=1231198740)

> **This repository is automatically synced from [elabit/robotmk-starter](https://github.com/elabit/robotmk-starter/tree/main/examples/web-webshop).**
> Do not edit files here directly — changes will be overwritten on the next sync.
> Last sync: [`8831cda`](https://github.com/elabit/robotmk-starter/commit/8831cda318b5255ce6dedb9c71b0ce82b41f0cf8)

---
# web-webshop

Full checkout-flow example using [robotframework-browser](https://robotframework-browser.org) and
[robotframework-crypto](https://github.com/Snooz82/robotframework-crypto), driven by the
Robotmk **multi-profile** feature.
The same suite runs once per user profile with profile-specific encrypted credentials.

## What This Demonstrates

- Robotmk **multi-profile** execution: one `robot.toml` defines three user profiles (`JaneDoe`, `JackHowe`, `BobSmith`)
- Per-profile `extend-variables` override `USER_EMAIL`, `USER_PASSWORD`, and `USER_NAME`
- Encrypted passwords via CryptoLibrary — `crypt:…` values stored directly in `robot.toml`
- A real checkout flow modularised across multiple keyword resource files (`Resources/`)
- Dynamic `output-dir` with a timestamp expression in `robot.toml`

## Test Cases

| Test Case | Description |
|---|---|
| `User Can Reach Checkout Page` | Logs in as the configured user, adds items to the cart, and completes checkout |

The suite is executed **three times** — once per profile (JaneDoe, JackHowe, BobSmith) — each
with its own credentials and a timestamped output directory.

## Key Files

| File | Purpose |
|---|---|
| `webshop.robot` | Main suite: login → add items to cart → checkout |
| `robot.toml` | Multi-profile config with 3 user profiles and encrypted passwords |
| `conda.yaml` | Environment (Python `3.12`, Browser `19.14.2`, Crypto `0.3`) |
| `keys/private_key.json` | Demo private key for credential decryption |
| `Resources/authentication.resource` | `Login As User` keyword |
| `Resources/catalog.resource` | `Add Item To Cart` / `Add Items To Cart` keywords |
| `Resources/cart.resource` | `Open Cart` keyword |
| `Resources/checkout.resource` | `Fill Billing Address` / `Execute Payment` keywords |
| `.devcontainer/devcontainer.json` | Devcontainer with noVNC desktop for headed browser testing |

## Links

- [Practice Software Testing – Webshop](https://practicesoftwaretesting.com)
- [robotframework-browser](https://robotframework-browser.org)
- [robotframework-crypto](https://github.com/Snooz82/robotframework-crypto)
- [Robotmk Homepage](https://robotmk.org)


## Prerequisites

**RCC**  to create isolated self contained environments. Download from the [Robotmk release page](https://github.com/elabit/robotmk/releases/download/v4.0.0/) or use the provided script (`_dev/scripts/download-rcc.sh` / `download-rcc.ps1`).
  
## Libraries & Versions

| Library | Version |
|---|---|
| Python | `3.12` |
| Node.js | `22.11.0` |
| Robot Framework | `7.4` |
| robotframework-browser | `19.14.2` |
| robotframework-crypto | `0.3` |



## How to Run

### On the console

Run directly with RCC (creates the isolated environment on first run):

```bash
rcc task script --robot robot.yaml -- robot suite.robot
```

### In VS Code / Locally

Create and activate the environment, then open VS Code from the activated environment: 

```bash
rcc task shell
code . 
```

Install the [RobotCode](https://marketplace.visualstudio.com/items?itemName=d-biehl.robotcode) extension for VS Code to run the robot with the integrated run/debug tools.  
**This is the recommended way for the implementation of Robot Framework suites.**

### In VS Code / Devcontainer

Just press the button below. RCC is pre-installed, will create the environment and activate it for VS Code. 

## Closing Notes

Also try the other RF example suites, they all work in the Codespace environment.  

This is only the beginning of the journey, there is a lot more to explore in the world of Robot Framework, Robotmk and Checkmk.  

If you want to learn more, there are several ways of how we can support you:

- [Synthetic Monitoring Trainings](https://lp.robotmk.org/robotmk-masterclass-4d-en)
- Implementing a **Robotmk POC** in your company
- Know How Transfer
- Code Review of existing Tests & Coaching Sessions
- "Extended Workbench" - We work together on your test automation projects for a defined period of time

Reach out to us via mail at robotmk.org or book a free [clarification call](https://meet.brevo.com/simon-meggle).

**Simon Meggle**  
*CEO Elabit GmbH*  
*Founder of Robotmk*  
*Product Manager of Synthetic Monitoring at Checkmk*

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=1231198740)
