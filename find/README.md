```Bash
#!/bin/bash
```

#Find

## 
```Bash
find . -name "*.txt"
```

```Bash
find . -type f
```



## Eseguire comandi

```Bash
find . -name 'A*' | while read -r line; do newName=$(echo $line | sed 's/A/_x/'); mv ./$line ./$newName; done
```

```BASH
find . -type d -exec chmod 750 {} \;
```

