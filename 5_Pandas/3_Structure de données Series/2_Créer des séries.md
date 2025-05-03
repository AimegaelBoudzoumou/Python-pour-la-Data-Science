# Créer des séries

Pour pouvoir créer sa première série, il faut d’abord importer la librairie Pandas, puis utiliser la fonction ```Series()```.

Voici la syntaxe générale :
```python
import pandas as pd 
serie=pd.Series(donnees)
```

## a. À partir de valeurs aléatoires

Syntaxe:
```pythonù
import numpy as np 
import pandas as pd 
pd.Series(np.random.choice(data, size))
```

__Pratiquons__
```python
import numpy as np 
import pandas as pd 
mes_nombres = pd.Series(np.random.choice(list(range(0,500)),10)) 
print(mes_nombres)
```

## b. À partir d’une liste Python

```python
import pandas as pd 
ma_serie = pd.Series([25,45,62,12,11]) 
print(ma_serie)
```

Rappel : 

Avec Pandas, les différents types sont les suivants :

```object``` = chaines de caractères, texte (```str``` en Python)

```int64/int32``` = valeurs entières numériques (```int``` en Python)

```float64``` = valeurs réelles, à virgules (```float``` en Python)

```bool``` = booléens, valeurs VRAIE ou FAUX (```bool``` en Python)

## c. À partir d’un tableau NumPy (ndarray)

Il est aussi possible de créer une série à partir d’un tableau NumPy ```(ndarray)```.

```python
import pandas as pd 
series = pd.Series(numpy_array)
```

## d. À partir d’un fichier texte

Pour rappel, l’option ```squeeze``` permet de dire à Pandas que l’on souhaite créer un objet de classe ```Series```, lors de la lecture du fichier, et non pas un dataframe.

Nous allons sélectionner la colonne ```Weight``` de notre tableau, qui correspond au poids des athlètes.

```python

```
