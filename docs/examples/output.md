# Data for further processing

List of available outputs :

```
pycoa.listoutput()
```

Example with pandas :

```
A=pycoa.get(where=[‘Paris’], what=‘daily’, which=‘tot_vacc_complet’,output=‘pandas’)
A.head()
```

## Save data to an external file

To do this, we'll use the saveoutput function. This takes 3 arguments:

- `pandas`: the data to be saved in a Python pandas dataframe format. This variable is required; there is no default value.
- `saveformat`: the format of the file to be saved excel (default) or csv.
- `savename` : name of the file to save, (by default the file is named pycoaout + ‘.xlsx/.csv’.

```
A=pycoa.get(which=‘tot_vacc_complet’,where=‘Bretagne’,output=‘pandas’)
pycoa.saveoutput(pandas=A,savename=‘monfichier’,saveformat=‘csv’)
```

The pandas dataframe A is saved in a csv format file with the name myfile.csv. The file created is located in the current directory.