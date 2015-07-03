# Bookings

The bookings endpoint allows you access to the real-time bookings engine.

## Get Booking

```shell
curl -X GET 'https://api.adventurebucketlist.com/v1/bookings/e3afed81-4a9c-4480-a78a-e0872408b95a'
```

```ruby
# Get booking with the ID
booking_id = 'e3afed81-4a9c-4480-a78a-e0872408b95a'
client.get_booking_by_id(booking_id)

# For convenience, you can also get booking by full URL
url = 'https://api.adventurebucketlist.com/v1/bookings/3f002e80-62c6-4274-a2d7-3f191923be09'
client.get_booking_by_url(url)
```

```python
# Get booking with the ID
booking_id = 'e3afed81-4a9c-4480-a78a-e0872408b95a'
client.get_booking_by_id(booking_id)

# For convenience, you can also get booking by full URL
url = 'https://api.adventurebucketlist.com/v1/bookings/3f002e80-62c6-4274-a2d7-3f191923be09'
client.get_booking_by_url(url)
```

```javascript
// Get booking with the ID
var bookingId = 'e3afed81-4a9c-4480-a78a-e0872408b95a';
client.getBookingById(bookingId, function (err, booking) {
  console.log("booking err", err);
  console.log("booking", booking);
});

// For convenience, you can also get booking by full URL
var url = 'https://api.adventurebucketlist.com/v1/bookings/3f002e80-62c6-4274-a2d7-3f191923be09';
client.getBookingByUrl(url, function (err, booking) {
  console.log("booking err", err);
  console.log("booking", booking);
});
```

```php
<?php
// Get booking with the ID
$bookingId = 'e3afed81-4a9c-4480-a78a-e0872408b95a';
$client->getBookingById($bookingId);

// For convenience, you can also get booking by full URL
$url = 'https://api.adventurebucketlist.com/v1/bookings/3f002e80-62c6-4274-a2d7-3f191923be09';
$client->getBookingByUrl($url);
?>
```

> Expected return value

```shell
$ curl -i https://api.adventurebucketlist.com/v1/bookings/1
HTTP/1.1 200 OK
Content-Type: application/json; charset=UTF-8
X-Rate-Limit-Limit: 120
X-Rate-Limit-Remaining: 119
X-Rate-Limit-Reset: 1424380431341

{
   "bookingId":"1",
   "notes":"These are my test notes",
   "title":"Hummingbird Walking Tour",
   "attendees":{
      "adult":1,
      "youth":0
   },
   "status":"active",
   "transactions": [
      {
         "type":"payment",
         "attendees":{
            "adult":1,
            "youth":0
         },
         "subtotal":20,
         "total":21.9,
         "created":"2015-07-01T03:14:06.712Z",
         "paymentMethod":"cash"
      }
   ],
   "customer": {
      "fullName":"Kevin Adams",
      "location": {
         "streetAddress":"123 Main Street",
         "city":"San Jose",
         "state":"California",
         "country":"United States",
         "location": {
            "coordinates": [
               -121.88316800000001,
               37.3511049
            ],
            "type":"Point"
         },
         "type":"customer",
         "tag":"Main Location"
      },
      "email":"kevinadams77@yahoo.com",
      "phoneNumber":"6506191125"
   }
}
```

```ruby
# Hashie::Mash Object
booking.bookingId # "886313e1-3b8a-5372-9b90-0c9aee199e5d"
booking.status # "active"
booking.startTime # "2014-05-06T13:15:30Z"
```

```python
# Dict Object
{
   "bookingId":"1",
   "notes":"These are my test notes",
   "title":"Hummingbird Walking Tour",
   "attendees":{
      "adult":1,
      "youth":0
   },
   "status":"active",
   "transactions": [
      {
         "type":"payment",
         "attendees":{
            "adult":1,
            "youth":0
         },
         "subtotal":20,
         "total":21.9,
         "created":"2015-07-01T03:14:06.712Z",
         "paymentMethod":"cash"
      }
   ],
   "customer": {
      "fullName":"Kevin Adams",
      "location": {
         "streetAddress":"123 Main Street",
         "city":"San Jose",
         "state":"California",
         "country":"United States",
         "location": {
            "coordinates": [
               -121.88316800000001,
               37.3511049
            ],
            "type":"Point"
         },
         "type":"customer",
         "tag":"Main Location"
      },
      "email":"kevinadams77@yahoo.com",
      "phoneNumber":"6506191125"
   }
}
```

```javascript
// Json Object
{
   "bookingId":"1",
   "notes":"These are my test notes",
   "title":"Hummingbird Walking Tour",
   "attendees":{
      "adult":1,
      "youth":0
   },
   "status":"active",
   "transactions": [
      {
         "type":"payment",
         "attendees":{
            "adult":1,
            "youth":0
         },
         "subtotal":20,
         "total":21.9,
         "created":"2015-07-01T03:14:06.712Z",
         "paymentMethod":"cash"
      }
   ],
   "customer": {
      "fullName":"Kevin Adams",
      "location": {
         "streetAddress":"123 Main Street",
         "city":"San Jose",
         "state":"California",
         "country":"United States",
         "location": {
            "coordinates": [
               -121.88316800000001,
               37.3511049
            ],
            "type":"Point"
         },
         "type":"customer",
         "tag":"Main Location"
      },
      "email":"kevinadams77@yahoo.com",
      "phoneNumber":"6506191125"
   }
}
```

```php
<?php
// Array Object
[
   "bookingId" => "1",
   "notes" => "These are my test notes",
   "title" => "Hummingbird Walking Tour",
   "attendees" => [
      "adult" => 1,
      "youth" => 0
   ],
   "status" => "active",
   "transactions" => [
      [
         "type" => "payment",
         "attendees" => [
            "adult" => 1,
            "youth" => 0
         ],
         "subtotal" => 20,
         "total" => 21.9,
         "created" => "2015-07-01T03 => 14 => 06.712Z",
         "paymentMethod" => "cash"
      ]
   ],
   "customer" => [
      "fullName" => "Kevin Adams",
      "location" => [
         "streetAddress" => "123 Main Street",
         "city" => "San Jose",
         "state" => "California",
         "country" => "United States",
         "location" => [
            "coordinates" => [
               -121.88316800000001,
               37.3511049
            ],
            "type" => "Point"
         ],
         "type" => "customer",
         "tag" => "Main Location"
      ],
      "email" => "kevinadams77@yahoo.com",
      "phoneNumber" => "6506191125"
   ]
]
?>
```

This endpoint retrieves a single booking with the given ID.  You can only retrieve information about bookings that you placed on the system.

### HTTP Request

`GET /v1/bookings/<ID>`

### Query Parameters

Parameter | Description
--- | ---
ID | The ID of the booking to retrieve

## Create Booking


```ruby
# booking a customer with 1 adult and 1 youth
booking = {
  :eventId => "8b8ctkgnngr2pi1cotb872oubg_20150415T170000Z",
  :fullName => "Phil Miller",
  :email => "phil@miller.com",
  :phoneNumber => "16506225555",
  :location => {
    :streetAddress => "123 Main St",
    :city => "New York",
    :state => "NY",
    :country => "US",
    :coordinates => [100.5,200.1]
  },
  :adults => 1,
  :youths => 1,
  :notes => "Please have them back in one piece"
}

client.create_booking(booking)
```

```python
# booking a customer with 1 adult and 1 youth
booking = {
  "eventId": "8b8ctkgnngr2pi1cotb872oubg_20150415T170000Z",
  "fullName": "Phil Miller",
  "email": "phil@miller.com",
  "phoneNumber": "16506225555",
  "location": {
    "streetAddress": "123 Main St",
    "city": "New York",
    "state": "NY",
    "country": "US",
    "coordinates": [100.5,200.1]
  },
  "adults": 1,
  "youths": 1,
  "notes": "Please have them back in one piece"
}

client.create_booking(booking)
```

```javascript
// booking a customer with 1 adult and 1 youth
booking = {
  "eventId": "8b8ctkgnngr2pi1cotb872oubg_20150415T170000Z",
  "fullName": "Phil Miller",
  "email": "phil@miller.com",
  "phoneNumber": "16506225555",
  "adults": 1,
  "youths": 1,
  "notes": "Please have them back in one piece",
  "location": {
    "streetAddress": "123 Main St",
    "city": "New York",
    "state": "NY",
    "country": "US",
    "coordinates": [100.5,200.1]
  }
};

client.createBooking(booking);
```

```php
<?php
// booking a customer with 1 adult and 1 youth
$booking = {
  "eventId" => "8b8ctkgnngr2pi1cotb872oubg_20150415T170000Z",
  "fullName" => "Phil Miller",
  "email" => "phil@miller.com",
  "phoneNumber" => "16506225555",
  "location" => {
    "streetAddress" => "123 Main St",
    "city" => "New York",
    "state" => "NY",
    "country" => "US",
    "coordinates" => [100.5,200.1]
  },
  "adults" => 1,
  "youths" => 1,
  "notes" => "Please have them back in one piece"
};

$client.createBooking($booking)
?>
```

> A successful booking creation returns the url location of the new booking in the response location header with HTTP Response Code of 202.

```shell
HTTP/1.1 202 ACCEPTED
Location: 'https://api.adventurebucketlist.com/v1/bookings/3f002e80-62c6-4274-a2d7-3f191923be09'
```

```ruby
# string
'https://api.adventurebucketlist.com/v1/bookings/3f002e80-62c6-4274-a2d7-3f191923be09'
```

```python
# string
'https://api.adventurebucketlist.com/v1/bookings/3f002e80-62c6-4274-a2d7-3f191923be09'
```

```javascript
// string
'https://api.adventurebucketlist.com/v1/bookings/3f002e80-62c6-4274-a2d7-3f191923be09'
```

```php
<?php
// string
'https://api.adventurebucketlist.com/v1/bookings/3f002e80-62c6-4274-a2d7-3f191923be09'
?>
```

Create a new booking with the given parameters

### HTTP Request

`POST /v1/bookings/`

### Parameters

Parameter | Description
--- | ---
eventId | The ID of the event the customer wishes to book
fullName | Customer first and last name
email | Customer email address
Number | Customer phone number
location | Json Object e.g. { streetAddress:'123 Main St', city:'San Jose', state:'CA', country:'US', coordinates:[100.5, 200.1] }
adults | Number of adults on the reservation
children | Number of children on the reservation
youths | Number of youths on the reservation
notes | Notes from the customer to activity operator

## Cancel Booking

```shell
curl -X DELETE 'https://api.adventurebucketlist.com/v1/bookings/e3afed81-4a9c-4480-a78a-e0872408b95a'
```

```ruby
booking_id = 'e3afed81-4a9c-4480-a78a-e0872408b95a'
client.cancel_booking(booking_id)
```

```python
booking_id = 'e3afed81-4a9c-4480-a78a-e0872408b95a'
client.cancel_booking(booking_id)
```

```javascript
var bookingId = 'e3afed81-4a9c-4480-a78a-e0872408b95a';
client.cancelBooking(bookingId, function (err, msg) {
  console.log("cancel booking err", err);
  console.log("cancel booking", msg);
});
```

```php
<?php
$bookingId = 'e3afed81-4a9c-4480-a78a-e0872408b95a';
$client->cancelBooking($bookingId);
?>
```

> The above command returns an HTTP response with status code 204

```shell
HTTP/1.1 204
```

```ruby
# Hashie::Mash Object
response.status # 204
response.message # "This operation has completed successfully"
```

```python
# Dict Object
{ "status": 204, message: "This operation has completed successfully" }
```

```javascript
// JSON Object
{ status: 204, message: "This operation has completed successfully" }
```

```php
<?php
// Array Object
[ "status" => 204, "message" => "This operation has completed successfully" ]
?>
```

This endpoint cancels a single booking with the given ID.  You can only cancel bookings that you placed on the system.

### HTTP Request

`DELETE /v1/bookings/<ID>`

### Parameters

Parameter | Description
--- | ---
ID | The ID of the booking to cancel
