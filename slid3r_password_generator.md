# Slid3r Password Generator 🔐

A secure Bash one-liner that generates a **32-character password** including:
- Uppercase letters
- Lowercase letters
- Numbers
- **Exactly one underscore**, randomly placed

No dependencies. No fluff. Just pure shell magic.

---

## 🧠 The One-Liner

```bash
< /dev/urandom tr -dc 'A-Za-z0-9' | head -c31 | awk '{print $0 "_"}' | fold -w1 | shuf | tr -d '\n'; echo
```

---

## 💻 Usage Options

### 🔹 Option 1: Bash/Zsh Function

Add the following to your `~/.bashrc` or `~/.zshrc`:

```bash
slid3r_pw() {
  < /dev/urandom tr -dc 'A-Za-z0-9' | head -c31 | awk '{print $0 "_"}' | fold -w1 | shuf | tr -d '\n'; echo
}
```

Then run it anytime with:
```bash
slid3r_pw
```

---

### 🔹 Option 2: Standalone Script

Create a script file at `~/bin/slid3r_pw`:

```bash
#!/bin/bash
< /dev/urandom tr -dc 'A-Za-z0-9' | head -c31 | awk '{print $0 "_"}' | fold -w1 | shuf | tr -d '\n'; echo
```

Make it executable:
```bash
chmod +x ~/bin/slid3r_pw
```

Add your bin to the PATH (if not already):

```bash
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

Now run:
```bash
slid3r_pw
```

---

### 🔹 Option 3: System-Wide Install

Make it available for all users:

```bash
sudo cp ~/bin/slid3r_pw /usr/local/bin/
```

Then anyone on the system can run:
```bash
slid3r_pw
```

---

## 🏴‍☠️ Author

**Jim “Slid3r” Harris**  
_“May your underscores always land where chaos reigns.”_

---

## ☠️ License

MIT — or pirate it freely, you rogue.
