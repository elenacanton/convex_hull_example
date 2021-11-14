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

# Shaughnessy

![image](https://user-images.githubusercontent.com/52316463/141693960-7394ed0d-73fb-41bb-a51b-288570662f6d.png)

# Strachocona:

![image](https://user-images.githubusercontent.com/52316463/141694026-12c4897b-5445-4378-aba5-73df1bcd9522.png)

