# Uncompyle-Pyxie POC
This is a patched version of uncompyle2 that has been modified to decompile the pyx bytecode from the PyXie RAT write up.

## Modifications
The following modifications have been made to get this to work with PyXie bytecode:
* Patched _load_file() to skip the version check and load the code object from the begining of the file.
* Added a copy of the Python 2.7 dis.py to uncompyle2 directory. This ultimately forces uncompyle2 to attempt to load opcode.py from this directoy.
* Added a copy of the Python 2.7 opcode.py and modified it to redefine the known remapped opcodes. 

## Usage
Python 2.7 is required to run this
```
python uncompyle2.py pyXie_bytecode.pyx
``` 



## Ref: 
Uncompyle2 -  https://github.com/wibiti/uncompyle2

PyXie write up -  https://threatvector.cylance.com/en_us/home/meet-pyxie-a-nefarious-new-python-rat.html
