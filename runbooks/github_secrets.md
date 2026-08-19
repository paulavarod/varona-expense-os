# GitHub Secrets

## Purpose

These secrets allow GitHub Actions to deploy Varona Expense OS to the Hostinger VPS without exposing credentials in the repository.

## Where to add them

In GitHub:

```txt
Repository → Settings → Secrets and variables → Actions → New repository secret
```

Add each secret exactly with the names below.

## Required VPS Secrets

### VPS_HOST

The public IP address or hostname of the VPS.

Example:

```txt
123.123.123.123
```

### VPS_USER

The SSH user used to connect to the VPS.

Examples:

```txt
root
ubuntu
paula
```

### VPS_SSH_KEY

The private SSH key that GitHub Actions will use to connect to the VPS.

This must include the full private key block:

```txt
-----BEGIN OPENSSH PRIVATE KEY-----
...
-----END OPENSSH PRIVATE KEY-----
```

Do not commit this value to the repository.

### VPS_PORT

Usually:

```txt
22
```

Use a different value only if the VPS SSH port was changed.

## Required App Secrets

### POSTGRES_PASSWORD

Strong password for PostgreSQL.

Use a long random string.

### BETTER_AUTH_SECRET

Long random secret used by TaxHacker authentication.

Use a long random string.

Example format:

```txt
at-least-32-random-characters
```

## AI Provider Secrets

At least one AI provider should be configured.

### OPENAI_API_KEY

OpenAI API key.

Recommended first option if using OpenAI extraction.

### GOOGLE_API_KEY

Google Gemini API key.

Alternative to OpenAI.

### MISTRAL_API_KEY

Mistral API key.

Alternative provider.

## Recommended Initial Setup

For the first deployment, add:

```txt
VPS_HOST
VPS_USER
VPS_SSH_KEY
VPS_PORT
POSTGRES_PASSWORD
BETTER_AUTH_SECRET
OPENAI_API_KEY
```

You can leave these empty if not used:

```txt
GOOGLE_API_KEY
MISTRAL_API_KEY
```

## Important Security Notes

- Never paste secrets into normal Markdown files.
- Never commit `.env` files.
- Keep the repository private before using real documents.
- Use TEST first before PROD.
