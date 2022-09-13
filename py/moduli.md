# Moduli

| [Indice](readme.md) | [Controllo flusso](flusso.md) | [Funzioni](funzioni.md) | [Strutture dati](strutture.md) | | [Moduli](moduli.md) | | [Strutture dati](strutture.md) | | [Moduli](moduli.md) | | [I/O](io.md)

### Creazione di un modulo
Quando aumenta la complessità di un programma, viene suddiviso in `moduli`. 
Un modulo è un file contiene definizioni e istruzioni. Il nome del file è lo 
stesso del modulo con estensione .py nella directory corrente (per ora ...). 
Supponiamo il modulo fibo che contiene le due funzioni di Fibonacci.
```python
# modulo dei numeri di Fibonacci
def fib(n):                 # stampa i numeri di Fibonacci fino a n
    a, b = 0, 1
    while b < n:
        print(b)
        a, b = b, a + b

def fib2(n):                # ritorna i valori di Fibonacci fino a n
    a, b = 0, 1
    while b < n
        result.append(b)
        a, b = b, a + b
    return result   
```
Qui il modulo è importato
```python
import fibo
fibo.fib(100)           # notazione puntata

fib = fibo.fib          # semplificazione della notazione puntata 

print(fibo.__name__)    # stampa il nome del modulo in formato stringa
```

#### Uso di più moduli
Un modulo può contenere istruzioni esegubili. Queste istruzioni sono eseguite per
inizializzare il modulo. In ogni modo anche le sole funzioni saranno `eseguite` 
creando la tabella dei simboli privata del modulo stesso. Si possono utilizzare anche
le variabili globali del modulo. `nome_modulo.nome_elemento`.
I moduli possono importare altri moduli.
#### Uso notazione form
```python
from fibo import fib2    # importo solo la funzione fib2

from fibo import *       # importo tutti i nomi tranne quelli che iniziano
                         #+ con underscore '_'
```
#### Ricerca dei moduli

La ricerca dei moduli inizia dalla directory corrente, quindi nelle directory specificate
dalla varibile `PYTHONPATH` successivamente si sposta nella directory `/usr/local/lib/python`
(in UNIX).
In effetti tutti i path sono contenuti nella variabile `sys.path`.
```python
>>> import sys
>>> print(sys.path)
... ['/home/lnx/py', '/usr/lib/python38.zip', '/usr/lib/python3.8', '/usr/lib/python3.8/lib-dynload', '/usr/local/lib/python3.8/dist-packages', '/usr/lib/python3/dist-packages']
```
#### File python compilati

Quando si vuole accellarare il `caricamento dei moduli` si produce una versione 
compilata del modulo con il comando `python3 -O`.
Questo comando produce un file con estensione .pyc

#### Moduli standard
Python viene fornito con una libreria di moduli standard. Alcuni sono interni all'interpete
`built-in`, sebbene non facciano parte del nucleo del linguaggio forniscono 
un supporto alle operazioni (accesso al sistema operativo o per garantire efficienza).
```python
>>> import sys
>>> print(sys.ps1)
'>>>'
>>> print(sys.ps2)
'...'
sys.ps1 = 'C>'
C> print(ciao)
ciao
```
Le variabili sys.p1 e sys.ps2 sono disponibili nella modalità interattiva dell'interpete.
```python
import sys
sys.path.append('/home/lnx/py/moduli/') # Aggiungo una mia dir dei moduli
```
#### Funzione dir()
Si ottine una stringa ordinata dei nomi definiti nel modulo
```python
>>> import fibo, sys
>>> dir(fibo)               # non fibo.dir()
['__builtins__', '__cached__', '__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', 'fib', 'fib2']

>>> dir(sys)
['__breakpointhook__', '__displayhook__', '__doc__', '__excepthook__', '__interactivehook__', '__loader__', '__name__', '__package__', '__spec__', '__stderr__', '__stdin__', '__stdout__', '__unraisablehook__', '_base_executable', '_clear_type_cache', '_current_frames', '_debugmallocstats', '_framework', '_getframe', '_git', '_home', '_xoptions', 'abiflags', 'addaudithook', 'api_version', 'argv', 'audit', 'base_exec_prefix', 'base_prefix', 'breakpointhook', 'builtin_module_names', 'byteorder', 'call_tracing', 'callstats', 'copyright', 'displayhook', 'dont_write_bytecode', 'exc_info', 'excepthook', 'exec_prefix', 'executable', 'exit', 'flags', 'float_info', 'float_repr_style', 'get_asyncgen_hooks', 'get_coroutine_origin_tracking_depth', 'getallocatedblocks', 'getcheckinterval', 'getdefaultencoding', 'getdlopenflags', 'getfilesystemencodeerrors', 'getfilesystemencoding', 'getprofile', 'getrecursionlimit', 'getrefcount', 'getsizeof', 'getswitchinterval', 'gettrace', 'hash_info', 'hexversion', 'implementation', 'int_info', 'intern', 'is_finalizing', 'last_traceback', 'last_type', 'last_value', 'maxsize', 'maxunicode', 'meta_path', 'modules', 'path', 'path_hooks', 'path_importer_cache', 'platform', 'prefix', 'ps1', 'ps2', 'pycache_prefix', 'set_asyncgen_hooks', 'set_coroutine_origin_tracking_depth', 'setcheckinterval', 'setdlopenflags', 'setprofile', 'setrecursionlimit', 'setswitchinterval', 'settrace', 'stderr', 'stdin', 'stdout', 'thread_info', 'unraisablehook', 'version', 'version_info', 'warnoptions']
```
la funzione dir() usata senza argomenti elenca i nomi attualmente definiti
```python
import fibo
>>> vocali = ('a', 'e', 'i', 'o', 'u')
>>> dir()
['__annotations__', '__builtins__', '__doc__', '__loader__', '__name__', '__package__', '__spec__', 'fibo', 'vocali']
```

#### Elenco built-in
dir() non elenca i nomi delle funzioni e delle varibili `built-in`. All'uopo si importi
il modulo builtins.

```python
import builtins       # in python 2.8 import __builtin__

>>> dir(builtins)
['ArithmeticError', 'AssertionError', 'AttributeError', 'BaseException', 'BlockingIOError', 'BrokenPipeError', 'BufferError', 'BytesWarning', 'ChildProcessError', 'ConnectionAbortedError', 'ConnectionError', 'ConnectionRefusedError', 'ConnectionResetError', 'DeprecationWarning', 'EOFError', 'Ellipsis', 'EnvironmentError', 'Exception', 'False', 'FileExistsError', 'FileNotFoundError', 'FloatingPointError', 'FutureWarning', 'GeneratorExit', 'IOError', 'ImportError', 'ImportWarning', 'IndentationError', 'IndexError', 'InterruptedError', 'IsADirectoryError', 'KeyError', 'KeyboardInterrupt', 'LookupError', 'MemoryError', 'ModuleNotFoundError', 'NameError', 'None', 'NotADirectoryError', 'NotImplemented', 'NotImplementedError', 'OSError', 'OverflowError', 'PendingDeprecationWarning', 'PermissionError', 'ProcessLookupError', 'RecursionError', 'ReferenceError', 'ResourceWarning', 'RuntimeError', 'RuntimeWarning', 'StopAsyncIteration', 'StopIteration', 'SyntaxError', 'SyntaxWarning', 'SystemError', 'SystemExit', 'TabError', 'TimeoutError', 'True', 'TypeError', 'UnboundLocalError', 'UnicodeDecodeError', 'UnicodeEncodeError', 'UnicodeError', 'UnicodeTranslateError', 'UnicodeWarning', 'UserWarning', 'ValueError', 'Warning', 'ZeroDivisionError', '_', '__build_class__', '__debug__', '__doc__', '__import__', '__loader__', '__name__', '__package__', '__spec__', 'abs', 'all', 'any', 'ascii', 'bin', 'bool', 'breakpoint', 'bytearray', 'bytes', 'callable', 'chr', 'classmethod', 'compile', 'complex', 'copyright', 'credits', 'delattr', 'dict', 'dir', 'divmod', 'enumerate', 'eval', 'exec', 'exit', 'filter', 'float', 'format', 'frozenset', 'getattr', 'globals', 'hasattr', 'hash', 'help', 'hex', 'id', 'input', 'int', 'isinstance', 'issubclass', 'iter', 'len', 'license', 'list', 'locals', 'map', 'max', 'memoryview', 'min', 'next', 'object', 'oct', 'open', 'ord', 'pow', 'print', 'property', 'quit', 'range', 'repr', 'reversed', 'round', 'set', 'setattr', 'slice', 'sorted', 'staticmethod', 'str', 'sum', 'super', 'tuple', 'type', 'vars', 'zip']
```

## I package

I package sono un modo di strutturare lo spazio dei nomi dei moduli. L'accesso ai 
moduli avvine con la notazione puntata.

Si supponga di voler progettare una collezione di moduli che tratti file e dati audio.
Ci sono molti formati audio: .wav, .aiff, .au.
#### Una possibile struttura del package
Uso di uno schema gerarchico

```
Sound/                            # package principale
      __initi__.py                # iniziliazza il package
      Formats/                    # sotto package
                __init__.py       # inizializza il sotto packege
                wavread.py
                wavwrite.py
                aiffread.py
                aiffwrite.py
                auread.py
                auwrite.py
                ...
      Effect/                     # sotto package effetti sonori
                __init__.py
                echo.py
                surround.py
                reverse.py
      Filters/
                __init__.py
                equalizer.py
                karaoke.py
                ...
```
Quando viene importato il package sound, python cerca in sys.path i package 
contenuti nelle singole directory. 
I file `__init__.py` sono necessati per informare python che si tratta di contenitori
di package. per evitare che nomi comuni come `string` o `type` nascondano moduli validi.
`__init__.py` può essere vuoto, contenere codice di inizializzaione e contribuire alla formazione
della varibile `__all__`

#### Importare moduli o singoli moduli
Una modalità utilizzando tutto il nome a notazione puntata
```python
import Sound.Effects.echo
Sound.Effects.echo.echofilter(input, output, delay=0.7, atten=4)
```
Un'altra modalità senza utilizzo del prefisso
```python
from Sound.Effects import echo
echo.echofilter(input, output, delay=0.7, atten=4) # è disponibile senza prefisso
```
terza modalità: importo la sola funzione
```python
from Sound.Effects.echo import echofilter
echofilter(input, output, delay=0.7, atten=4) # è disponibile direttamente
```
#### Importare con * da un package
Quel che succede con `from Sound.Effects import *` dipende da tanti
fattori, non ultimo il sistema operativo usato. In Windows esempio i nomi dei file
non sono case-sensitive. Spetta all'autore del package mantenere un indice esplicito.
Esempio gli autori non vogliono fare importare tutte le funzioni o le varibili e utilizzando il file `__init.py__` per esplicitarlo con la varibile `__all__`

```python
__all__ = ["echo", "surround", "reverse"]
```
Con la clausola ` * ` con questa definizione di `__all__` sono importate solo le tre funzioni 
























