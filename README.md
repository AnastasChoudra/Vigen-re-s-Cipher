# Vigenère Cipher

Small project implementing a Vigenère cipher with an installable CLI.

## Install

- Editable/development install:

```bash
pip install -e .
```

## Usage

Encode:

```bash
vigenere --encode --keyword KEY --message "Hello, World!"
```

Decode:

```bash
vigenere --decode --keyword KEY --message "ciphertext"
```

Or read from stdin:

```bash
echo "text" | vigenere --encode --keyword key
```
