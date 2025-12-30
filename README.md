# Vigenère Cipher 🔐

A minimal, well-tested implementation of the classic Vigenère cipher with an
installable command-line interface (CLI) and a small importable Python module.

- Purpose: educational utility and lightweight library for encoding/decoding
  text with a repeating-key Vigenère cipher. Preserves letter case and leaves
  non-letter characters unchanged.
- License: MIT

---

## Features

- Clean, documented implementation in `vigenere_cipher.py`.
- CLI: `vigenere` (installed as an entry point) supporting `--encode`/`--decode`.
- Keyword validation: only ASCII alphabetic keywords are accepted.
- Unit tests with `pytest` and type checks with `mypy`.
- GitHub Actions workflow for CI (black, mypy, pytest).

---

## Installation

Clone the repository and install in editable (development) mode:

```bash
git clone <repo-url>
cd vigenere-cipher
pip install -e .
```

You can also install the development tools:

```bash
pip install -r requirements-dev.txt
```

Supported Python versions: 3.8+

---

## Usage

### CLI

Encode a message:

```bash
vigenere --encode --keyword KEY --message "Hello, World!"
```

Decode a message:

```bash
vigenere --decode --keyword KEY --message "ciphertext"
```

Read from stdin (useful in scripts or pipelines):

```bash
echo "text" | vigenere --encode --keyword key
```

If the `vigenere` console script is not on your PATH (Windows/Powershell
limitations), run the module directly:

```bash
python -m vigenere_cipher --help
```

### Importing the library

Use the module directly from Python code:

```python
from vigenere_cipher import vigenere_encode, vigenere_decode

cipher = vigenere_encode("Hello, World!", "key")
plain = vigenere_decode(cipher, "key")
```

Behavior notes:
- `keyword` must be a non-empty string of ASCII letters (A–Z, a–z).
- Case of alphabetic characters is preserved; punctuation and numbers are left unchanged.

---

## Tests & Quality

Run the test suite using `pytest`:

```bash
python -m pytest -q
```

Code formatting and style:

- Black is used for formatting (configuration in `pyproject.toml`).
- `mypy` is configured for lightweight static typing checks.

CI is configured in `.github/workflows/ci.yml` to run black, mypy and pytest on push/PR.

---

## Contributing

Contributions are welcome — please open issues or PRs. Suggested ways to help:

- Add more tests, edge cases, or property-based tests (Hypothesis).
- Improve CLI features (file input/output, encoding options).
- Add packaging metadata and release automation.

Please follow the existing style (Black + type hints) and add tests for new behaviors.

---

## License

This project is licensed under the MIT License. See `LICENSE` for details.

---