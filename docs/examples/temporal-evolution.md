# Time trend (plot)

## 1. Date

```
pycoa.plot(which=‘tot_vacc_complet’, where=‘Bretagne’, typeofplot=‘date’)
```

This query will plot the change in the total number of people fully vaccinated in the Brittany region. The data is separated by department. Try it with or without typeofplot=‘date’, and you'll see that you get the same graph.

```
pycoa.plot(which=‘tot_vacc_complet’, where=‘Paris’, what=‘daily’, option=‘smooth7’)
```

This plot shows the daily change in the total number of fully vaccinated people in Paris. Using the ‘smooth7’ option, the data is smoothed over a 7-day period to smooth out daily variations such as weekends.

```
pycoa.plot(where=‘Île-de-France’, option=‘sumall’, when=‘01/01/2021:01/01/2023’)
```

This plot shows changes in the default epidemiological value (tot_dchosp). Using `sumall` allows us to group together all the departments in the Paris region. Try it out with and without! Thanks to the when attribute, only data between 01/01/2021 and 01/01/2023 are displayed.

### Partial sums

It is possible to create partial sums of data. For example, to obtain the sum for Brittany, Île-de-France and Hauts-de-Francee, use double brackets as follows

```
pycoa.plot(where=[[‘Bretagne’,‘Île-de-France’,‘Hauts-de-France’]],option=‘sumall’)
```

### Semi-partial sums

It is also possible to create semi-partial sums of data. For example, to obtain sums for Brittany, Île-de-France and Hauts-de-France, we would use double brackets as follows. Pretty much the same as the previous query, but the values are separated by region.

```
pycoa.plot(where=[[‘Bretagne’],[‘Île-de-France’],[‘Hauts-de-France’]],option=‘sumall’)
```

### Bypop

You may want to normalise the curves by the number of inhabitants. To do this we use bypop .

This variable can be expressed as a power of 10: ‘no’, ‘100’, ‘1k’, ‘100’, ‘1M’ or ‘pop’ .

```
pycoa.plot(where=‘France’,bypop=‘100k’)
```

Here a normalisation per 100k inhabitants has been applied. So we have the rate of deaths in hospital per 100k inhabitants by department.

## 2. Menulocation

```
pycoa.plot(which=‘cur_rea’, typeofplot=‘menulocation’)
```

We use `which=‘cur_rea’` to represent the number of patients currently in intensive care. The `typeofplot='menulocation'`option allows us to compare two curves by selecting specific regions or countries from a drop-down menu.

## 3. Yearly

```
pycoa.plot(where=‘Nord’,what=‘daily’,option=[‘nonneg’,‘smooth7’],typeofplot=‘yearly’)
```

This graph shows the daily trend in hospital deaths in the North region. By specifying `what=‘daily’`, we examine daily values, allowing us to see daily fluctuations. In addition, by using `option=[‘nonneg’,‘smooth7’]`, the data is smoothed to avoid negative values and attenuate short-term fluctuations. Finally, by choosing `typeofplot=‘yearly’`, we have a representation of the months for different years, which is essential for detecting seasonal effects and comparing trends from one year to the next.


## 4. Spiral

```
pycoa.plot(where=‘Paris’,what=‘daily’,option=[‘nonneg’,‘smooth7’],typeofplot=‘spiral’, when=‘01/01/2021:01/01/2023’)
```

Same query as above, just change the date. By choosing `typeofplot=‘spiral’`, the data is represented in a spiral, which offers a different and interesting perspective on the temporal evolution of the data.

## 5. Versus

This representation will allow us to compare 2 curves of different epidemiological variables.

```
A = pycoa.get(which=‘cur_rea’, where=‘Paris’)
B = pycoa.get(which=‘tot_vacc_complet’, where=‘Paris’)
A[‘tot_vacc_complet’] = B[‘tot_vacc_complet’]
pycoa.plot(input=A, input_field=[‘cur_rea’, ‘tot_vacc_complet’], title='cur_rea and tot_vacc_complet at 
```