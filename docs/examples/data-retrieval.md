# Data retrieval

It is possible to retrieve data in a Pandas DataFrame, a data structure similar to an Excel spreadsheet, managed by the Pandas library.

```
mydf= pycoa.get(where=‘France’, which=‘tot_vacc_complet’)
display(mydf)
```

This request uses the pycoa.get function to retrieve the complete vaccination data for France and store it in a data structure called DataFrame, managed by the pandas library. The DataFrame is similar to an Excel spreadsheet and can be easily manipulated and analysed to extract useful information. Next, using display(mydf), we display the DataFrame to view the retrieved data in an organised and readable way. Here we can see a preview of the first and last rows.