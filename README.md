# Binning_Random_Values
This Python script generates random values and bins them into user-defined categories. The script demonstrates how to use Pandas' cut function to divide continuous numerical data into discrete intervals and label them accordingly.

## Sample Code

```python
import numpy as np
import pandas as pd

# Generate random data
df = pd.DataFrame(np.random.random(100)*100, columns=['value'])

# Read the number of categories from user input
n = int(input("Enter the number of categories"))

# Bin the data into n categories, starting from index 1
df['category']= pd.cut(df['value'], bins = n, labels=[f"category{i+1} for i in range(n)"])
print(df)
