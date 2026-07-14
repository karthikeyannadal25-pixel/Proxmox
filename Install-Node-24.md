For **Ubuntu 24.04**, the recommended way to install **Node.js 24 (LTS)** is using the official NodeSource repository.

## Step 1: Update the system

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Step 2: Install required packages

```bash
sudo apt install -y curl ca-certificates gnupg
```

---

## Step 3: Add the Node.js 24 repository

```bash
curl -fsSL https://deb.nodesource.com/setup_24.x | sudo -E bash -
```

This will add the Node.js 24 repository to your system.

---

## Step 4: Install Node.js

```bash
sudo apt install -y nodejs
```

---

## Step 5: Verify the installation

Check Node.js version:

```bash
node -v
```
Check npm version:

```bash
npm -v
```

---

## Step 6: Verify the installation path

```bash
which node
which npm
```

Expected output:

```text
/usr/bin/node
/usr/bin/npm
```

---
