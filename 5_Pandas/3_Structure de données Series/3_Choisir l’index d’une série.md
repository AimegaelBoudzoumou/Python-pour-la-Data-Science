# Choisir l’index d’une série

Syntaxe:
```python
serie = pd.read_csv("mon_fichier.csv", index_col=[colonne1]  
squeeze=True, usecols=[colonne1,colonne2])
```

Nous allons créer une série avec la colonne Weight du fichier des Jeux olympiques comme valeurs et la colonne Name du fichier comme index.

__Attention à l'utilisation de _squeeze___

```python
import pandas as pd
ma_serie_de_poids_index_defaut=pd.read_csv("athlete_events.csv", usecols=["Weight", "Name"], index_col=["Name"])
ma_serie_de_poids_index_defaut.squeeze()
```

ou

```python
import pandas as pd
ma_serie_de_poids_index_defaut=pd.read_csv("athlete_events.csv", usecols=[1,5], index_col=[1])
ma_serie_de_poids_index_defaut.squeeze()
```

![image](https://github.com/user-attachments/assets/6dd9474f-ac54-4479-9e70-3665657175af)
