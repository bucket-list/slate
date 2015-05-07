# Introduction to API

```shell
$ curl -i https://api.adventurebucketlist.com/v1/activities/1
HTTP/1.1 200 OK
Content-Type: application/json; charset=UTF-8
X-Rate-Limit-Limit: 120
X-Rate-Limit-Remaining: 119
X-Rate-Limit-Reset: 1424380431341

{
  "title": "Super Fun Activity",
  "description": "This activity is super fun",
  "rating": "All Levels",
  "required": ["shirt", "shoes"]
  ...
}
```

Adventure Bucket List provides developers with a simple and powerful REST API to integrate your applications with our Activities Marketplace, enabling you to display activity information and availability in real time and create bookings.

All API access is over HTTPS, and accessed at the [`https://api.adventurebucketlist.com`](https://api.adventurebucketlist.com) domain. All data is sent and received as JSON - `application/json`.
