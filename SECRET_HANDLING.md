# Secret Handling Guidelines

This document outlines the guidelines for handling sensitive information such as API keys, passwords, and other secrets in the AutoResearcher project.

## Overview

The AutoResearcher project requires several API keys to function properly:

- Gemini API Key (from Google)
- Tavily API Key (for web search)
- Google Cloud Project ID
- Service Account JSON (for Google Cloud authentication)

## Best Practices

### 1. Never Hardcode Secrets

- Do not include API keys or other secrets directly in the code.
- Avoid committing secrets to version control.

### 2. Use Environment Variables or Secrets Management

- On Kaggle: Use the "Secrets" feature in the notebook settings.
- On Google Colab: Use the "Secrets" feature or prompt for input using `getpass`.
- For local development: Use environment variables or a `.env` file (ensure `.env` is in `.gitignore`).

### 3. Secure Storage

- Store secrets securely using platform-provided secret management tools.
- Rotate API keys regularly.
- Limit the scope of service accounts and API keys to only necessary permissions.

### 4. Code Examples

When sharing code or notebooks, use placeholders for secrets:

```python
# Instead of:
# gemini_api_key = "your-actual-key-here"

# Use:
import os
gemini_api_key = os.getenv('GEMINI_API_KEY') or input('Enter Gemini API Key: ')
```

Or for Kaggle/Colab:

```python
from kaggle_secrets import UserSecretsClient
user_secrets = UserSecretsClient()
gemini_api_key = user_secrets.get_secret("GEMINI_API_KEY")
```

### 5. Reporting Security Issues

If you discover a security vulnerability or accidentally expose a secret:

1. Immediately revoke the exposed secret.
2. Notify the project maintainer.
3. Update any affected code to use secure methods.

## Compliance

This project aims to comply with security best practices. Contributors are expected to follow these guidelines to maintain the security and integrity of the project.