# Authentication

> To initialize the client, use this code:

```shell
# N/A, click on another language tab for example
```

```ruby
require 'bucket-list'

client = ABL::Client.new(
    :public_key => '<public_key>',
    :secret_key => '<secret_key>',
    :mode => '<mode>'
    )
```

```python
from bucketlist.client import ABLClient

client = ABL(
    api_key='<api_key>',
    api_secret='<api_secret>',
    mode='<mode>'
    )
```

```javascript
var abl = require('abl-client-node')
var client = abl(
    '<api_key>',
    '<api_secret>',
    '<environment>',
    '<version>'
    );
```

```php
<?php
require 'vendor/autoload.php';
use ABL\Client\ABLClient;

$client = ABLClient::factory([
    'publicKey' => '<public_key>',
    'secretKey' => '<secret_key>',
    'environment' => '<environment>'
    ]);
?>
```

>If you are not using a client, Authenticated Requests should include these headers:

```http
POST /endpoint HTTP/1.1
X-ABL-Access-Key: <YOUR_API_KEY>
X-ABL-Signature: <HMAC_SIGNATURE>
X-ABL-Date: <CURRENT_TIMESTAMP>
```

> The client will automatically sign your requests with the proper headers.

The Adventure Bucket List API provides a publicly accessible endpoint to query tours. Without authentication, this endpoint is subject to Rate Limits.

<aside class="warning">
You must always keep your API Keys secure to make sure no one can access your account.  If you think a key might be compromised, simply revoke your API key [here](https://www.adventurebucketlist.com/#/api).
</aside>

*If you are building your own client for the API...*

### Building an HMAC Signature with SHA-256

1. Concatenate the timestamp, request URL and parameters into a UTF-8 String:
2. Convert the message to Base64
3. Sign the message using HMAC with SHA-256 and your API Secret Key
4. Convert to Base64 once again

Encode a get request like this:

`1403755197367https://api.adventurebucketlist.com/v1/tours?location=[120.5%2C%200.5]`

Encode a post request like this:

`1403755197367https://api.adventurebucketlist.com/v1/tours{"title": "Super Fun Activity","description": "This tour is super fun","rating": "All Levels","required": ["shirt", "shoes"]}`
