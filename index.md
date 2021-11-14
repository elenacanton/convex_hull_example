import pandas as pd
crimes = pd.read_csv("crime.csv")

crimes.head()

crimes['NEIGHBOURHOOD'].unique()

coords = crimes.query('NEIGHBOURHOOD == "Shaughnessy"')[['Latitude', 'Longitude']].values

pd.DataFrame(coords).dropna().plot.scatter(x=0, y=1)
import matplotlib.pyplot as plt
plt.gca().set_aspect('equal')
