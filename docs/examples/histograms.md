# Histograms

## 1. Bycountry

```
pycoa.hist(where=‘Normandie’, which=‘tot_vacc_complet’)
```

Histogram showing the distribution of the total number of people fully vaccinated in the Normandy region, comparing the different departments.

## 2. Byvalue

```
pycoa.hist(where=‘Bretagne’, which=‘tot_vacc_complet’, typeofhist=‘byvalue’, bins=4)
```

Histogram representing the distribution of the total number of fully vaccinated people in the Brittany region, comparing the different departments but with vertical bars. The bins attribute allows you to choose the number of bars you want to display.

## 3. Magpie

```
pycoa.hist(where=[‘Bretagne’, ‘Île-de-France’] ,which=‘tot_vacc_complet’, typeofhist=‘pie’)
```

Pie chart showing the distribution of the total number of fully vaccinated people in the Brittany region

## dateslider

In order to study the temporal evolution of the histo and map functions, the dateslider=True (default False) argument can be invoked. Once invoked, a cursor will appear at the top of the graphs, allowing you to choose a date prior to the date of the graph.

```
pycoa.hist(which=‘tot_vacc_complet’,where=‘Île-de-France’,dateslider=True)
```
