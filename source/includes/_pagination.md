# Pagination

The Adventure Bucket List provides access to a vast wealth of tour options.  To avoid asking for too much information, and in order to keep our servers performing nimbly, the API will automatically paginate your requested items.

## Basics

```shell
curl -I https://api.adventurebucketlist.com/v1/tours?location=[120.5%2C%200.5]
```

```ruby
# Get tour using location query param
query = { "location" => [120.5, 200.5], "pageSize" => 50 }
tours = client.get_tours(query)
```

```python
# Get tour using location query param
query = { "location": [120.5, 200.5], "pageSize": 50 }
tours = client.get_tours(body=query)
```

```javascript
// Get tour using location query param
query = { "location": [120.5, 200.5], "pageSize": 50 };
tours = client.getTours(query);
```

```php
<?php
// Get tour using location query param
query = [ "location" => [120.5, 200.5], "pageSize" => 50 ];
tours = client->getTours(query);
?>
```

The default number of items returned per page is 25.  You can specify how many items to return (up to a maximum of 50).

Parameter | Description
--- | ---
`page` | Integer, the number of the page requested
`pageSize` | Integer, the number of items to return per page

## Consuming Links

> Response headers include pagination urls

```shell
X-Next-Page-Url: https://api.adventurebucketlist.com/v1/tours?location=[120.5%2C%200.5]&pageSize=50&page=2
X-Last-Page-Url: https://api.adventurebucketlist.com/v1/tours?location=[120.5%2C%200.5]&pageSize=50&page=34
```

```ruby
# Last Page
last_response = client.last_response
last_response.get_last_page()
```

```python
# Last Page
last_response = client.last_response
last_response.get_last_page()
```

```javascript
// Last Page
lastResponse = client.lastResponse
lastResponse.getLastPage()
```

```php
<?php
// Last Page
lastResponse = client.lastResponse
lastResponse->getLastPage()
?>
```

Here are the possible headers values:

Header | Description
--- | ---
X-Next-Page-Url	| Shows the URL of the immediate next page of results.
X-Last-Page-Url	| Shows the URL of the last page of results.
X-First-Page-Url | Shows the URL of the first page of results.
X-Prev-Page-Url	| Shows the URL of the immediate previous page of results.


The `X-Next-Page-Url` header tells us that the next page is `page=2`.  For the first call using this query, this makes sense, because we expect to be on `page=1` currently. The `X-Last-Page-Url` header provides even more information, telling us we have 33 more pages of data we could request.

The ABL API Clients make getting any page easy.
