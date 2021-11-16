import pandas as pd
crimes = pd.read_csv("crime.csv")

crimes.head()
![image](https://user-images.githubusercontent.com/52316463/141693934-05739de7-dff2-4994-848c-836e806a77f3.png)


crimes['NEIGHBOURHOOD'].unique()
![image](https://user-images.githubusercontent.com/52316463/141693921-53e2ffd2-47ea-42ad-a956-1373e10f10e5.png)


coords = crimes.query('NEIGHBOURHOOD == "Shaughnessy"')[['Latitude', 'Longitude']].values

pd.DataFrame(coords).dropna().plot.scatter(x=0, y=1)
import matplotlib.pyplot as plt
plt.gca().set_aspect('equal')

from shapely.geometry import Polygon

Polygon(
    list(
        pd.DataFrame(coords).apply(lambda srs: (srs[0], srs[1]), axis='columns').values
    )
).convex_hull

# Kerrisdale
![image](https://user-images.githubusercontent.com/52316463/142045067-282cf188-3bb0-488e-8168-15bc817c48fb.png)
![image](https://user-images.githubusercontent.com/52316463/142045105-6d31f546-bb94-4f07-a26c-d8f081fb9409.png)



# Strachocona:

![image](https://user-images.githubusercontent.com/52316463/141694026-12c4897b-5445-4378-aba5-73df1bcd9522.png)
![image](https://user-images.githubusercontent.com/52316463/142045174-969edd4d-40c4-48d8-9a63-f0cdb5531955.png)



