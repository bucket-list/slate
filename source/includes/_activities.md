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
var query = { "price": [50, 100] };
client.getActivities(query, function (err, activities) {
  console.log("activities err", err);
  console.log("activities", activities);
});
```

```php
<?php
// Get all activities with the following query (page limit applies)
query = { "price" => [50, 100] };
$client->getActivities($query);
?>
```

> Expected return value

```shell
$ curl -i https://api.adventurebucketlist.com/v1/activities
HTTP/1.1 200 OK
Content-Type: application/json; charset=UTF-8
X-Rate-Limit-Limit: 120
X-Rate-Limit-Remaining: 119
X-Rate-Limit-Reset: 1424380431341

{
    "activities": [
    {
        "tz":"America/Mexico_City",
        "title":"Surfing in Tofino",
        "mainDescription":"Surfing is a surface water sport in which the wave rider, referred to as a surfer, rides on the forward or deep face of a moving wave, which is usually carrying the surfer toward the shore. Waves suitable for surfing are primarily found in the ocean, but can also be found in lakes or in rivers in the form of a standing wave or tidal bore. However, surfers can also utilize artificial waves such as those from boat wakes and the waves created in artificial wave pools.",
        "rating":"Intermediate",
        "category":"Water",
        "companyName":"Worldwide Surf Adventures",
        "location": {
            "streetAddress":"10 Main Street, Vancouver, BC V6J, Canada",
            "city":"Vancouver",
            "state":"British Columbia",
            "country":"Canada",
            "location": {
                "coordinates": [
                    -123.1383701,
                    49.2686033
                ],
                "type":"Point"
            },
            "type":"tour",
            "tag":"Main Location"
        },
        "image":"https://photos.ablsolution.com/photo1",
        "status":"active",
        "images": [
            "https://photos.ablsolution.com/photo1.jpg",
            "https://photos.ablsolution.com/photo2.jpg"
        ],
        "whatIncluded": [
            "Lunch",
            "Transportation",
            "Lessons"
        ],
        "requirements": [
            "Must be able to swim"
        ],
        "whatToBring": [
            "bathing suit",
            "Sunscreen"
        ],
        "charges": [
            {
                "description":"gst",
                "amount":7,
                "type":"tax"
            }
        ],
        "timeslots":[
            {
                "user":"558b0101c59ff947062f8f68",
                "title":"Surfing in Tofino",
                "startTime":"2015-06-25T14:15:00.000Z",
                "endTime":"2015-06-25T20:15:00.000Z",
                "duration":6,
                "daysRunning":[0,1,2,3],
                "maxOcc":5,
                "minOcc":2,
                "charges":[
                    {
                        "description":"Adult Price",
                        "type":"adult",
                        "amount":120
                    },
                    {
                        "description":"Youth Price",
                        "type":"youth",
                        "amount":105
                    }
                ]
            }
        ]
    }
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
        "tz":"America/Mexico_City",
        "title":"Surfing in Tofino",
        "mainDescription":"Surfing is a surface water sport in which the wave rider, referred to as a surfer, rides on the forward or deep face of a moving wave, which is usually carrying the surfer toward the shore. Waves suitable for surfing are primarily found in the ocean, but can also be found in lakes or in rivers in the form of a standing wave or tidal bore. However, surfers can also utilize artificial waves such as those from boat wakes and the waves created in artificial wave pools.",
        "rating":"Intermediate",
        "category":"Water",
        "companyName":"Worldwide Surf Adventures",
        "location": {
            "streetAddress":"10 Main Street, Vancouver, BC V6J, Canada",
            "city":"Vancouver",
            "state":"British Columbia",
            "country":"Canada",
            "location": {
                "coordinates": [
                    -123.1383701,
                    49.2686033
                ],
                "type":"Point"
            },
            "type":"tour",
            "tag":"Main Location"
        },
        "image":"https://photos.ablsolution.com/photo1",
        "status":"active",
        "images": [
            "https://photos.ablsolution.com/photo1.jpg",
            "https://photos.ablsolution.com/photo2.jpg"
        ],
        "whatIncluded": [
            "Lunch",
            "Transportation",
            "Lessons"
        ],
        "requirements": [
            "Must be able to swim"
        ],
        "whatToBring": [
            "bathing suit",
            "Sunscreen"
        ],
        "charges": [
            {
                "description":"gst",
                "amount":7,
                "type":"tax"
            }
        ],
        "timeslots":[
            {
                "user":"558b0101c59ff947062f8f68",
                "title":"Surfing in Tofino",
                "startTime":"2015-06-25T14:15:00.000Z",
                "endTime":"2015-06-25T20:15:00.000Z",
                "duration":6,
                "daysRunning":[0,1,2,3],
                "maxOcc":5,
                "minOcc":2,
                "charges":[
                    {
                        "description":"Adult Price",
                        "type":"adult",
                        "amount":120
                    },
                    {
                        "description":"Youth Price",
                        "type":"youth",
                        "amount":105
                    }
                ]
            }
        ]
    }]
}
```

```javascript
// Json Object
{
    "activities": [
    {
        "tz":"America/Mexico_City",
        "title":"Surfing in Tofino",
        "mainDescription":"Surfing is a surface water sport in which the wave rider, referred to as a surfer, rides on the forward or deep face of a moving wave, which is usually carrying the surfer toward the shore. Waves suitable for surfing are primarily found in the ocean, but can also be found in lakes or in rivers in the form of a standing wave or tidal bore. However, surfers can also utilize artificial waves such as those from boat wakes and the waves created in artificial wave pools.",
        "rating":"Intermediate",
        "category":"Water",
        "companyName":"Worldwide Surf Adventures",
        "location": {
            "streetAddress":"10 Main Street, Vancouver, BC V6J, Canada",
            "city":"Vancouver",
            "state":"British Columbia",
            "country":"Canada",
            "location": {
                "coordinates": [
                    -123.1383701,
                    49.2686033
                ],
                "type":"Point"
            },
            "type":"tour",
            "tag":"Main Location"
        },
        "image":"https://photos.ablsolution.com/photo1",
        "status":"active",
        "images": [
            "https://photos.ablsolution.com/photo1.jpg",
            "https://photos.ablsolution.com/photo2.jpg"
        ],
        "whatIncluded": [
            "Lunch",
            "Transportation",
            "Lessons"
        ],
        "requirements": [
            "Must be able to swim"
        ],
        "whatToBring": [
            "bathing suit",
            "Sunscreen"
        ],
        "charges": [
            {
                "description":"gst",
                "amount":7,
                "type":"tax"
            }
        ],
        "timeslots":[
            {
                "user":"558b0101c59ff947062f8f68",
                "title":"Surfing in Tofino",
                "startTime":"2015-06-25T14:15:00.000Z",
                "endTime":"2015-06-25T20:15:00.000Z",
                "duration":6,
                "daysRunning":[0,1,2,3],
                "maxOcc":5,
                "minOcc":2,
                "charges":[
                    {
                        "description":"Adult Price",
                        "type":"adult",
                        "amount":120
                    },
                    {
                        "description":"Youth Price",
                        "type":"youth",
                        "amount":105
                    }
                ]
            }
        ]
    }]
}
```

```php
<?php
// Array Object

[
  "activities" =>  [
  [
    "tz" => "America/Mexico_City",
    "title" => "Surfing in Tofino",
    "mainDescription" => "Surfing is a surface water sport in which the wave rider, referred to as a surfer, rides on the forward or deep face of a moving wave, which is usually carrying the surfer toward the shore. Waves suitable for surfing are primarily found in the ocean, but can also be found in lakes or in rivers in the form of a standing wave or tidal bore. However, surfers can also utilize artificial waves such as those from boat wakes and the waves created in artificial wave pools.",
    "rating" => "Intermediate",
    "category" => "Water",
    "companyName" => "Worldwide Surf Adventures",
    "location" =>  [
      "streetAddress" => "10 Main Street, Vancouver, BC V6J, Canada",
      "city" => "Vancouver",
      "state" => "British Columbia",
      "country" => "Canada",
      "location" => [
        "coordinates" => [
          -123.1383701,
          49.2686033
        ],
        "type" => "Point"
      ],
      "type" => "tour",
      "tag" => "Main Location"
    ],
    "image" => "https => //photos.ablsolution.com/photo1",
    "status" => "active",
    "images" =>  [
      "https => //photos.ablsolution.com/photo1.jpg",
      "https => //photos.ablsolution.com/photo2.jpg"
    ],
    "whatIncluded" => [
      "Lunch",
      "Transportation",
      "Lessons"
    ],
    "requirements" => [
      "Must be able to swim"
    ],
    "whatToBring" => [
      "bathing suit",
      "Sunscreen"
    ],
    "charges" => [
      [
        "description" => "gst",
        "amount" => 7,
        "type" => "tax"
      ]
    ],
    "timeslots" => [
      [
        "user" => "558b0101c59ff947062f8f68",
        "title" => "Surfing in Tofino",
        "startTime" => "2015-06-25T14 => 15 => 00.000Z",
        "endTime" => "2015-06-25T20 => 15 => 00.000Z",
        "duration" => 6,
        "daysRunning" => [0,1,2,3],
        "maxOcc" => 5,
        "minOcc" => 2,
        "charges" => [
          [
            "description" => "Adult Price",
            "type" => "adult",
            "amount" => 120
          ],
          [
            "description" => "Youth Price",
            "type" => "youth",
            "amount" => 105
          ]
        ]
      ]
    ]
  ]
]
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
  "tz":"America/Mexico_City",
  "title":"Surfing in Tofino",
  "mainDescription":"Surfing is a surface water sport in which the wave rider, referred to as a surfer, rides on the forward or deep face of a moving wave, which is usually carrying the surfer toward the shore. Waves suitable for surfing are primarily found in the ocean, but can also be found in lakes or in rivers in the form of a standing wave or tidal bore. However, surfers can also utilize artificial waves such as those from boat wakes and the waves created in artificial wave pools.",
  "rating":"Intermediate",
  "category":"Water",
  "companyName":"Worldwide Surf Adventures",
  "location": {
    "streetAddress":"10 Main Street, Vancouver, BC V6J, Canada",
    "city":"Vancouver",
    "state":"British Columbia",
    "country":"Canada",
    "location": {
      "coordinates": [
        -123.1383701,
        49.2686033
      ],
      "type":"Point"
    },
    "type":"tour",
    "tag":"Main Location"
  },
  "image":"https://photos.ablsolution.com/photo1",
  "status":"active",
  "images": [
    "https://photos.ablsolution.com/photo1.jpg",
    "https://photos.ablsolution.com/photo2.jpg"
  ],
  "whatIncluded": [
    "Lunch",
    "Transportation",
    "Lessons"
  ],
  "requirements": [
    "Must be able to swim"
  ],
  "whatToBring": [
    "bathing suit",
    "Sunscreen"
  ],
  "charges": [
    {
      "description":"gst",
      "amount":7,
      "type":"tax"
    }
  ],
  "timeslots":[
    {
      "user":"558b0101c59ff947062f8f68",
      "title":"Surfing in Tofino",
      "startTime":"2015-06-25T14:15:00.000Z",
      "endTime":"2015-06-25T20:15:00.000Z",
      "duration":6,
      "daysRunning":[0,1,2,3],
      "maxOcc":5,
      "minOcc":2,
      "charges":[
        {
          "description":"Adult Price",
          "type":"adult",
          "amount":120
        },
        {
          "description":"Youth Price",
          "type":"youth",
          "amount":105
        }
      ]
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
  "tz":"America/Mexico_City",
  "title":"Surfing in Tofino",
  "mainDescription":"Surfing is a surface water sport in which the wave rider, referred to as a surfer, rides on the forward or deep face of a moving wave, which is usually carrying the surfer toward the shore. Waves suitable for surfing are primarily found in the ocean, but can also be found in lakes or in rivers in the form of a standing wave or tidal bore. However, surfers can also utilize artificial waves such as those from boat wakes and the waves created in artificial wave pools.",
  "rating":"Intermediate",
  "category":"Water",
  "companyName":"Worldwide Surf Adventures",
  "location": {
    "streetAddress":"10 Main Street, Vancouver, BC V6J, Canada",
    "city":"Vancouver",
    "state":"British Columbia",
    "country":"Canada",
    "location": {
      "coordinates": [
        -123.1383701,
        49.2686033
      ],
      "type":"Point"
    },
    "type":"tour",
    "tag":"Main Location"
  },
  "image":"https://photos.ablsolution.com/photo1",
  "status":"active",
  "images": [
    "https://photos.ablsolution.com/photo1.jpg",
    "https://photos.ablsolution.com/photo2.jpg"
  ],
  "whatIncluded": [
    "Lunch",
    "Transportation",
    "Lessons"
  ],
  "requirements": [
    "Must be able to swim"
  ],
  "whatToBring": [
    "bathing suit",
    "Sunscreen"
  ],
  "charges": [
    {
      "description":"gst",
      "amount":7,
      "type":"tax"
    }
  ],
  "timeslots":[
    {
      "user":"558b0101c59ff947062f8f68",
      "title":"Surfing in Tofino",
      "startTime":"2015-06-25T14:15:00.000Z",
      "endTime":"2015-06-25T20:15:00.000Z",
      "duration":6,
      "daysRunning":[0,1,2,3],
      "maxOcc":5,
      "minOcc":2,
      "charges":[
        {
          "description":"Adult Price",
          "type":"adult",
          "amount":120
        },
        {
          "description":"Youth Price",
          "type":"youth",
          "amount":105
        }
      ]
    }
  ]
}
```

```javascript
// Json Object
{
  "tz":"America/Mexico_City",
  "title":"Surfing in Tofino",
  "mainDescription":"Surfing is a surface water sport in which the wave rider, referred to as a surfer, rides on the forward or deep face of a moving wave, which is usually carrying the surfer toward the shore. Waves suitable for surfing are primarily found in the ocean, but can also be found in lakes or in rivers in the form of a standing wave or tidal bore. However, surfers can also utilize artificial waves such as those from boat wakes and the waves created in artificial wave pools.",
  "rating":"Intermediate",
  "category":"Water",
  "companyName":"Worldwide Surf Adventures",
  "location": {
    "streetAddress":"10 Main Street, Vancouver, BC V6J, Canada",
    "city":"Vancouver",
    "state":"British Columbia",
    "country":"Canada",
    "location": {
      "coordinates": [
        -123.1383701,
        49.2686033
      ],
      "type":"Point"
    },
    "type":"tour",
    "tag":"Main Location"
  },
  "image":"https://photos.ablsolution.com/photo1",
  "status":"active",
  "images": [
    "https://photos.ablsolution.com/photo1.jpg",
    "https://photos.ablsolution.com/photo2.jpg"
  ],
  "whatIncluded": [
    "Lunch",
    "Transportation",
    "Lessons"
  ],
  "requirements": [
    "Must be able to swim"
  ],
  "whatToBring": [
    "bathing suit",
    "Sunscreen"
  ],
  "charges": [
    {
      "description":"gst",
      "amount":7,
      "type":"tax"
    }
  ],
  "timeslots":[
    {
      "user":"558b0101c59ff947062f8f68",
      "title":"Surfing in Tofino",
      "startTime":"2015-06-25T14:15:00.000Z",
      "endTime":"2015-06-25T20:15:00.000Z",
      "duration":6,
      "daysRunning":[0,1,2,3],
      "maxOcc":5,
      "minOcc":2,
      "charges":[
        {
          "description":"Adult Price",
          "type":"adult",
          "amount":120
        },
        {
          "description":"Youth Price",
          "type":"youth",
          "amount":105
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
  "tz" => "America/Mexico_City",
  "title" => "Surfing in Tofino",
  "mainDescription" => "Surfing is a surface water sport in which the wave rider, referred to as a surfer, rides on the forward or deep face of a moving wave, which is usually carrying the surfer toward the shore. Waves suitable for surfing are primarily found in the ocean, but can also be found in lakes or in rivers in the form of a standing wave or tidal bore. However, surfers can also utilize artificial waves such as those from boat wakes and the waves created in artificial wave pools.",
  "rating" => "Intermediate",
  "category" => "Water",
  "companyName" => "Worldwide Surf Adventures",
  "location" =>  [
    "streetAddress" => "10 Main Street, Vancouver, BC V6J, Canada",
    "city" => "Vancouver",
    "state" => "British Columbia",
    "country" => "Canada",
    "location" => [
      "coordinates" => [
        -123.1383701,
        49.2686033
      ],
      "type" => "Point"
    ],
    "type" => "tour",
    "tag" => "Main Location"
  ],
  "image" => "https => //photos.ablsolution.com/photo1",
  "status" => "active",
  "images" =>  [
    "https => //photos.ablsolution.com/photo1.jpg",
    "https => //photos.ablsolution.com/photo2.jpg"
  ],
  "whatIncluded" => [
    "Lunch",
    "Transportation",
    "Lessons"
  ],
  "requirements" => [
    "Must be able to swim"
  ],
  "whatToBring" => [
    "bathing suit",
    "Sunscreen"
  ],
  "charges" => [
    [
      "description" => "gst",
      "amount" => 7,
      "type" => "tax"
    ]
  ],
  "timeslots" => [
    [
      "user" => "558b0101c59ff947062f8f68",
      "title" => "Surfing in Tofino",
      "startTime" => "2015-06-25T14 => 15 => 00.000Z",
      "endTime" => "2015-06-25T20 => 15 => 00.000Z",
      "duration" => 6,
      "daysRunning" => [0,1,2,3],
      "maxOcc" => 5,
      "minOcc" => 2,
      "charges" => [
        [
          "description" => "Adult Price",
          "type" => "adult",
          "amount" => 120
        ],
        [
          "description" => "Youth Price",
          "type" => "youth",
          "amount" => 105
        ]
      ]
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
