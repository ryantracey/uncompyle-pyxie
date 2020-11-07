# Uncompyle-Pyxie POC
This is a patched version of uncompyle2 that has been modified to decompile the pyx bytecode from the BlackBerry Cylance and Palo Alto Networks PyXie RAT write ups.

## Modifications
The following modifications have been made to get this to work with PyXie bytecode:
* Patched _load_module() to skip the version check and load the code object from the begining of the file.
* Added a copy of the Python 2.7 dis.py to uncompyle2 directory. This ultimately forces uncompyle2 to attempt to load opcode.py from this directoy.
* Added a copy of the Python 2.7 opcode.py and modified it to redefine the known remapped opcodes. 

## Usage
Python 2.7 is required to run this

Depending on what variant of PyXie you are decompiling, you will need to replace the "opcodes.py"  in the "uncompyle2" directory with the appropriate one from the "PyXie Opcodes" directory. 

```
python uncompyle2.py pyXie_bytecode.pyx
``` 



## Ref: 
Uncompyle2 -  https://github.com/wibiti/uncompyle2

Palo Alto Networks Unit42 write up - Palo Alto Networks Unit42 write up - Unit 42 
BlackBerry Cylance write up -  https://threatvector.cylance.com/en_us/home/meet-pyxie-a-nefarious-new-python-rat.html
