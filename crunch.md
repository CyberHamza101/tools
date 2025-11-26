# Crunch Wordlist Generator

## 📌 Overview

Crunch is a command-line tool used to generate custom wordlists for password attacks. It allows you to define patterns, lengths, character sets, and output rules to create highly targeted dictionaries.

Crunch is especially useful in:

* **Brute force attacks**
* **Password auditing**
* **Wireless security testing** (with tools like Aircrack-ng)
* **Custom rule-based wordlist generation**

---

## ⚙️ Installation

Crunch usually comes pre-installed in penetration testing distributions such as **Kali Linux**. If it is not installed, you can install it using:

```bash
sudo apt install crunch
```

Verify installation:

```bash
crunch --version
```

---

## 🧩 Basic Usage

The simplest form of Crunch requires two numbers:

```bash
crunch <min-length> <max-length>
```

Example: generate all combinations from 3 to 5 characters using default charset:

```bash
crunch 3 5
```

---

## 🔤 Custom Character Sets

You can define your own characters:

```bash
crunch 4 4 abc123
```

This generates every possible 4‑character combination from `a b c 1 2 3`.

---

## 🎯 Output to a File

Save the wordlist to a file using `-o`:

```bash
crunch 6 6 abc123 -o wordlist.txt
```

---

## 🧠 Using Patterns

Crunch supports **patterns** with the `-t` flag.

### Pattern Symbols

* `@` → lowercase letters
* `,` → uppercase letters
* `%` → numbers
* `^` → symbols

### Example

```bash
crunch 8 8 -t @@%%^^%%
```

This produces words matching the pattern (two lowercases, two numbers, two symbols, two numbers).

---

## 📌 Combining Character Sets and Patterns

You can define custom characters using `-p` (no repetition) or `-t` with a charset.

Example using `-t` with custom characters:

```bash
crunch 6 6 -t @@123@! -o custom.txt
```

---

## 🚀 Generating Wordlists Using -p (Permutation Mode)

`-p` generates all permutations of the given words **without repeating characters**.

Example:

```bash
crunch 1 1 -p admin 123
```

This generates permutations from the words `admin` and `123`.

---

## 📂 Output Redirection for Large Files

Crunch can produce massive files, so you can pipe output directly into another tool:

Example with Aircrack-ng:

```bash
crunch 8 8 abc123 | aircrack-ng -w - capture.cap
```

---

## 📁 Changing Output Encoding

Crunch supports different encodings:

```bash
crunch 4 4 -e ascii
```

---

## 📝 Useful Examples

Generate 8-digit numbers only:

```bash
crunch 8 8 0123456789
```

Generate lowercase-only passwords of length 5:

```bash
crunch 5 5 abcdefghijklmnopqrstuvwxyz
```

Generate a complex password list matching a structure:

```bash
crunch 10 10 -t %%@@^^,,%%
```

---

## ⚠️ Notes

* Crunch can produce extremely large files — monitor disk space.
* Using targeted rules gives much better results than brute force.
* Always use Crunch ethically and only on systems you are authorized to test.

---

