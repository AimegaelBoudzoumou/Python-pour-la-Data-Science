```python
import pandas as pd

df = pd.read_excel("mes_fichiers/Emtec.xlsx", usecols = 'B,J')
df

df[df["Phase"] == "Suspendu"]

new_line = [8506930, "Suspendu"]

df.loc[len(df)] = new_line

df[df["Phase"] == "Suspendu"]
```
