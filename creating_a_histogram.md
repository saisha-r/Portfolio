# Creating a Histogram
The following code works with reaction time (RT) data in a flanker experiment. There was a skew in the RT data, which posed an issue for running statistics. Therefore, a inverse transformation (i.e., 1/RT) was applied to make the RT data's distribution more statistically normal. Then, a histogram of the inverse-transformed RT data was plotted.

```python
# Inverse-transform the RT data
df.loc[:,'rt_inv'] = 1/df['rt_ms']

# Plotting
df.loc[:,'rt_inv'].plot(kind='hist')

# Adds a solid line at the median and dashed lines at the 25th and 75th percentiles
plt.axvline(df['rt_inv'].describe()['25%'], 0, 1, color='turquoise', linestyle='--')
plt.axvline(df['rt_inv'].median(), 0, 1, color='cyan', linestyle='-')
plt.axvline(df['rt_inv'].describe()['75%'], 0, 1, color='turquoise', linestyle='--')

# Displays the plot
plt.show()
```

<img src="histogram.png" alt="histogram"/>
 <br />. 
