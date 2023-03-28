# COMP3040 A3 part 1：

---
### Description:

The Winnipeg transit open source API allows users to input latitude and longitude coordinates for specific locations and receive unique location keys as output. Additionally, the API facilitates trip planning between two locations and provides information on available transit options for the journey. 

---

### List of end points and parameters:
* /v3/locations.json : The endpoints that return the locations, which are used for the trip planner. It takes the latitude and longitude and returns the location keys. The latitude and longitude should be searched on Google Maps and in at least 6 decimal places:
  
  * Parameter list:
     * api-key: The unique key that allowed you access the Winnipeg transit, for this assignment, it is **Ouh7yeOXam4Aj0a8_SEa**.
     * lon: The longtitude of your location.
     * lat: The latitude of your location. 
 

*  /v3/trip-planner.json: The end points that manage the method of trip. It takes 2 keys location and time, return possible transit methods.

 * Parameter list:
     * api-key: The unique key that allowed you access the Winnipeg transit, for this assignment, it is **Ouh7yeOXam4Aj0a8_SEa**.
     * origin: The start point of your trip. The format of this parameter should be **address/location_code**.
     * destination: The destination of your trip. The format of this parameter should also be **address/location_code**.
     * time: The time when you depart. The format should be **hh:mm**.


---

### Resources:

* For location part, here is a copy of resources.

 ![p1](/pic/res_loc.png)

The most important part is 'key', a number represent the location we choose. 

Following informations like street-number and street provide further details.

'geographic' contains the lat and lon we entered.


* For trip-planner part, the resources is huge and we have to check it seperately.
 
![p1](/pic/res_trip01.png)

This series of data are general infomation about our trip: the number of trip method; start and end time and the  time takes on different behaviors.

![p1](/pic/res_trip02.png)
  
'from' or 'to' indicates your origin and destination, it also contains the location key and infomations about the street.

![p1](/pic/res_trip03.png)

'route'provide more infomation about public transport. We only need to check the 'number' to get the route number. 
for this case, 'from' and 'to' will also show the stop name.

---

### Sample request and sample response:


* For location part, let us try the following values:

![p1](/pic/sample_loc01.png)

Status code 200 means it returns the key successfully.

![p1](/pic/sample_loc02.png)


* Let's try trip-planner:

![p1](/pic/sample_trip01.png)

And it returns:

![p1](/pic/sample_trip02.png)

---
