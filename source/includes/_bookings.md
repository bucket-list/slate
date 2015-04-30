# Bookings

The bookings endpoint allows you access to Adventure Bucket List's real time bookings engine.

## Get Booking

This endpoint retrieves a single booking with the given ID.  You can only retrieve information about bookings that you placed on the system.

### HTTP Request

`GET /v1/bookings/<ID>`

### Query Parameters

Parameter | Description
--- | ---
ID | The ID of the booking to retrieve

## Create Booking

Create a new booking with the given parameters

### HTTP Request

`POST /v1/bookings/`

### Parameters

Parameter | Description
--- | ---
eventId | The ID of the event the customer wishes to book
fullName | Customer first and last name
email | Customer email address
phone | Customer phone number
location | Json Object e.g. { street_address:'123 Main St', city:'San Jose', state:'CA', country:'US', coordinates:[100.5, 200.1] }
adults | Number of adults on the reservation
children | Number of children on the reservation
youths | Number of youths on the reservation
notes | Notes from the customer to activity operator

## Cancel Booking

This endpoint cancels a single booking with the given ID.  You can only cancel bookings that you placed on the system.

### HTTP Request

`POST /v1/bookings/<ID>`

### Parameters

Parameter | Description
--- | ---
ID | The ID of the booking to cancel
