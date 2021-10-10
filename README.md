# Distance Calculator in Power BI using DAX (Data Analysis Expressions)

First Categorize all the coordinates under Latitude and Longitude . Then create one calculated column using the following code:

```DAX
Distance = 

var lat1=radians(Location_Data[Origin_Latitude])
var long1=radians(Location_Data[Origin_Longitude])
var Lat2 = radians(Location_Data[Destination_Latitude])
var long2=radians(Location_Data[Destination_Longitude])
var Erth_rdius = 6371 
//Erth_rdius in KM is 6371 

var dlat =(lat2-lat1)
var dlon =(long2-long1)
Var a = sin(dlat/2)^2 + cos(lat1)*cos(lat2)*sin(dlon/2)^2
var c = 2* ASIN(SQRT(a))
var distance = Erth_rdius*c
return
distance
```

![image](https://user-images.githubusercontent.com/83135594/136706026-2083ee09-cac1-4d24-b54b-de4bd99097d5.png)


