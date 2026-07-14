# Install Java 21
## Step 1: Update the Package List

```bash
sudo apt update
```

---

## Step 2: Install OpenJDK 21

```bash
sudo apt install openjdk-21-jdk -y
```

---

## Step 3: Verify the Installation

```bash
java -version
```

Expected output:

```text
openjdk version "21.x.x" 2026-xx-xx
OpenJDK Runtime Environment (build 21.x.x)
OpenJDK 64-Bit Server VM (build 21.x.x, mixed mode, sharing)
```

Also verify the compiler:

```bash
javac -version
```

Expected output:

```text
javac 21.x.x
```

---

## Step 4: Check the Installation Path

```bash
readlink -f $(which java)
```

Example output:

```text
/usr/lib/jvm/java-21-openjdk-amd64/bin/java
```

The Java home directory is:

```text
/usr/lib/jvm/java-21-openjdk-amd64
```

---

## Step 5: Set `JAVA_HOME`

Edit your shell configuration:

```bash
nano ~/.bashrc
```

Add these lines at the end:

```bash
export JAVA_HOME=/usr/lib/jvm/java-21-openjdk-amd64
export PATH=$JAVA_HOME/bin:$PATH
```

Save and reload:

```bash
source ~/.bashrc
```

Verify:

```bash
echo $JAVA_HOME
```

Expected output:

```text
/usr/lib/jvm/java-21-openjdk-amd64
```

---
