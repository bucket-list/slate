# Events

Events are an individual occurrences of activities.  Event objects contain information about time, occupancy, availability and price.

## Get All Events

```shell
curl -X GET 'https://api.adventurebucketlist.com/api/v1/events?activityId=558b0aafc59ff947062f8fb4&dateRange%5B%5D=2015-06-01T07%3A00%3A00.000Z&dateRange%5B%5D=2015-07-01T07%3A00%3A00.000Z'
```

```ruby
# Get all events with the following query
query = {
  "activityId" => "552ea021a09742a705853cf8",
  "dateRange" => [
    "2015-06-01T07:00:00.000Z",
    "2015-07-01T07:00:00.000Z"
  ]
}
client.get_events(query)
```

```python
# Get all events with the following query
query = {
  "activityId": "552ea021a09742a705853cf8",
  "dateRange": [
    "2015-06-01T07:00:00.000Z",
    "2015-07-01T07:00:00.000Z"
  ]
}
client.get_events(query)
```

```javascript
// Get all events with the following query
query = {
  "activityId": "552ea021a09742a705853cf8",
  "dateRange": [
    "2015-06-01T07:00:00.000Z",
    "2015-07-01T07:00:00.000Z"
  ]
}
client.getEvents(query, function (err, events) {
  console.log("events err", err);
  console.log("events", events);
});
```

```php
<?php
// Get all activities with the following query (page limit applies)
query = {
  "activityId" => "552ea021a09742a705853cf8",
  "dateRange" => [
    "2015-06-01T07:00:00.000Z",
    "2015-07-01T07:00:00.000Z"
  ]
};
$client->getEvents($query);
?>
```

> Expected return value

```shell
$ curl -i https://api.adventurebucketlist.com/v1/events
HTTP/1.1 200 OK
Content-Type: application/json; charset=UTF-8
X-Rate-Limit-Limit: 120
X-Rate-Limit-Remaining: 119
X-Rate-Limit-Reset: 1424380431341

{
   "timeslots":[
      {
         "_id":"558b0aaec59ff947062f8fb2",
         "title":"Surfing in Tofino",
         "duration":6,
         "daysRunning":[0,1,2,3],
         "maxOcc":5,
         "minOcc":2,
         "charges":[
            {
               "_id":"558b0aaec59ff947062f8fac",
               "description":"Adult Price",
               "type":"adult",
               "amount":120
            },
            {
               "_id":"558b0aaec59ff947062f8fad",
               "description":"Youth Price",
               "type":"youth",
               "amount":105
            }
         ],
         "events":[
            {
               "_id":"558dc4c27c6f506f63cbcf8f",
               "startTime":"2015-06-25T14:15:00.000Z",
               "endTime":"2015-06-25T20:15:00.000Z",
               "available":5
            }
         ]
      }
   ]
}
```

```ruby
# Hashie::Mash Object
timeslots.each do |timeslot|
  timeslot.id # "558dc4c27c6f506f63cbcf8f"
  timeslot.events.each do |event|
    event.available # remaining space, e.g. 8
  end
end
```

```python
# Dict Object
{
   "timeslots":[
      {
         "_id":"558b0aaec59ff947062f8fb2",
         "title":"Surfing in Tofino",
         "duration":6,
         "daysRunning":[0,1,2,3],
         "maxOcc":5,
         "minOcc":2,
         "charges":[
            {
               "_id":"558b0aaec59ff947062f8fac",
               "description":"Adult Price",
               "type":"adult",
               "amount":120
            },
            {
               "_id":"558b0aaec59ff947062f8fad",
               "description":"Youth Price",
               "type":"youth",
               "amount":105
            }
         ],
         "events":[
            {
               "_id":"558dc4c27c6f506f63cbcf8f",
               "startTime":"2015-06-25T14:15:00.000Z",
               "endTime":"2015-06-25T20:15:00.000Z",
               "available":5
            }
         ]
      }
   ]
}
```

```javascript
// Json Object
{
   "timeslots":[
      {
         "_id":"558b0aaec59ff947062f8fb2",
         "title":"Surfing in Tofino",
         "duration":6,
         "daysRunning":[0,1,2,3],
         "maxOcc":5,
         "minOcc":2,
         "charges":[
            {
               "_id":"558b0aaec59ff947062f8fac",
               "description":"Adult Price",
               "type":"adult",
               "amount":120
            },
            {
               "_id":"558b0aaec59ff947062f8fad",
               "description":"Youth Price",
               "type":"youth",
               "amount":105
            }
         ],
         "events":[
            {
               "_id":"558dc4c27c6f506f63cbcf8f",
               "startTime":"2015-06-25T14:15:00.000Z",
               "endTime":"2015-06-25T20:15:00.000Z",
               "available":5
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
   "timeslots" => [
      [
         "_id" => "558b0aaec59ff947062f8fb2",
         "title" => "Surfing in Tofino",
         "duration" => 6,
         "daysRunning" => [0,1,2,3],
         "maxOcc" => 5,
         "minOcc" => 2,
         "charges" => [
            [
               "_id" => "558b0aaec59ff947062f8fac",
               "description" => "Adult Price",
               "type" => "adult",
               "amount" => 120
            ],
            [
               "_id" => "558b0aaec59ff947062f8fad",
               "description" => "Youth Price",
               "type" => "youth",
               "amount" => 105
            ]
         ],
         "events" => [
            [
               "_id" => "558dc4c27c6f506f63cbcf8f",
               "startTime" => "2015-06-25T14 => 15 => 00.000Z",
               "endTime" => "2015-06-25T20 => 15 => 00.000Z",
               "available" => 5
            ]
         ]
      ]
   ]
]
?>
```

This endpoint retrieves all events based on a given query.

### HTTP Request

`GET /v1/events/`

### Query Parameters

Parameter | Description
--- | ---
`activityId` | The ID of the activity to which the events belong (required)
`dateRange` | array containing start and end dates in ISO8601 format

## Get Single Event

```shell
curl -X GET 'https://api.adventurebucketlist.com/api/v1/events/558b0aafc59ff947062f8fb4'
```

```ruby
# Get event with the ID
event_id = '558b0aafc59ff947062f8fb4'
client.get_event_by_id(event_id)
```

```python
# Get event with the ID
event_id = '558b0aafc59ff947062f8fb4'
client.get_event_by_id(event_id)
```

```javascript
// Get event with the ID
var eventId = '558b0aafc59ff947062f8fb4';
client.getActivityById(eventId, function (err, event) {
  console.log("event err", err);
  console.log("event", event);
});
```

```php
<?php
// Get event with the ID
$eventId = '558b0aafc59ff947062f8fb4';
$client->getEventById($eventId);
?>
```

> Expected return value

```shell
$ curl -i https://api.adventurebucketlist.com/v1/events/1
HTTP/1.1 200 OK
Content-Type: application/json; charset=UTF-8
X-Rate-Limit-Limit: 120
X-Rate-Limit-Remaining: 119
X-Rate-Limit-Reset: 1424380431341

{
  "_id":"558dc4c27c6f506f63cbcf8f",
  "title":"Surfing in Tofino",
  "startTime":"2015-06-25T14:15:00.000Z",
  "endTime":"2015-06-25T20:15:00.000Z",
  "available":5,
  "maxOcc":5,
  "minOcc":2,
  "charges":[
    {
      "_id":"558b0aaec59ff947062f8fac",
      "description":"Adult Price",
      "type":"adult",
      "amount":120
    },
    {
      "_id":"558b0aaec59ff947062f8fad",
      "description":"Youth Price",
      "type":"youth",
      "amount":105
    }
  ]
}
```

```ruby
# Hashie::Mash Object
event.id # "558dc4c27c6f506f63cbcf8f"
event.charges.each do |charge|
  charge.amount # 120
  charge.type # adult
end
```

```python
# Dict Object
{
  "_id":"558dc4c27c6f506f63cbcf8f",
  "title":"Surfing in Tofino",
  "startTime":"2015-06-25T14:15:00.000Z",
  "endTime":"2015-06-25T20:15:00.000Z",
  "available":5,
  "maxOcc":5,
  "minOcc":2,
  "charges":[
    {
      "_id":"558b0aaec59ff947062f8fac",
      "description":"Adult Price",
      "type":"adult",
      "amount":120
    },
    {
      "_id":"558b0aaec59ff947062f8fad",
      "description":"Youth Price",
      "type":"youth",
      "amount":105
    }
  ]
}
```

```javascript
// Json Object
{
  "_id":"558dc4c27c6f506f63cbcf8f",
  "title":"Surfing in Tofino",
  "startTime":"2015-06-25T14:15:00.000Z",
  "endTime":"2015-06-25T20:15:00.000Z",
  "available":5,
  "maxOcc":5,
  "minOcc":2,
  "charges":[
    {
      "_id":"558b0aaec59ff947062f8fac",
      "description":"Adult Price",
      "type":"adult",
      "amount":120
    },
    {
      "_id":"558b0aaec59ff947062f8fad",
      "description":"Youth Price",
      "type":"youth",
      "amount":105
    }
  ]
}
```

```php
<?php
// Array Object
[
  "_id" => "558dc4c27c6f506f63cbcf8f",
  "title" => "Surfing in Tofino",
  "startTime" => "2015-06-25T14:15:00.000Z",
  "endTime" => "2015-06-25T20:15:00.000Z",
  "available" => 5,
  "maxOcc" => 5,
  "minOcc" => 2,
  "charges" => [
    [
      "_id" => "558b0aaec59ff947062f8fac",
      "description" => "Adult Price",
      "type" => "adult",
      "amount" => 120
    ],
    [
      "_id" => "558b0aaec59ff947062f8fad",
      "description" => "Youth Price",
      "type" => "youth",
      "amount" => 105
    ]
  ]
]
?>
```

This endpoint retrieves all events based on a given query.

### HTTP Request

`GET /v1/event/<ID>`

### Query Parameters

Parameter | Description
--- | ---
ID | The ID of the event to retrieve
