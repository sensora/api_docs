Sensora
======
All api calls require a valid api key.Get one at [http://sensora.net](Sensora.net)

API endpoints
=======

## Get Methods

### api/locate/:latitude/:longitude/:areasize
Returns json data with sensors inside an area [default: 2kms] from the origin point. Area size must be expressed in meters.

### api/sensor/:id
Returns profile and last insert data for given sensor.

### api/sensor/:id/:fromdate/:todate
Returns data for sensor between dates. Dates must be linux time strings.

## Post Methods

### api/sensor
id and sensor_id are required.
Saves data for sensor. All data fields are optional so you can upload what you can. Valid data params are: temperature, moisture, altitude, pressure, sound.