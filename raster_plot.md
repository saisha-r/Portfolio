# Raster Plot
The following code creates a raster plot to show the spike times in a mouse neuron during sine wave grating. These data were provided by Dr. Nathan Crowder, Department of Psychology & Neuroscience, Dalhousie University.


```python
# Import necessary packages
import pandas as pd
import matplotlib.pyplot as plt
```


```python
# Read in data
df = pd.read_csv('crowder_data_all.csv')
```


```python
# Set variables

# Names of all neurons
neurons = df['neuron'].unique()

# All condition labels
conditions = df['condition'].unique()

# Labels for the levels of stimulus contrast
contr_levels = df['contrast'].unique()

# Labels for different trial ID numbers
trials = sorted(df['repetition'].unique())

# Length of each trial
trial_length = 4000

# Stimulus timing
stim_on_time = 2000
stim_off_time = 3000
```


```python
# Subset data to create a new dataframe
# This selects data from neuron labelled m1_6
# In the control condition
# With a contrast level of 48%

dat = df[(df['neuron'] == 'm1_6') & (df['condition'] == 'CTRL') & (df['contrast'] == 48)]
```


```python
# Raster plot
fig, ax = plt.subplots()

plt.axvspan(stim_on_time, stim_off_time, alpha=0.5, color='grey')

for trials in sorted(dat['repetition'].unique()):
    spike_times = dat[dat['repetition'] == trials]['spiketime']
    ax.vlines(spike_times,
              trials + 0.4, trials - 0.4)

ax.set_xlabel('Time (ms)')
ax.set_xlim(0, trial_length)

ax.set_ylabel('Trial Number')
ax.set_title('Neuronal Spike Times')

plt.show()
```




    
![png](raster%20plot_files/raster%20plot_5_0.png)
    


