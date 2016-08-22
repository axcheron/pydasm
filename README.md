# pydasm

I had some trouble compiling **pydasm** on recent Windows platforms. This "slightly" modified version should works on
Windows 7/8/10 (Only tested on Windows 10).

**pydasm** is a python wrapper for [libdasm](https://github.com/axcheron/libdasm).

## Installation

First, install [Microsoft Visual C++ Compiler for Python 2.7 ](https://www.microsoft.com/en-us/download/details.aspx?id=44266)

```bash
git clone https://github.com/axcheron/pydasm
python setup.py install
```

Also, if you don't already have it, you can find the last version of [Python 2.7 here](https://www.python.org/download/releases/2.7/).

## Usage

```python
import pydasm

buffer = '\x90\x31\xc9\x31\xca\x31\xcb'

offset = 0
while offset < len(buffer):
   i = pydasm.get_instruction(buffer[offset:], pydasm.MODE_32)
   print pydasm.get_instruction_string(i, pydasm.FORMAT_INTEL, 0)
   if not i:
     break
   offset += i.length
```

## Credits

Thanks to jt, skape, thief, spoonm and fine folks @nologin responsible for libdasm !
Special thanks to ero for creating and contributing pydasm.

## License

This project is released under the BSD license. See LICENCE.