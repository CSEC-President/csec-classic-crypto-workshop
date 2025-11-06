# CSEC Classic Cryptography Workshop

A hands-on introduction to breaking the Vigenère cipher through cryptanalysis in Python.

## Prerequisites

- **Python 3.8+** - If not installed, see: https://www.python.org/downloads/
- **Jupyter Notebook** - Will be installed in setup, official installation instructions can be found here: https://jupyter.org/install
- Basic Python knowledge (reading the reference sheet from this document)
- macOS, Windows, or Linux

## Workshop Structure

This workshop teaches cryptanalysis by implementing attacks on the Vigenère cipher. 
All work is done in a Jupyter notebook where you implement the cryptanalysis techniques.

---

## Quick Start

### Install Jupyter Notebook

```bash
# Install Jupyter
pip3 install jupyter

# Verify installation
jupyter --version
```

---

## Launch Workshop

```bash
# Clone the workshop repo
git clone https://github.com/CSEC-President/csec-classic-crypto-workshop

# Navigate to workshop directory
cd /path/to/workshop

# Launch Jupyter
jupyter notebook
```

This opens your browser at http://localhost:8888

Open `vigenere_workshop.ipynb` in the file browser and _follow the instructions_.

---

## After Setup

 In Jupyter:
 - Shift+Enter runs current cell
 - Cells run in order from top to bottom
 - Kernel → Restart to reset everything

---

## Basic Python Reference

Essential Python for the workshop:

### Strings and Characters
```python
# String operations
text.upper()                    # Convert to uppercase
text.lower()                    # Convert to lowercase
''.join(list_of_chars)          # Join list into string
text.split()                    # Split into words

# Character operations
ord('A')                        # Get ASCII value (65)
chr(65)                         # Get character from ASCII ('A')
char.isalpha()                  # Check if letter

# Looping through string
for char in text:
    print(char)

for i, char in enumerate(text):
    print(f"Position {i}: {char}")
```

### Lists
```python
# Lists
my_list = [1, 2, 3]
my_list.append(4)              # Add to end
my_list[0]                     # First element
len(my_list)                   # Length

# List comprehension
squares = [x**2 for x in range(10)]
filtered = [x for x in my_list if x > 2]

# Slicing
my_list[start:end:step]        # Slice with step
my_list[::3]                   # Every 3rd element
```

### Dictionaries
```python
# Creating dictionaries
my_dict = {'a': 1, 'b': 2}

# Accessing
my_dict['a']                   # Get value
my_dict.get('a', 0)           # Get with default
my_dict.keys()                 # All keys
my_dict.values()               # All values

# Looping
for key, value in my_dict.items():
    print(f"{key}: {value}")

# Finding max by value
max(my_dict, key=my_dict.get)
```

### Counter (for frequency analysis)
```python
from collections import Counter

# Count frequencies
freq = Counter("hello world")
freq['l']                      # Returns 3
freq.most_common(3)            # Top 3 most common

# Usage example
text = "ABCABC"
letter_freq = Counter(text)
most_common_letter = letter_freq.most_common(1)[0][0]
```

### Math Operations
```python
# Basic math
a % b                          # Modulo (remainder)
a // b                         # Integer division

# GCD 
from math import gcd
gcd(12, 8)                     # Greatest common divisor

# GCD of multiple numbers
from functools import reduce
result = reduce(gcd, [12, 8, 16])
```

### Common Patterns
```python
# Filter non-alphabetic characters
clean = ''.join(c for c in text if c.isalpha())

# Get every nth character (for splitting by key position)
group = text[start::key_length]

# Count occurrences
text.count('ABC')
```

---

## Troubleshooting

### Jupyter Issues

**Problem:** `jupyter: command not found`
```bash
python3 -m jupyter notebook
```

**Problem:** Port 8888 already in use
```bash
jupyter notebook --port 8889
```

**Problem:** Kernel keeps dying
- Restart the kernel: Kernel → Restart

**Problem:** Cell output is missing
- Click "Kernel → Restart & Run All"

### Python Issues

**Problem:** Import errors
```bash
# Check Python version (should be 3.8+)
python3 --version
```

**Problem:** Functions not found
- Make sure you ran all previous cells in order
- Restart kernel and run from beginning

---

## Alternative: Using Google Colab

To use without installing Jupyter locally:

1. Go to https://colab.research.google.com/
2. File → Upload notebook
3. Upload `vigenere_workshop.ipynb`
4. Run cells normally

---

## Disclaimer

**Ethical Guidelines**: Never attempt to decrypt communications without authorization. Report vulnerabilities responsibly. Use knowledge to understand security, not to violate it.

**Your Responsibility**: You are solely responsible for your actions. The instructor and workshop organizers accept no responsibility for:
- Hardware issues, data loss, or system instability
- Unauthorized decryption of communications or breaking into systems
- Legal consequences of misuse or any malicious use of techniques learned

By participating, you acknowledge understanding these terms and agree to use this knowledge ethically and legally.
---

## Additional Resources

- [CryptoHack](https://cryptohack.org/) - Interactive cryptography CTF-style challenges
- [Cryptopals Challenges](https://cryptopals.com/) - Practical cryptography exercises
- [Khan Academy: Cryptography](https://www.khanacademy.org/computing/computer-science/cryptography) - Modern Cryptography section
- [CyberChef](https://gchq.github.io/CyberChef/) - Useful toolkit for cryptoanalysis
- "Introduction to Modern Cryptography" by Jonathan Katz
- [Elementary Group Theory for Programmers](https://rareskills.io/post/group-theory) - Mathematical foundations for modern cryptography
---

Authors: Clarence Lam, Sasha Zyuzin

Good luck! 🔐