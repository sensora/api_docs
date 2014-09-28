Sensora
======
All api calls require a valid api key.Get one at [http://sensora.net](Sensora.net)

API endpoints
=======

## Get Methods
### Required parameters
api_key
Ej. api/sensor/xxxx-xxxx-xxxx-xxxx?api_key=yourapikeyhere

### api/locate/:latitude/:longitude/:areasize
Returns json data with sensors inside an area [default: 5kms] from the origin point. Area size must be expressed in kilometers.

### api/sensor/:id
Returns profile and last insert data for given sensor.

### api/sensor/:id/:fromdate/:todate
Returns data for sensor between dates. Dates must be linux time strings.

## Post Methods
### Required parameters
api_key
sensor_id
Ej. api/sensor?key_id=xxxxxxx&sensor_id=xxxxx-xxxx-xxx-xxxxxx
### api/sensor
It receives an json object from an array like:
	$dataToSend = [
		'data' => [
			[
				'temperature'	=> 15,
				'moisture'	=> 75,
			],
			[
				'temperature'	=> 16,
				'moisture'	=> 72,
				'created_at'	=> '2014-09-28 05:00:00'
			],
		],
	];

	json_encode($dataToSend);

Saves data for sensor. All data fields are optional so you can upload what you can. Valid data params are: temperature, moisture, altitude, pressure, noise, light.