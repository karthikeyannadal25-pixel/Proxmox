# Enable Root Login
## Step 1: Login to the VM Console

If you logged in as a normal user:

```bash
sudo -i
```

---

## Step 2: Edit the SSH Configuration

Open the SSH configuration file:

```bash
nano /etc/ssh/sshd_config
```

Find one of these lines:

```text
#PermitRootLogin prohibit-password
```
Change it to:

```text
PermitRootLogin yes
```

---

## Step 3: Enable Password Authentication (if needed)

Find:

```text
PasswordAuthentication no
```

Change it to:

```text
PasswordAuthentication yes
```
---

## Step 4: Save the File

In Nano:

* **Ctrl + O** → Save
* **Enter**
* **Ctrl + X** → Exit

---

## Step 5: Restart SSH

Ubuntu/Debian:

```bash
systemctl restart ssh
```

or

```bash
systemctl restart sshd
```
---

## Step 6: Set a Root Password (if needed)

If root has no password:

```bash
passwd root
```

Enter your new password.

### Quick Command Summary

```bash
sudo -i
nano /etc/ssh/sshd_config

# Change:
PermitRootLogin yes
PasswordAuthentication yes

systemctl restart ssh

passwd root

ssh root@<VM_IP>
```
