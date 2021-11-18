# Converting Files into a Single Dataframe

In a folder of data files from a Flanker experiment, the following codes:

1) Imports the glob module in order to match file patterns
2) Selects all the files that start with "s" followed by any two characters and then ".txt"
3) Converts these files into a list of pandas Dataframes using list comprehension
4) Merges the data into a single DataFrame called df

```python
import glob
print('All the files that start with s:', glob.glob('s??/s??.txt'))
df_list = [pd.read_csv(f, sep='\t') for f in glob.glob('s*/s*.txt')]
df = pd.concat(df_list)



```

```
