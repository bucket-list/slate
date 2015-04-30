# Rate Limiting

### HTTP Response Headers

The following headers are applied per minute to public and authenticated requests:

Header | Description
---|---
`X-Rate-Limit-Limit` | The number of requests you can send within your rate limit window
`X-Rate-Limit-Remaining` | The number of requests that you can send before you will exceed your rate limit
`X-Rate-Limit-Reset` | When your next rate limit window will be reset (in UTC [epoch milliseconds](http://en.wikipedia.org/wiki/Unix_time))
