# <center>**Use of geoprocessing to highlight the improvement of air quality in relation to confinement due to covid-19**</center>

----------

This project was developed for the Geospatial Programming class of Spring 2020, an international collaboration between two universities, [EPF](https://www.epf.fr/) of France and [RUDN](http://www.rudn.ru) of Russia.

We are Nicolas and Alex, two engineering students at the EPF and we made this program under the supervision of [Naci Dilekli](https://github.com/ndilekli/).

Our project is used to highlight the improvement of air quality in relation to confinement due to covid-19 in Paris region. More precisely, it can be used to compare NO2 levels in Paris between two dates. It is also able to determine the number of people whose decrease of pollution is above certain value entered by the user.

The user can choose the date he or she wants, between 2017 and 2020, and to determine the threshold of decrease of pollution.

To run the code the module arcpy must be installed. Therefore, ArcGIS should probably be installed on your computer. Furthermore, you shall run Jupyter notebook from ArcGIS directory to access arcpy.

First, the user is asked to enter the root of the folder where the databases is located and where new files will be created. The folder must be organised like that:

![Image](https://github.com/AlexEPF/EPF-RUDN-pollution_covid/blob/master/dossier.jpg)

With the root: `“C:/Documents/ArcGIS/Airparif/”` (do not forget “`/`” at the end).

In the Jupyter notebook, there are three main functions using other subfunctions:

 1. `varDelta` function returns the graph of the number of inhabitants as a function of the pollution reduction threshold for 2 user-defined dates
 2. `varDateMonth` function returns the graph of the number of inhabitants whose pollution has decreased by more than a certain level each month between two user-defined dates
 3. `varDateDay` function returns the graph of the number of inhabitants whose pollution has decreased by more than a certain level each day between two user-defined dates

The user must run all cells until varDateDay function.
The next cell allows to run a user interface (orange underlined title for a better identification) where the user enters the graph he or she wants to see, the two dates and the threshold.

For varDelta, the threshold asked is the maximum threshold until which the user wants to plot the graph (maximum of the abscissa axis). What is at stake with the varDelta function is to plot a graph showing the number of people as a function of the variation of pollution they have seen between two dates. It can be useful to plot two graphs with the same maximum threshold and the same first date but with different second dates. For example, one analysis with the second date before the confinement and another one with the second date during the confinement. This way, it is possible to get a result such as the following one showing an increase in the number of inhabitants living in an area where air quality has improved since the beginning of the confinement:

![Image](https://github.com/AlexEPF/EPF-RUDN-pollution_covid/blob/master/graph1.jpg)
![Image](https://github.com/AlexEPF/EPF-RUDN-pollution_covid/blob/master/graph2.jpg)

At the end of the code, there is an extra function, `Pop_pollu` function, which returns only the number of inhabitants whom pollution has fallen by a certain threshold between two user-defined dates. As it creates corresponding files in the folder, this function is mostly useful to see the results, layers, rasters... in ArcGIS. This last function has its own user interface (title in orange) contained in the last cell of the notebook.


The database containing the pollution record at different measuring stations in Paris region is provided by the organisation [Airparif](http://www.airparif.asso.fr/).

The updated database of Airparif can be downloaded here as a shapefile [here](https://data-airparif-asso.opendata.arcgis.com/datasets/mes-idf-horaire-no2/data?geometry=1.464,48.491,3.304,49.124).

 ![Image](https://github.com/AlexEPF/EPF-RUDN-pollution_covid/blob/master/database.jpg)

The downloaded folder should contain 6 files:

![Image](https://github.com/AlexEPF/EPF-RUDN-pollution_covid/blob/master/fichiers.png)
 

Feel free to contact us if you have any issue:

alex.paysant-tholi@epfedu.fr

nicolas.beraud@epfedu.fr
