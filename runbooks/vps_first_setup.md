# VPS First Setup

## Purpose

Prepare a fresh Hostinger VPS to run Varona Expense OS.

This only needs to be done once per VPS.

## Assumed OS

Recommended:

```txt
Ubuntu 22.04 LTS or Ubuntu 24.04 LTS
```

## 1. Connect to the VPS

From your computer:

```bash
ssh root@YOUR_VPS_IP
```

If your user is not root:

```bash
ssh YOUR_USER@YOUR_VPS_IP
```

## 2. Update packages

```bash
sudo apt update && sudo apt upgrade -y
```

## 3. Install Docker

```bash
curl -fsSL https://get.docker.com | sh
```

## 4. Enable Docker

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

## 5. Check Docker

```bash
docker --version
docker compose version
```

## 6. Create Varona directory

```bash
sudo mkdir -p /opt/varona
sudo chown -R $USER:$USER /opt/varona
```

## 7. Add GitHub Actions SSH key

Generate an SSH key locally or in a secure place.

The public key must be added to the VPS:

```bash
mkdir -p ~/.ssh
nano ~/.ssh/authorized_keys
```

Paste the public key.

Then:

```bash
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

The private key goes into GitHub Secret:

```txt
VPS_SSH_KEY
```

## 8. Firewall

For TEST:

```bash
sudo ufw allow 7331/tcp
```

For PROD:

```bash
sudo ufw allow 7332/tcp
```

For SSH:

```bash
sudo ufw allow OpenSSH
```

Enable firewall:

```bash
sudo ufw enable
sudo ufw status
```

Hostinger may also have a firewall in its control panel. Make sure ports 22, 7331 and 7332 are allowed there if needed.

## 9. First Deployment

After GitHub Secrets are configured:

```txt
GitHub → Actions → Deploy Varona Expense OS → Run workflow → test
```

Then open:

```txt
http://YOUR_VPS_IP:7331
```

## 10. Production

Only deploy PROD after TEST works with sample documents.

PROD will be available at:

```txt
http://YOUR_VPS_IP:7332
```

## Security Notes

- Do not upload sensitive company documents until login/auth is configured.
- Keep GitHub repository private.
- Use strong passwords and secrets.
- Start with TEST only.
