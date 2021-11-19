# Creating a Table and Point Plot
The following codes work with behavioural data from a "flanker-Simon" experiment. First I generate a table of descriptive statistics for reaction time (RT), grouped by flanker and Simon conditions. Then I create a point plot with only the congruent and incongruent conditions (which required me to remove the neurtral conditions from both the flankers and Simon data).

```python
#Table of descriptive statistics
df_agg.groupby(['flankers', 'simon']).describe()

#Point plot with only the congruent and incongruent conditions
df_agg = df_agg[(df_agg.flankers != 'neutral') & (df_agg.simon != 'neutral')]

sns.catplot(kind='point', join=False,
           data=df_agg,
           x='flankers', y='clean_rt', hue='simon',
           order=['congruent', 'incongruent'])

plt.show()
```
