#  Using databases

For this example, we are using data from OWID, certainly the most complete database on Covid-19. A priori, the data concerning the number of cases and deaths are identical to those displayed by Johns Hopkins University, one of the first institutions to monitor the JHU epidemic.

## Changes to the database

```
pycoa.setwhom(‘owid’)
```

## Geographical representation of the number of deaths due to Covid-19

By default, the epidemiological data loaded is the 1st item in the database, in this case `‘total_deaths’`, i.e. the total number of deaths. `Thepycoa.map` function represents the map of the geographical areas linked to the database, in this case all the countries in the world.

The `visu=‘folium’` option modifies the map marginally.

```
pycoa.map()
pycoa.map(visu=‘folium’)
```

## Histogram of the number of people vaccinated per 100 inhabitants

It is possible to select a subset of the world's countries by specifying the where keyword; in this case, the G20 countries are selected. Other similar options are possible, which can be retrieved as explained above using the `pycoa.listwhere()` function.

```
pycoa.hist(which=‘total_people_vaccinated_per_hundred’, where=‘G20’)
```
