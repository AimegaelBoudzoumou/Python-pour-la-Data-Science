# Introduction

On peut décrire les séries de Pandas comme étant une colonne d’un dataframe, un tableau à une dimension (vecteur) ou encore une suite de valeurs, numériques ou non. 

On peut aussi décrire une série comme un ensemble de valeurs représentant une variable pour un ensemble d’observations ou d’individus. 

Une série a un nom : par exemple dans l’image ci-dessous, le nom de la série est "Variable". 

Tout comme les autres structures Python que nous avons déjà vues, une série possède aussi des index.

![image](https://github.com/user-attachments/assets/65e67f9f-ee4f-4575-8fee-67bd57a59d1c)

Une série peut être créée à partir d’une liste, d’un tableau NumPy, ou encore d’un dictionnaire, grâce à la méthode ```Series()```. 

Elle peut aussi être créée à partir d’un fichier grâce aux fonctions de lecture de fichiers que nous avons vues précédemment, telles que ```read_table()``` ou ```read_csv()```.

La structure de données ```Series``` possède deux composants principaux :

- les valeurs, auxquelles on peut accéder avec la méthode ```values()```,

- les étiquettes, plus couramment appelées les index, auxquelles on peut accéder avec la méthode ```index()```.

La série possède un seul axe, il s’agit de l’axe des index, contrairement au dataframe, que nous verrons plus tard, qui contient deux axes : les lignes et les colonnes.

Il faut savoir que pour les séries, par défaut, les index sont des nombres entiers : ils commencent à 0 et s’incrémentent, comme les ```ndarrays``` de NumPy. Mais il est aussi possible de remplacer ces index entiers par des étiquettes du type que l’on souhaite (nombres, caractères). Par exemple, si on préfère mettre des lettres comme index plutôt que des nombres, Pandas nous autorise à le faire. Ainsi, on pourra accéder aux valeurs de la série soit en donnant la position de la valeur entre crochets, soit en donnant l’étiquette correspondant à cette valeur, toujours entre crochets.

Enfin, au sein d’une série, il est fortement conseillé d’utiliser des données qui sont homogènes, de même type (uniquement des valeurs numériques, uniquement des valeurs de type caractères, etc.), même si le stockage de valeurs de types hétérogènes est permis.

