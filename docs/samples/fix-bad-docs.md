# Installation Guide

**Prerequisite:** Node.js version 18 or higher.

1. Install the package globally by running the following command in your terminal:
    ```bash
    npm install -g my-db-cli
    ```
2. Verify the installation:
    ```bash
    my-db-cli --version
    ```
    If installed successfully, the terminal will display the current version number.

---

# Obtaining an API Key

An API key is required to use our weather service API. You will need a developer account to generate a key. 

If you do not have an account, follow the registration steps below. If you already have an account, skip directly to [Generating an API key](#generating-an-api-key).

## Registering for an Account

1. Fill out the sign-up form on the **Developer Portal**.
2. Click the verification link sent to your email to activate your account.

## Generating an API Key

> **IMPORTANT:** For security reasons, your API key will **only be shown once**. If you lose it, you will need to generate a new key.

1. Log in to the **Developer Portal**.
2. Navigate to the **Dashboard** and click **Generate Key**.
3. Copy the API key and save it somewhere safe (such as a password manager or environment variable). Your key will **never be shown again**.