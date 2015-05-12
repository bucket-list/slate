# Activities

Activities objects contain all information about what, where and when that activity will take place. The timeslot sub-object gives information about the different times, occupancy and prices offered.

## Get All Activities

```shell
curl -X GET 'https://api.adventurebucketlist.com/v1/activities'
```

```ruby
# Get all activities with the following query (page limit applies)
query = { "price" => [50, 100] }
client.get_activities(query)
```

```python
# Get all activities with the following query (page limit applies)
query = { "price": [50, 100] }
client.get_activities(query)
```

```javascript
// Get all activities with the following query (page limit applies)
var query = { "price": [50, 100] }
client.getActivities(query, function (err, activities) {
  console.log("activities err", err);
  console.log("activities", activities);
});
```

```php
<?php
// Get all activities with the following query (page limit applies)
query = { "price" => [50, 100] }
$client->getActivities($query);
?>
```

> Expected return value

```shell
$ curl -i https://api.adventurebucketlist.com/v1/activities/1
HTTP/1.1 200 OK
Content-Type: application/json; charset=UTF-8
X-Rate-Limit-Limit: 120
X-Rate-Limit-Remaining: 119
X-Rate-Limit-Reset: 1424380431341

{
  "activities": [
    {
      "id":"552ea021a09742a705853cf8"
      "title":"High Seas Catamaran Adventure",
      "operator": "Sea Breeze Adventures",
      "startDate":"Wed Apr 15 2015 00:00:00 GMT-0700 (PDT)",
      "endDate":"Wed Apr 29 2015 00:00:00 GMT-0700 (PDT)",
      "tz":"America/Los_Angeles",
      "youthPrice":50,
      "adultPrice":100,
      "category":"Land",
      "rating":"Beginners",
      "mainDescription":"This text can be between 200 and 1000 characters.",
      "image_lg":"https://images.adventurebucketlist.com/blue.jpg",
      "image_array":["https://images.adventurebucketlist.com/blue.jpg"],
      "addons":[{"amount":14.00,"label":"Lunch","description":"Your choice of sandwich, chips and soda"}],
      "taxes":[{"type":"percentage","amount":5.13,"description":"VAT"}],
      "unifiedDuration":false,
      "unifiedOcc":false,
      "unifiedPrice":true,
      "whatIncluded":["snorkel","fins","light snack"],
      "requirements":["must be able to swim"],
      "whatToBring":["sunscreen","swimsuit","sunglasses","towel"],
      "location":[
        {
          "locationTag":"Main Location",
          "coordinates":[-121.8983,37.3],
          "country":"United States",
          "state":"California",
          "city":"San Jose",
          "street_address":"664 N 2nd St, San Jose, CA 95112, USA"
        }
      ],
      "timeslots":[
        {
          "daysRunning":[1,3,6],
          "deposit":0,
          "startTime":"2015-04-15T17:00:00.000Z",
          "minOcc":1,
          "maxOcc":7,
          "duration":3,
          "eventId":"8b8ctkgnngr2pi1cotb872oubg"
        }
      ]
    }
  ]
}

```

```ruby
# Hashie::Mash Object
activities.each do |activity|
  activity.id # "886313e1-3b8a-5372-9b90-0c9aee199e5d"
  activity.whatIncluded.each do |include|
    include # snorkel, fins, light snack
  end
end
```

```python
# Dict Object
{
  "activities": [
    {
      "id":"552ea021a09742a705853cf8"
      "title":"High Seas Catamaran Adventure",
      "operator": "Sea Breeze Adventures",
      "startDate":"Wed Apr 15 2015 00:00:00 GMT-0700 (PDT)",
      "endDate":"Wed Apr 29 2015 00:00:00 GMT-0700 (PDT)",
      "tz":"America/Los_Angeles",
      "youthPrice":50,
      "adultPrice":100,
      "category":"Land",
      "rating":"Beginners",
      "mainDescription":"This text can be between 200 and 1000 characters.",
      "image_lg":"https://images.adventurebucketlist.com/blue.jpg",
      "image_array":["https://images.adventurebucketlist.com/blue.jpg"],
      "addons":[{"amount":14.00,"label":"Lunch","description":"Your choice of sandwich, chips and soda"}],
      "taxes":[{"type":"percentage","amount":5.13,"description":"VAT"}],
      "unifiedDuration":false,
      "unifiedOcc":false,
      "unifiedPrice":true,
      "whatIncluded":["snorkel","fins","light snack"],
      "requirements":["must be able to swim"],
      "whatToBring":["sunscreen","swimsuit","sunglasses","towel"],
      "location":[
        {
          "locationTag":"Main Location",
          "coordinates":[-121.8983,37.3],
          "country":"United States",
          "state":"California",
          "city":"San Jose",
          "street_address":"664 N 2nd St, San Jose, CA 95112, USA"
        }
      ],
      "timeslots":[
        {
          "daysRunning":[1,3,6],
          "deposit":0,
          "startTime":"2015-04-15T17:00:00.000Z",
          "minOcc":1,
          "maxOcc":7,
          "duration":3,
          "eventId":"8b8ctkgnngr2pi1cotb872oubg"
        }
      ]
    }
  ]
}
```

```javascript
// Json Object
{
  "activities": [
    {
      "id":"552ea021a09742a705853cf8"
      "title":"High Seas Catamaran Adventure",
      "operator": "Sea Breeze Adventures",
      "startDate":"Wed Apr 15 2015 00:00:00 GMT-0700 (PDT)",
      "endDate":"Wed Apr 29 2015 00:00:00 GMT-0700 (PDT)",
      "tz":"America/Los_Angeles",
      "youthPrice":50,
      "adultPrice":100,
      "category":"Land",
      "rating":"Beginners",
      "mainDescription":"This text can be between 200 and 1000 characters.",
      "image_lg":"https://images.adventurebucketlist.com/blue.jpg",
      "image_array":["https://images.adventurebucketlist.com/blue.jpg"],
      "addons":[{"amount":14.00,"label":"Lunch","description":"Your choice of sandwich, chips and soda"}],
      "taxes":[{"type":"percentage","amount":5.13,"description":"VAT"}],
      "unifiedDuration":false,
      "unifiedOcc":false,
      "unifiedPrice":true,
      "whatIncluded":["snorkel","fins","light snack"],
      "requirements":["must be able to swim"],
      "whatToBring":["sunscreen","swimsuit","sunglasses","towel"],
      "location":[
        {
          "locationTag":"Main Location",
          "coordinates":[-121.8983,37.3],
          "country":"United States",
          "state":"California",
          "city":"San Jose",
          "street_address":"664 N 2nd St, San Jose, CA 95112, USA"
        }
      ],
      "timeslots":[
        {
          "daysRunning":[1,3,6],
          "deposit":0,
          "startTime":"2015-04-15T17:00:00.000Z",
          "minOcc":1,
          "maxOcc":7,
          "duration":3,
          "eventId":"8b8ctkgnngr2pi1cotb872oubg"
        }
      ]
    }
  ]
}
```

```php
<?php
// Array Object
[
  "activities" => [
    [
      "id" => "552ea021a09742a705853cf8"
      "title" => "High Seas Catamaran Adventure",
      "operator" =>  "Sea Breeze Adventures",
      "startDate" => "Wed Apr 15 2015 00 => 00 => 00 GMT-0700 (PDT)",
      "endDate" => "Wed Apr 29 2015 00 => 00 => 00 GMT-0700 (PDT)",
      "tz" => "America/Los_Angeles",
      "youthPrice" => 50,
      "adultPrice" => 100,
      "category" => "Land",
      "rating" => "Beginners",
      "mainDescription" => "This text can be between 200 and 1000 characters.",
      "image_lg" => "https://images.adventurebucketlist.com/blue.jpg",
      "image_array" => ["https://images.adventurebucketlist.com/blue.jpg"],
      "addons" => [["amount" => 14.00,"label" => "Lunch","description" => "Your choice of sandwich, chips and soda"]],
      "taxes" => [["type" => "percentage","amount" => 5.13,"description" => "VAT"]],
      "unifiedDuration" => false,
      "unifiedOcc" => false,
      "unifiedPrice" => true,
      "whatIncluded" => ["snorkel","fins","light snack"],
      "requirements" => ["must be able to swim"],
      "whatToBring" => ["sunscreen","swimsuit","sunglasses","towel"],
      "location" => [
        [
          "locationTag" => "Main Location",
          "coordinates" => [-121.8983,37.3],
          "country" => "United States",
          "state" => "California",
          "city" => "San Jose",
          "street_address" => "664 N 2nd St, San Jose, CA 95112, USA"
        ]
      ],
      "timeslots" => [
        [
          "daysRunning" => [1,3,6],
          "deposit" => 0,
          "startTime" => "2015-04-15T17 => 00 => 00.000Z",
          "minOcc" => 1,
          "maxOcc" => 7,
          "duration" => 3,
          "eventId":"8b8ctkgnngr2pi1cotb872oubg"
        ]
      ]
    }
  ]
}
?>
```

This endpoint retrieves all activities based on a given query.

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

```shell
curl -X GET 'https://api.adventurebucketlist.com/v1/activities/e3afed81-4a9c-4480-a78a-e0872408b95a'
```

```ruby
# Get all activities with the following query
activity_id = 'e3afed81-4a9c-4480-a78a-e0872408b95a'
client.get_activity_by_id(activity_id)
```

```python
# Get activity with the ID
activity_id = 'e3afed81-4a9c-4480-a78a-e0872408b95a'
client.get_activity_by_id(activity_id)
```

```javascript
// Get activity with the ID
var activityId = 'e3afed81-4a9c-4480-a78a-e0872408b95a';
client.getActivityById(activityId, function (err, activity) {
  console.log("activity err", err);
  console.log("activity", activity);
});
```

```php
<?php
// Get activity with the ID
$activityId = 'e3afed81-4a9c-4480-a78a-e0872408b95a';
$client->getActivityById($activityId);
```

> Expected return value

```shell
$ curl -i https://api.adventurebucketlist.com/v1/activities/1
HTTP/1.1 200 OK
Content-Type: application/json; charset=UTF-8
X-Rate-Limit-Limit: 120
X-Rate-Limit-Remaining: 119
X-Rate-Limit-Reset: 1424380431341

{
  "id":"552ea021a09742a705853cf8"
    "title":"High Seas Catamaran Adventure",
    "operator": "Sea Breeze Adventures",
    "startDate":"Wed Apr 15 2015 00:00:00 GMT-0700 (PDT)",
    "endDate":"Wed Apr 29 2015 00:00:00 GMT-0700 (PDT)",
    "tz":"America/Los_Angeles",
    "youthPrice":50,
    "adultPrice":100,
    "category":"Land",
    "rating":"Beginners",
    "mainDescription":"This text can be between 200 and 1000 characters.",
    "image_lg":"https://images.adventurebucketlist.com/blue.jpg",
    "image_array":["https://images.adventurebucketlist.com/blue.jpg"],
    "addons":[{"amount":14.00,"label":"Lunch","description":"Your choice of sandwich, chips and soda"}],
    "taxes":[{"type":"percentage","amount":5.13,"description":"VAT"}],
    "unifiedDuration":false,
    "unifiedOcc":false,
    "unifiedPrice":true,
    "whatIncluded":["snorkel","fins","light snack"],
    "requirements":["must be able to swim"],
    "whatToBring":["sunscreen","swimsuit","sunglasses","towel"],
    "location":[
    {
      "locationTag":"Main Location",
      "coordinates":[-121.8983,37.3],
      "country":"United States",
      "state":"California",
      "city":"San Jose",
      "street_address":"664 N 2nd St, San Jose, CA 95112, USA"
    }
  ],
    "timeslots":[
    {
      "daysRunning":[1,3,6],
      "deposit":0,
      "startTime":"2015-04-15T17:00:00.000Z",
      "minOcc":1,
      "maxOcc":7,
      "duration":3,
      "eventId":"8b8ctkgnngr2pi1cotb872oubg"
    }
  ]
}

```

```ruby
# Hashie::Mash Object
activity.id # "886313e1-3b8a-5372-9b90-0c9aee199e5d"
activity.whatIncluded.each do |include|
include # snorkel, fins, light snack
end
```

```python
# Dict Object
{
  "id":"552ea021a09742a705853cf8"
    "title":"High Seas Catamaran Adventure",
    "operator": "Sea Breeze Adventures",
    "startDate":"Wed Apr 15 2015 00:00:00 GMT-0700 (PDT)",
    "endDate":"Wed Apr 29 2015 00:00:00 GMT-0700 (PDT)",
    "tz":"America/Los_Angeles",
    "youthPrice":50,
    "adultPrice":100,
    "category":"Land",
    "rating":"Beginners",
    "mainDescription":"This text can be between 200 and 1000 characters.",
    "image_lg":"https://images.adventurebucketlist.com/blue.jpg",
    "image_array":["https://images.adventurebucketlist.com/blue.jpg"],
    "addons":[{"amount":14.00,"label":"Lunch","description":"Your choice of sandwich, chips and soda"}],
    "taxes":[{"type":"percentage","amount":5.13,"description":"VAT"}],
    "unifiedDuration":false,
    "unifiedOcc":false,
    "unifiedPrice":true,
    "whatIncluded":["snorkel","fins","light snack"],
    "requirements":["must be able to swim"],
    "whatToBring":["sunscreen","swimsuit","sunglasses","towel"],
    "location":[
    {
      "locationTag":"Main Location",
      "coordinates":[-121.8983,37.3],
      "country":"United States",
      "state":"California",
      "city":"San Jose",
      "street_address":"664 N 2nd St, San Jose, CA 95112, USA"
    }
  ],
    "timeslots":[
    {
      "daysRunning":[1,3,6],
      "deposit":0,
      "startTime":"2015-04-15T17:00:00.000Z",
      "minOcc":1,
      "maxOcc":7,
      "duration":3,
      "eventId":"8b8ctkgnngr2pi1cotb872oubg"
    }
  ]
}
```

```javascript
// Json Object
{
  "id":"552ea021a09742a705853cf8"
    "title":"High Seas Catamaran Adventure",
    "operator": "Sea Breeze Adventures",
    "startDate":"Wed Apr 15 2015 00:00:00 GMT-0700 (PDT)",
    "endDate":"Wed Apr 29 2015 00:00:00 GMT-0700 (PDT)",
    "tz":"America/Los_Angeles",
    "youthPrice":50,
    "adultPrice":100,
    "category":"Land",
    "rating":"Beginners",
    "mainDescription":"This text can be between 200 and 1000 characters.",
    "image_lg":"https://images.adventurebucketlist.com/blue.jpg",
    "image_array":["https://images.adventurebucketlist.com/blue.jpg"],
    "addons":[{"amount":14.00,"label":"Lunch","description":"Your choice of sandwich, chips and soda"}],
    "taxes":[{"type":"percentage","amount":5.13,"description":"VAT"}],
    "unifiedDuration":false,
    "unifiedOcc":false,
    "unifiedPrice":true,
    "whatIncluded":["snorkel","fins","light snack"],
    "requirements":["must be able to swim"],
    "whatToBring":["sunscreen","swimsuit","sunglasses","towel"],
    "location":[
    {
      "locationTag":"Main Location",
      "coordinates":[-121.8983,37.3],
      "country":"United States",
      "state":"California",
      "city":"San Jose",
      "street_address":"664 N 2nd St, San Jose, CA 95112, USA"
    }
  ],
    "timeslots":[
    {
      "daysRunning":[1,3,6],
      "deposit":0,
      "startTime":"2015-04-15T17:00:00.000Z",
      "minOcc":1,
      "maxOcc":7,
      "duration":3,
      "eventId":"8b8ctkgnngr2pi1cotb872oubg"
    }
  ]
}
```

```php
<?php
// Array Object
[
  "id" => "552ea021a09742a705853cf8"
  "title" => "High Seas Catamaran Adventure",
  "operator" =>  "Sea Breeze Adventures",
  "startDate" => "Wed Apr 15 2015 00 => 00 => 00 GMT-0700 (PDT)",
  "endDate" => "Wed Apr 29 2015 00 => 00 => 00 GMT-0700 (PDT)",
  "tz" => "America/Los_Angeles",
  "youthPrice" => 50,
  "adultPrice" => 100,
  "category" => "Land",
  "rating" => "Beginners",
  "mainDescription" => "This text can be between 200 and 1000 characters.",
  "image_lg" => "https://images.adventurebucketlist.com/blue.jpg",
  "image_array" => ["https://images.adventurebucketlist.com/blue.jpg"],
  "addons" => [["amount" => 14.00,"label" => "Lunch","description" => "Your choice of sandwich, chips and soda"]],
  "taxes" => [["type" => "percentage","amount" => 5.13,"description" => "VAT"]],
  "unifiedDuration" => false,
  "unifiedOcc" => false,
  "unifiedPrice" => true,
  "whatIncluded" => ["snorkel","fins","light snack"],
  "requirements" => ["must be able to swim"],
  "whatToBring" => ["sunscreen","swimsuit","sunglasses","towel"],
  "location" => [
    [
      "locationTag" => "Main Location",
      "coordinates" => [-121.8983,37.3],
      "country" => "United States",
      "state" => "California",
      "city" => "San Jose",
      "street_address" => "664 N 2nd St, San Jose, CA 95112, USA"
    ]
  ],
  "timeslots" => [
    [
      "daysRunning" => [1,3,6],
      "deposit" => 0,
      "startTime" => "2015-04-15T17 => 00 => 00.000Z",
      "minOcc" => 1,
      "maxOcc" => 7,
      "duration" => 3,
      "eventId":"8b8ctkgnngr2pi1cotb872oubg"
    ]
  ]
]
?>
```

This endpoint retrieves a single activity with the given ID.

### HTTP Request

`GET /v1/activities/<ID>`

### Query Parameters

Parameter | Description
--- | ---
ID | The ID of the activity to retrieve
