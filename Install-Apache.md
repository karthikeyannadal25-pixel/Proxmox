# Apache Install
## Step 1: Update the package list

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Step 2: Install Apache

```bash
sudo apt install apache2 -y
```

---

## Step 3: Start Apache

```bash
sudo systemctl start apache2
```

Enable Apache to start automatically after reboot:

```bash
sudo systemctl enable apache2
```

---

## Step 4: Check Apache status

```bash
sudo systemctl status apache2
```

You should see something like:

```
Active: active (running)
```

Press **Q** to exit the status screen.

---

## Step 5: Allow Apache through the firewall (if UFW is enabled)

Check firewall status:

```bash
sudo ufw status
```

If active:

```bash
sudo ufw allow 'Apache Full'
sudo ufw reload
```

Verify:

```bash
sudo ufw status
```

---

## Step 6: Test Apache

Find your server's IP:

```bash
curl ifconfig.me
```

or

```bash
hostname -I
```

Open in your browser:

```
http://YOUR_SERVER_IP
```

You should see the **Apache2 Ubuntu Default Page**.

---

## Step 7: Verify Apache is listening

```bash
sudo ss -tulpn | grep :80
```

Expected output:

```
LISTEN 0 511 *:80
```

---

## Step 8: Check Apache version

```bash
apache2 -v
```

Example:

```
Server version: Apache/2.4.x (Ubuntu)
```

---

# Useful Apache commands

Start:

```bash
sudo systemctl start apache2
```

Stop:

```bash
sudo systemctl stop apache2
```

Restart:

```bash
sudo systemctl restart apache2
```

Reload configuration:

```bash
sudo systemctl reload apache2
```

View status:

```bash
sudo systemctl status apache2
```

---

# Important directories

Apache installation:

```
/etc/apache2/
```

Document root:

```
/var/www/html
```

Main configuration:

```
/etc/apache2/apache2.conf
```

Virtual hosts:

```
/etc/apache2/sites-available/
/etc/apache2/sites-enabled/
```

Apache logs:

```
/var/log/apache2/access.log
/var/log/apache2/error.log
```

---

## Install commonly used Apache modules

```bash
sudo a2enmod rewrite
sudo a2enmod headers
sudo a2enmod ssl
sudo a2enmod proxy
sudo a2enmod proxy_http
sudo a2enmod proxy_wstunnel
sudo systemctl restart apache2
```

---

If your goal is to host **Spring Boot**, **React**, or **Node.js** applications (as you've been working with those), I can also help you configure Apache as a reverse proxy and set up virtual hosts.
