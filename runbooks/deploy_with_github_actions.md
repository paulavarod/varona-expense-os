# Deploy with GitHub Actions

## Purpose

This runbook explains how to deploy Varona Expense OS from GitHub to the Hostinger VPS.

The deployment uses:

```txt
GitHub Actions
    ↓
SSH to VPS
    ↓
Docker Compose
    ↓
TaxHacker + PostgreSQL
```

## Environments

There are two environments:

```txt
TEST → /opt/varona/expense-test → port 7331
PROD → /opt/varona/expense-prod → port 7332
```

## Deploy TEST

In GitHub:

```txt
Actions → Deploy Varona Expense OS → Run workflow → environment: test
```

Expected result:

```txt
http://YOUR_VPS_IP:7331
```

## Deploy PROD

Only after TEST works.

In GitHub:

```txt
Actions → Deploy Varona Expense OS → Run workflow → environment: prod
```

Expected result:

```txt
http://YOUR_VPS_IP:7332
```

## What the Workflow Does

1. Checks out the repository.
2. Selects `environments/test` or `environments/prod`.
3. Copies Docker files to the VPS.
4. Creates `/opt/varona/expense-test` or `/opt/varona/expense-prod`.
5. Creates `.env` on first deploy from GitHub Secrets.
6. Runs:

```bash
docker compose pull
docker compose up -d
docker compose ps
```

## Important Behavior

If `.env` already exists on the server, the workflow keeps it.

This prevents accidental overwriting of production secrets.

## First Deployment Checklist

Before running the workflow:

- [ ] VPS exists.
- [ ] Docker is installed.
- [ ] GitHub Secrets are set.
- [ ] Repository is private.
- [ ] You deploy TEST first.

## After Deployment

Open:

```txt
http://YOUR_VPS_IP:7331
```

Then:

- Create the first user/login.
- Configure AI provider if needed.
- Upload one test invoice.
- Check extraction.
- Review export.

## Troubleshooting

SSH failure:

- Check `VPS_HOST`.
- Check `VPS_USER`.
- Check `VPS_PORT`.
- Check that `VPS_SSH_KEY` is the private key.
- Check that the public key exists in `~/.ssh/authorized_keys` on the VPS.

Docker failure:

- Check Docker is installed.
- Run manually on VPS:

```bash
docker --version
docker compose version
```

Port not opening:

- Check firewall.
- Check Hostinger panel firewall.
- Check container status:

```bash
cd /opt/varona/expense-test
docker compose ps
docker compose logs app --tail=100
```
