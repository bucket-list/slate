# Activities

Activities objects contain all information about what, where and when that activity will take place. The timeslot sub-object gives information about the different times, occupancy and prices offered.

## Get All Activities

This endpoint retrieves all tours based on a given query.

### HTTP Request

`GET /v1/activities/`

### Query Parameters

Parameter | Description
--- | ---
`location` | Coordinate point or Street Address, City, State/Province, Country
`distance` | enum  `['5km', '10km', '25km', '50km', '5mi', '10mi', '25mi', '50mi']`
`category` | Use commas to delimit categories, colons delimit category and subcategory
`price` | Float values of minimum and maximum prices desired, format `[min, max]`

## Get Single Activity

This endpoint retrieves a single activity with the given ID.

### HTTP Request

`GET /v1/activities/<ID>`

### Query Parameters

Parameter | Description
--- | ---
ID | The ID of the activity to retrieve
