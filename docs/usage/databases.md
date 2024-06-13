# Database selection

Several databases linked to Covid-19 can be used.

The first of the following instructions lists the available databases, with their name, the country code in [ISO 3166-1 alpha 3](https://fr.wikipedia.org/wiki/ISO_3166-1#Table_de_codage) format (or ww for world), the level of geographical detail (granularity) and the associated country or regions.

```
pycoa.listwhom(True)
```

For the example, the second instruction is used to select the main French database, produced by Santé Publique France (the database is therefore called `spf`). This may take a few moments.

```
pycoa.setwhom(‘spf’, reload=False)
```

Santé Publique France publishes data relating to the Covid-19 epidemic in France. Unfortunately, unlike other databases, the data format varies frequently and without warning. As a result, some commands unfortunately fail while *Pycoa* is updated to reflect the latest changes.

**To find out which database is currently in use, you can use:**

```
pycoa.getwhom()
```

Once the database has been loaded, we are given a list of information:

- The list of epidemiological data (which): *[‘cur_hosp’, ‘cur_idx_R’, ‘cur_idx_tx_incid’, ‘cur_idx_tx_occupation_sae’, ‘cur_nb_A0’, ‘cur_nb_A1’, ‘cur_nb_C0’, ‘cur_nb_C1’, ‘cur_nbre_pass_corona’, ‘cur_rea’, ‘cur_tx_A1’, ‘cur_tx_C1’, cur_tx_pos', “incid_dchosp”, “incid_hosp”, “incid_rad”, “incid_rea”, “tot_P”, “tot_T”, “tot_dchosp”, “tot_rad”, “tot_vacc1”, “tot_vacc2_rappel”, “tot_vacc_complet”, “tot_vacc_rappel”]*
- An example of a `where` list: **Côtes-d'Armor, Eure, Orne, Pyrénées-Atlantiques, Ain...**
- Last update: 2024-05-14

## Database contents

The list of epidemiological variables available for the selected database is given by the following instruction:

```
pycoa.listwhich()
```

The list of geographical areas accessible in the selected database is given by the following instruction:

```
pycoa.listwhere()
```

Various keywords can be used to retrieve specific information from the database:

- `which`: epidemiological variables of interest (selected data)

- `where`: selection of geographical area(s) :
    - country, `list` of countries, region, continent...
    - department, `list` of departments, regions...

- `what`: in the case of a time series :
    - `cumul` if you want to see the sum of everything that has happened
    - `daily` for daily values
    - `weekly` for weekly values
    - `standart` (default here)

- `when`: date window for the data selected
    - `vide`': default format
    - `dd/mm/yyyy:dd/mm/yyyy'`: the start and end of the time window are specified
    - `dd/mm/yyyy::` only the start is specified, the end date is set by the last value in the database
    - `:dd/mm/yyyy`’: only the end date is specified, the start is set by the first value in the database

- option:
    - `nonneg`: smoothes the data to avoid negative values (post-corrections)
    - `nofillnan‘`: by default, accumulated data that has no value (’Not a Number' or Nan) is replaced by the previous day's values, “nofillnan” removes this padding
    - `smooth7`': smooth data over 7 days to eliminate fluctuations linked to weekends, for example
    - `sumall`': sums all the values present
    
- `bypop`: Used to normalise curves by the number of inhabitants. To do this, use bypop. This variable can be expressed as a power of 10: ‘no’, ‘100’, ‘1k’, ‘100’, ‘1M’ or ‘pop’ .

You can also use the following instructions:

- `pycoa.listwhat()` : Lists the various possible options for the what attribute.
- `pycoa.listwhere(True)` : Lists the regions.
- `pycoa.listoption()`: Lists the available options.
- `pycoa.listoutput()`: List available output formats: pandas, geopandas, list, dict, array.
- `pycoa.listbypop()` : Lists the options for normalising curves by the number of inhabitants.

