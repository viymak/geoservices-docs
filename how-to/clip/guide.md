[](guide.md "yes")


# How to clip data to a desired geography

In this guide, we will walk through the process of clipping a dataset to a desired extent.

GIS data is clipped by extent for a variety of reasons. A primary consideration is the size of the data. In this tutorial, we will take a fairly large dataset, building footprints for the state of Massachusetts, and clip it to the extent of a Boston neighborhood, Jamaica Plain.

In addition to wanting



**By the end of this tutorial, you will:**
- learn how to isolate a clipping extent from boundary data
- learn how to clip data using a clipping extent


## GIS Basics
**What does GIS do?**
- Create digital maps from existing data sources
- Perform spatial analysis, which doesn’t necessarily require actually making a map
- Collect and parse geographic data from individuals, satellites, sensors and so on
- Manage the spatial attributes of data

**GIS software packages**
- ESRI Arc Suite
 - The “Microsoft Office” of GIS
- FOSS (Free And Open Source Software) Alternatives
 - QGIS
- Software that doesn’t feel like GIS at all…
 - Google Maps, Apple Maps, Mapbox, Carto, other Web-based mapping tools

**Three major types of data:**
![types of data graphic](/media/img/types_data.png)

## Making the map!
You are going to make this map:
![mass map](/media/img/Mass_map.png)

1. **But first, you need to download the data.** [Click here](tinyurl.com/bpl-map-workshop "workshop data") for the data, and download the files **senior_ecards_counts.csv** and **ma_zipcodes.gpkg**.

![download](/media/img/download.png)

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

> **A quick note about coordinate systems:**
- Need to convert between coordinate systems on the earth’s surface (round) and the coordinate systems on your computer screen (flat)
- Simplest: use latitude/longitude
(we call this WGS 84, or EPSG:4326)
- Always check the bottom righthand corner to verify that your project is in your desired coordinate system!!

![coordinate](media/img/coordinate.png)


*grey-out text*




<details>
<summary>Example of a dropdown </summary>

- dropdown bullet 1<br>
- dropdown bullet 2

</details>


!> danger!

> note