```BASH
#!/bin/bash
```

# Bash

## Globbing
Come Bash espande alcuni gruppi di caratteri (_Bash non supporta le regx_)
* __?__ un qualsiasi singolo carattere: `ls miofile.???`
* __*__ zero o più caratteri: `cat *.c`
* __.__ punto __non è__ un carattere di globbing

* __[ ]__ definisce un range di valori `[a-z]` o `[:upper:]` : `[0-9]*` inizia con un numero: `[abc]` __uno__ dei valori _a b c_
* __$__ individua l'ultimo carattere `grep x$ miofile.txt`
* __^__ individua il primo carattere `grep ^[abc] miofile.txt`

* __{ }__ Espansione delle `{2..5}` _2 3 4 5 6 7_ `ls *.{c,o,h}` 

## Modifica file system
__cp__ copia file -R 
