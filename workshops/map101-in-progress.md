# Map Making 101

## Introduction

Welcome to the online tutorial for Map Making 101, the Leventhal Map & Education Center's (LMEC) introductory map making workshop.
This session is offered twice monthly at the Central Branch of the Boston Public Library. Please find upcoming offerings via the [LMEC Events Calendar.](https://www.leventhalmap.org/calendar/ "LMEC Events Calendar")

This tutorial will serve as both a digital companion to the in-person workshop, and a step-by-step tutorial for those unable to attend in person.


**By the end of this tutorial, you will have learned:**
- basics of GIS
- geospatial data formats
- intro to QGIS, a free geospatial software
- how to make a thematic map in QGIS
- how to export and share maps from QGIS



## About LMEC
The Norman B. **Leventhal Map and Education Center (LMEC)** at the Boston Public Library:
- cares for the cartographic collections of the Boston Public Library
- features exhibitions in its map gallery highlighting the collections and fostering spatial thinking and learning
- provides educational programs and learning resources to students of all ages
- creates and shares [free teaching resources](https://collections.leventhalmap.org/educators "Tools for teachers") for spatial thinking and learning in the classroom
- provides study space - free and daily - in its Learning Center
- makes all archival holdings [available for research](https://www.leventhalmap.org/research "Reference")   virtually or in person
- supports geospatial learning by connecting you with data and tools for map making

**Where you can find us:**


We are sandwiched between the historic McKim and modern Johnson buildings that comprise the Central Copley Branch of the Boston Public Library. The easiest way to navigate to our map gallery, is by entering from the Johnson entrance (700 Boylston Street). A few hundred feet from the entrance there is an elevator, or a staircase with eight steps to the upper level of the first floor. Once on this upper level, there is a wheelchair elevator, or six additional steps, to the Map Center's exhibition gallery.

Our **workshops** are hosted **in the BPL technology classroom** located on the Mezzanine floor of the Johnson building at the Central Branch. This is also accessible by elevator.

Our map gallery and learning center hours are listed [here.](https://www.leventhalmap.org/visit "Visit"). For more information, please give us a call at (617) - 859 - 2383.

Please find a map of our location within the Boston Public Library:
![BPL map](/media/img/BPL_map.png)


## Workshop Context

### Introduction to GIS
**What is GIS and what does it do?**

The acronym GIS has been used to refer to a number of terms since geospatial technology has come into existence. You may see it in place of "Geographic Information Science," "Geographic Information Software," or "Geographic Information Systems".

Let's go over some common undertakings geospatial tools and software can help us achieve:


1). **Creating digital maps** from existing data sources.

Geospatial software is capable of importing geospatial data, and displaying it graphically - i.e. a map. We can use the software to edit and manipulate the way the data is displayed, and create digital cartographic materials we can then prepare for print or for digital sharing.


2). **Performing spatial analysis**, which doesn’t necessarily require actually making a map.

Geospatial software can help us carry out techniques for spatial analysis. The goal of these techniques is typically to evaluate existing trends and patterns for any given phenomena, and attempt to predict future occurrences. This is similar to the way traditional statistical methods attempt to use math to make sense of the world - and how graphical computer software for statistics can make the use of these models much easier.

The difference between regular statistical methods and spatial analysis methods is that spatial analysis methods take into account *where* phenomena occur. Measuring the impact of distance or demographic, economic or environmental variables in relation to the phenomena at hand is often crucial for understanding trends and patterns in the data. You can use the mathematical results of your spatial analyses to make a map, or simply to inform your research.


3). **Collect and parse geographic data** from individuals, satellites, sensors and so on

Geospatial software can be used as a data collection tool. Not only can you use it to work with data you have downloaded or acquired elsewhere, you can use it to create data of your own.

4). **Manage the spatial attributes of data**

Geospatial software has a lot of data management functionalities. Just as we compared similarities between geospatial and statistical software, it is also appropriate to think of the data management capabilities of geospatial software as akin to relational database software. Here, we can observe and manage the relationships between many different data tables. We can access and edit tables' attributes (also called "properties", "columns" or "fields"). We can query records, and create subsets of the data based on different filtering parameters, including location. Because the software knows how to interpret the *where* of every record, we are able to manage our data in relation to actual locations.


### Software options


**GIS software packages**

ESRI:
    - ArcMap, ArcGIS Pro, and so on (desktop)
    - The goliath, or “Microsoft Office” of GIS
    - expensive, powerful, sometimes cumbersome

FOSS (Free And Open Source Software) Alternatives:
    - QGIS (excellent free alternative to ESRI desktop software)

Software that doesn’t feel like GIS at all:
    - Google Maps, Apple Maps, Mapbox, Carto, other Web-based mapping tools


### GIS data overview

There are three main types of geospatial data: raster, vector and tabular.

![types of data graphic](/media/img/types_data.png)


**Raster**

When raster data is displayed in geospatial software, it looks like an image. <br>
Here are some examples of common spatial raster data.



 ![example of raster data](/media/img/satellite.png) <br>
 *Example of raster data: satellite and aerial imagery*

![example of raster data](/media/img/map.png) <br>
 *Another example of raster data: scans of historical maps*

 ![third example](/media/img/shaded-relief.png) <br>
 *Third example of raster data: shaded relief made from a digital elevation model*



While this kind of spatial data is displayed graphically in geospatial software to appear like an image, it actually can be conceptualized as a matrix of numbers, where each pixel on the screen is a graphic representation for some numerical value. 

These numerical values can have many different meanings, depending on what type of raster data you are working with. For example, in a digital elevation model, each pixel has a numerical value that indicates the elevation of the area that pixel represents. 

In other cases the pixel values may have less meaningful significance, besides telling the computer how to display them. For example, pixel values in aerial photography or scans of historical maps pertain only to the color properties of the image. 


You may already be familiar with common raster data formats from working with regular old images -- .pngs, .jpgs, and the most high-resolution of these options, .tiff files. You may also run into GeoTIFFs, which are .tiff files that have been assigned spatial properties -- like the example of the historical map aligned over the United States  pictured above. 


**Vector**

Vector data is synonymous with geometry (just like in high school math class). There are three main kinds of vector data: point, line and polygon. An easy way to think about this, is that each geometric "feature," is a proxy for each feature in the real world your data is representing.

For example, you may be working with vector point data where every point represents a business in Boston.

Or, you may be working with line data where each line represents a river in the United States.

Or, you may be working with polygon data -- like we will be doing today -- where every polygon represents the shape of a town in Massachusetts.

These are each examples of vector data.

Typical formats for vector data are shapefiles, geopackages, and geoJSON.

Let's use points as an example to explore vector data more.

Say we have point data for businesses in Boston.

If we were to open up the data in its tabular form inside a geospatial software like QGIS, each record in the table would represent one business in Boston. There would be a field for latitude, and a field for longitude, which the software is able to interpret and display graphically as points on a map. There also could be columns for any other attributes we want to measure.

For example, in the business table, we could have a field for number of employees, owner's name, hours open, year established, and so on. This makes the geospatial software powerful, because it means we can map spatial phenomena in tandem with other aspects of the features we are studying.

Some data comes to us as inherently spatial. For example, the vector polygon zip code data we downloaded from the MassGIS Open Data portal for use in this workshop, is essentially a bunch of shapes representing zip code regions in Massachusetts. When we look at it in its tabular form, each record represents one zip code, and some of the columns present are spatial information for that zipcode polygon, names of the town it falls in, census FIPS code, and so on.

Some data is not inherently spatial, and actions need to be performed by us to get the data into a format where it is compatible with GIS mapping.

**Tabular data**

Sometimes we encounter tabular data (data that is in a table) that has no location information available, but enumerates some kind of occurrence we are interested in depicting on a map.

As long as the data occurrences happened *somewhere* this data can "become spatial".

There are many ways to do this, and if you are looking for help working with any particular dataset, please feel free to reach out to us via our [form.](https://www.leventhalmap.org/research/geospatial-data/ "Geospatial reference form") We are happy to help!

Once common way of taking non-spatial attribute data and turning it spatial is by a process called geocoding.

A **geocoder** is effectively a tool that takes a table with addresses and uses these addresses to estimate latitude and longitude values for each record.

Another common way of turning non-spatial tables into geospatial data, which we will be working through in this very tutorial, is by something called an attribute join.

In an **attribute join**, a statistical table is joined, or as we jokingly refer to it in our workshop, "smooshed" together with a spatial vector file, by using a common field in both tables. The result is vector geospatial data (i.e. data geospatial software can graphically display as a map) that now contains all of the statistical information from the original table we wished to measure.

A common data format for tabular data is .CSV.

"Comma Separated Values (CSV)" means that the table values are separated by commas.

For example, take a look at the .CSV we will be working with in this tutorial, opened in a basic notepad text editor:

![csv](/media/img/csv.png)

This file format is a very simple text format that programs like ArcGIS and QGIS can read easily with no issues. Sometimes you may run into headaches with Excel's default format .xlsx, and we therefore recommend exporting your tabular data as a .CSV before attempting to work with it using geospatial software or tools.

## Make a map
By the end of this tutorial, you will have made this map:
![mass map](/media/img/Mass_map.png)

This map was made by one of the Leventhal Map & Education Center interns in response to a request from a BPL librarian interested in reporting on the number of seniors in Massachusetts who are currently signed up for [BPL ecards.](https://www.bpl.org/ecard/ "BPL eCards") 

This type of map is called a **choropleth map**. A choropleth map is a type of thematic map, or a map that shows a particular theme or subject. A choropleth map uses differences in shading, coloring, other symbology within predefined areas to indicate differences in values of a particular variable in those areas. In this case, our choropleth map takes the variable "number of seniors with active BPL eCards" and represents the quantity of that variable in each zipcode feature as a corresponding shade of red. Zipcodes with larger number of seniors with BPL eCards appear darker, while those with fewer or none appear lighter.

### Data

The librarian already had an excel spreadsheet measuring rates of eCard users. This data was structured into two fields, one column for zip codes, and another containing the number of seniors per zip code who have an active eCard.

Here is an example of what that data looks like in excel:

/////include screenshot/////

Although QGIS can read an excel spreadsheet, it is best to use a file format that is standard rather than one created by and for a proprietary software like excel. In this case, we exported the file as a CSV (comma-separated values) file,a plain-text file that organizes and reads tabular data as a document of values (names, percentages, etc.) separated by commas. This type of file will always be read the same way regardless of the program you may choose to use to edit it.
/////fix this part later/////

Here is an example of what a CSV of that data looks like in a text editor:

![csv](/media/img/csv.png)


In this tutorial, we will take this non-spatial eCard data and join it with a spatial polygon zip code file obtained from MassGIS, in order to make a map of the number of seniors in Massachusetts who have e-cards.

First, we will need to download the data.

Navigate to the following links and select "Download" for each. It's OK to let these files auto-save to your downloads folder, or you can save it anywhere you will be able to easily find it again!

[Massachusetts Zip Codes - geospatial vector polygon data](https://drive.google.com/open?id=1LBvYo4aj0mlp7_hjD5qiZj6DUJ0T9GUK "MA Zipcodes")

[Senior e-card .csv table](https://drive.google.com/file/d/1BEHjMnl3zxkw9zjaJoQPMleziqcSdSLl/view "Senior e-cards")


### Using QGIS

1. If you are on technology classrom computers, open QGIS.
If you are following along off-site and do not yet have QGIS on your machine, you can download it for free [here.](https://qgis.org/en/site/forusers/download.html "QGIS download")

2. Open QGIS.

![open qgis](/media/img/open_qgis.png)

3. Add a new project.

![new project](/media/img/new_doc.png)

Your screen should now look like this!

![screen layout](media/img/screen_layout.png)

4. Add a basemap to your project. A basemap provides context for the data that you bring in -- it's not always necessary, but it usually adds a nice touch.

![add basemap](media/img/add_basemap.png)

Your screen should now have a white and blue map of the Earth on it, like this:

![basemap](media/img/basemap.png)



### Coordinate systems 101

The main idea behind understanding projections and coordinate systems is that when we are creating maps, either on paper or digitally, we are attempting to take the round earth and depict it on a flat surface.

There are many ways of accomplishing this, none of which simultaneously preserves the shape of map features, area, distance and form. One if not more of these attributes will always be distorted. For this reason, you should always think about what the goals of your map are, who your audience is and the location you are choosing to depict before selecting a projection.

You can read more about projections here:
https://www.axismaps.com/guide/general/map-projections/


> **A quick note about coordinate systems:**
- Need to convert between coordinate systems on the earth’s surface (round) and the coordinate systems on your computer screen (flat)
- Simplest: use latitude/longitude
(we call this WGS 84, or EPSG:4326)
- Always check the bottom righthand corner to verify that your project is in your desired coordinate system!!

![coordinate](media/img/coordinate.png)


### Adding data to QGIS

#### Vector

#### Tabular


This workshop does not include the use of any raster data (think satellite imagery, georeferenced maps), but if you are interested in learning more about working with raster data in QGIS, please find the [Working with Raster Data QGIS Documentation](https://docs.qgis.org/2.8/en/docs/user_manual/working_with_raster/supported_data.html "Raster QGIS")


### Joining data in QGIS


### Editing symbology in QGIS


### QGIS layout tools


For any questions centered on geospatial data or mapping projects, please do not hesitate to contact us. The best way to get in touch is to fill out our [geospatial reference form.](https://www.leventhalmap.org/research/geospatial-data/ "Geospatial reference form") Please be as specific as possible in describing what you aim to achieve with your project, so we can know best how to help you!
