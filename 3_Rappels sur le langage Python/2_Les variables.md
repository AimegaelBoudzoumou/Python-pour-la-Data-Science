# Les variables
Une variable consiste à attribuer un nom à une information. On range cette information dans une variable que l’on nomme, ce qui permet ensuite d’accéder à cette information en appelant simplement la variable.

syntaxe : 
```python
a=11
```

Le nom d’une variable peut contenir des lettres, des chiffres ou encore des underscores _, mais il ne peut pas commencer par un chiffre. 

```python
1a=11 # SyntaxError: invalid decimal literal

a1=11 # fonctionne correctement
```

Attention, Python est sensible à la casse, c’est-à-dire qu’il fait une différence entre minuscules et majuscules.
```python
m=3
M=4

print(m) # 3
print(M) # 4
```

Il est possible d'affecter une nouvelle valeur à une variable déjà existante
```python
m=5
print(m)
m=2
print(m)
```

Note :

La fonction print() de Python permet d’afficher quelque chose comme par exemple du texte : print("Hello"), ou encore le contenu d’une variable : print(ma_variable).

