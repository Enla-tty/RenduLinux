```sh 
mkdir commands && cd commands
```

```sh 
touch too_long

max=100
for (( i=1; i <= $max; ++i ))
do
    echo "Ligne $i" >> too_long
done
``` 

```sh 
head -n 5 too_long
tail -n 7 too_long
cat too_long | grep -o '[0-9]\+' | sort -n -r | head -n 3
```

```sh 
cat too_long | grep "42"
``` 

```sh 
sed -i -e 's/Ligne 42/the ultimate question of life, the universe and everything/g' too_long
```

```sh 
touch script
```
Contenu du script: 
```sh 
#!/bin/bash

function check_argv()
{
  if [[ $1 = NULL ]]; then
    echo "0";
    exit 0;
  else
    echo "1"
    exit 1;  
  fi
}

case $2 in
 hello) echo "hello"
 ;;
 toto) echo "toto"
 ;;
 *) echo "autre chose"
 ;;
esac

check_argv $1;
```

Un if/else fait tous les tests jusqu'à trouver un résultat correct ou arriver à la fin des tests, alors que le case ne fait que le test nécessaire.

