# Infrastructure Setup Scripts

Quick reference for provisioning and managing Azure infrastructure for this lab.

## Scripts Overview

| Script | Purpose |
|--------|---------|
| `1-setup.sh` | Clone template repository and provision Azure infrastructure |
| `2-setup-env.sh` | Configure environment variables for local development |
| `3-teardown.sh` | Delete all provisioned Azure resources |

## Usage

### 1. Initial Setup & Provisioning

```bash
./1-setup.sh
```

**What it does:**
- Clones the ForBeginners repository template
- Creates an Azure Developer CLI (azd) environment
- Configures AI model settings (with confirmation prompts)
- Provisions Azure infrastructure (does NOT deploy the application)

**Note:** After this completes, you'll need to manually run `azd up` if you want to deploy the application.

### 2. Environment Configuration

```bash
source ./2-setup-env.sh
```

**What it does:**
- Exports Azure resource connection strings and endpoints as environment variables
- Required before running local lab exercises

**Important:** Use `source` (not `./`) to ensure variables are set in your current shell.

### 3. Cleanup (Optional)

```bash
./3-teardown.sh
```

**What it does:**
- Removes all Azure resources created during setup
- Use this when you're done with the lab to avoid ongoing charges

## Quick Start

For most learners, run scripts in this order:

```bash
# 1. Provision infrastructure
./1-setup.sh

# 2. Set environment variables
source ./2-setup-env.sh

# 3. Complete your lab exercises

# 4. Clean up when done
./3-teardown.sh
```

## Agent Setup

**To complete your lab exercises, create an AI Agent**
1. Create a new Agent in the Foundry Portal
1. Set its name to "zava-customer-support"
1. Set its description to "You are Cora, a polite and helpful chatbot for Zava, an enterprise retailer of Home Improvement goods for DIY enthusiats"
1. Set its instructions as follows:

    ```
    You are a customer support chatbot for the Zava Home Improvement retail store.
    You are polite and helpful in your answers.
    You follow all legal and ethical guidelines.

    You always start by acknowledging the user's question with a cheerful phrase.  prefixed with an emoji related to the topic.
    For instance: "🔫Love this DIY project!"

    You then answer the question with a brief and factual answer (1-2 sentences max)

    Then you end with a helpful question that can guide the customer towards their goal.
    ```
