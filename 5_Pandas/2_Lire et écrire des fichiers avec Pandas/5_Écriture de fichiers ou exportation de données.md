# Écriture de fichiers ou exportation de données

Lorsque vos analyses sont terminées, il est possible que vous souhaitiez exporter votre dataframe de résultats afin de le stocker dans un fichier CSV, TXT ou encore XLSX. Les méthodes à utiliser se ressemblent beaucoup.

Pour exporter un dataframe dans un fichier CSV, la syntaxe est la suivante :

```python
mon_dataframe.to_csv("mes_resultats.csv") 
```

Ici, on utilise la méthode ```to_csv()``` sur l’objet mon_dataframe qui est notre dataframe de résultat, et on l’écrit dans le fichier ```mes_resultats.csv```.

Diverses options existent pour cette méthode, dont les principales sont les suivantes :

- ```sep``` : si on veut spécifier le séparateur ; par défaut, ce sera la virgule, étant donné qu’on utilise la méthode ```to_csv()```.
```python
mon_dataframe.to_csv("mes_resultats.csv", sep=",") 
```

- ```columns``` : une liste avec les colonnes qu’on souhaite écrire dans le fichier, si on ne les veut pas toutes.

Syntaxe:
```python
mon_dataframe.to_csv("mes_resultats.csv", columns=["ma_colonne1", "ma_colonne3"]) 
```

- ```header``` : si on souhaite écrire l’en-tête du dataframe dans le fichier ; par défaut, ce sera le cas.

- ```Index``` : par défaut, cette option est à ```True``` (vrai), ce qui spécifie à Pandas d’écrire les labels de lignes (les index de lignes) dans le fichier. À ```False```, il ne le fait pas.

Pour écrire le dataframe dans un fichier au format TXT, on pourra là aussi utiliser la méthode ```to_csv()```, mais en précisant le séparateur comme étant la tabulation.

Syntaxe:
```python
mon_dataframe.to_csv("mes_resultats.txt", sep="\t") 
```

Enfin, pour écrire votre dataframe dans un fichier Excel, la syntaxe est la suivante :

```python
mon_dataframe.to_excel("mes_resultats.xlsx") 
```

On peut utiliser l’option ```sheet_name``` pour définir le nom de la feuille qui contiendra le dataframe.

Syntaxe:
```python
mon_dataframe.to_excel("mes_resultats.xlsx",  
sheet_name="mes_resultats")
```

Les autres options de la méthode ```to_excel()``` sont assez similaires à celles de la méthode ```to_csv()```.

