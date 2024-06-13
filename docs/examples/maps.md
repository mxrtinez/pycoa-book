# Maps

Like the Cartesian graphs above, maps are interactive.

```
pycoa.map(where=[‘Metropolitan France’],which=‘tot_dchosp’)
```

This query generates an interactive map showing the total number of hospital deaths in mainland France. The display allows the data to be viewed dynamically, providing a clear and detailed overview of the impact of COVID-19 across the different regions.

```
pycoa.map(where=‘Île-de-France’,which=‘tot_vacc_complet’)
```

This query generates an interactive map showing the total number of complete vaccinations in mainland France. The display allows the data to be viewed dynamically, providing a clear and detailed overview of the impact of COVID-19 across the Île-de-France region.
Maplabel

Data can be added directly to the maps for display using the maplabel option.

- `maplabel` :
    - `'text'` displays data in text format on the map
    - `'spark'` displays a sparkline image (temporal evolution)

```
pycoa.map(where=‘Bretagne’, maplabel =‘text’)
```
