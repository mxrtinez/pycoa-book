#  Pycoa instructions

Pycoa allows you to import data from a public database, plot it and retrieve it for export The following instructions.

## `pycoa.plot`: 

Plot the selected data as a function of time (time series):

    - `typeofplot=‘date’` (default). The plot is a time series of the epidemiological variable studied.
    - `typeofplot=‘menulocation’`, if you only want to compare 2 time variations from the where list. A double drop-down menu appears, allowing you to choose the 2 curves to be compared.
    - `typeofplot=‘yearly’`, representation of months only for the different years in question, important for seeing seasonal effects. Used to compare different years.
    - `typeofplot=‘spiral’`, spiral representation, complementary to the previous one.

## `pycoa.map`: 

Map representations:

    You can change the textures on the maps. Here is the list of available textures (tiles):
    - `tile=‘openstreet’`: Uses OpenStreetMap map data, which is collected by a global community of contributors and updated in real time. This texture provides a detailed base map covering the whole world.
    - `tile=‘esri’`: Uses Esri mapping services, which provide rich, detailed map data. This texture is ideal for applications requiring precise, professional maps.
    - `tile=‘stamen’`: Uses tiles from Stamen Design, a company specialising in the creation of elegant and artistic maps. Stamen tiles offer a unique aesthetic with different options, such as a black and white map (toner), a coloured map (terrain) or a watercolour map.
    - `tile =‘positron’`: Provides modern, elegant maps created by Carto, with a minimalist aesthetic and bright colours. Positron maps are ideal for contemporary visualisations and design-led applications.

##  `pycoa.hist` : 

Histograms, with the option :

    - `typeofhist=‘bycountry’` (default), for a histogram with horizontal bars, location by location
    - `typeofhist=‘byvalue’`, for a histogram with vertical bars, by value
    - `typeofhist=‘pie’`, for a pie chart

## `pycoa.get`: 

Retrieve data for further processing:

You can also use the following instructions:

- `pycoa.listplot()` : Lists the available chart types.
- `pycoa.listhist()` : Lists the types of histograms available.
- `pycoa.listtile()` : Lists the textures available for maps.