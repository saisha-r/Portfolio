# Converting Files into a Single DataFrame

From a folder of data files from a flanker experiment, the following code:

1) Imports the glob module in order to use the glob function to match file patterns

2) Prints and selects all the files that start with "s" followed by any two characters and then ".txt"

3) Converts these files into a list of pandas DataFrames using list comprehension

4) Merges the data into a single DataFrame called df

5) Displays the 8 (random) rows in the DataFrame

*Input*
```python
import glob
print('All the files that start with s:', glob.glob('s??/s??.txt'))
df_list = [pd.read_csv(f, sep='\t') for f in glob.glob('s??/s??.txt')]
df = pd.concat(df_list)
df.sample(8)
```
*Output*
```python
    All the files that start with s: ['s03/s03.txt', 's02/s02.txt', 's01/s01.txt']
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>hour</th>
      <th>minute</th>
      <th>gender</th>
      <th>age</th>
      <th>handedness</th>
      <th>wait</th>
      <th>...</th>
      <th>trial</th>
      <th>target_location</th>
      <th>target</th>
      <th>flankers</th>
      <th>rt</th>
      <th>response</th>
      <th>error</th>
      <th>pre_target_response</th>
      <th>ITI_response</th>
      <th>target_on_error</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>66</th>
      <td>2</td>
      <td>2015</td>
      <td>5</td>
      <td>25</td>
      <td>14</td>
      <td>36</td>
      <td>f</td>
      <td>21</td>
      <td>r</td>
      <td>17.924</td>
      <td>...</td>
      <td>3</td>
      <td>down</td>
      <td>white</td>
      <td>neutral</td>
      <td>0.436</td>
      <td>white</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.024</td>
    </tr>
    <tr>
      <th>146</th>
      <td>1</td>
      <td>2015</td>
      <td>5</td>
      <td>22</td>
      <td>11</td>
      <td>30</td>
      <td>m</td>
      <td>25</td>
      <td>r</td>
      <td>1.599</td>
      <td>...</td>
      <td>19</td>
      <td>right</td>
      <td>white</td>
      <td>congruent</td>
      <td>0.501</td>
      <td>white</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.023</td>
    </tr>
    <tr>
      <th>94</th>
      <td>1</td>
      <td>2015</td>
      <td>5</td>
      <td>22</td>
      <td>11</td>
      <td>30</td>
      <td>m</td>
      <td>25</td>
      <td>r</td>
      <td>2.532</td>
      <td>...</td>
      <td>31</td>
      <td>up</td>
      <td>black</td>
      <td>neutral</td>
      <td>0.429</td>
      <td>black</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.023</td>
    </tr>
    <tr>
      <th>115</th>
      <td>2</td>
      <td>2015</td>
      <td>5</td>
      <td>25</td>
      <td>14</td>
      <td>36</td>
      <td>f</td>
      <td>21</td>
      <td>r</td>
      <td>12.508</td>
      <td>...</td>
      <td>20</td>
      <td>left</td>
      <td>white</td>
      <td>congruent</td>
      <td>0.584</td>
      <td>white</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.024</td>
    </tr>
    <tr>
      <th>97</th>
      <td>2</td>
      <td>2015</td>
      <td>5</td>
      <td>25</td>
      <td>14</td>
      <td>36</td>
      <td>f</td>
      <td>21</td>
      <td>r</td>
      <td>12.508</td>
      <td>...</td>
      <td>2</td>
      <td>right</td>
      <td>black</td>
      <td>congruent</td>
      <td>0.384</td>
      <td>black</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.024</td>
    </tr>
    <tr>
      <th>189</th>
      <td>2</td>
      <td>2015</td>
      <td>5</td>
      <td>25</td>
      <td>14</td>
      <td>36</td>
      <td>f</td>
      <td>21</td>
      <td>r</td>
      <td>3.096</td>
      <td>...</td>
      <td>30</td>
      <td>up</td>
      <td>black</td>
      <td>incongruent</td>
      <td>0.644</td>
      <td>black</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.024</td>
    </tr>
    <tr>
      <th>155</th>
      <td>2</td>
      <td>2015</td>
      <td>5</td>
      <td>25</td>
      <td>14</td>
      <td>36</td>
      <td>f</td>
      <td>21</td>
      <td>r</td>
      <td>2.156</td>
      <td>...</td>
      <td>28</td>
      <td>left</td>
      <td>black</td>
      <td>neutral</td>
      <td>0.436</td>
      <td>black</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.024</td>
    </tr>
    <tr>
      <th>27</th>
      <td>1</td>
      <td>2015</td>
      <td>5</td>
      <td>22</td>
      <td>11</td>
      <td>30</td>
      <td>m</td>
      <td>25</td>
      <td>r</td>
      <td>3.240</td>
      <td>...</td>
      <td>28</td>
      <td>right</td>
      <td>white</td>
      <td>neutral</td>
      <td>0.670</td>
      <td>white</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.022</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 21 columns</p>
</div>


