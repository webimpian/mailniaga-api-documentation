# Sending Log

***

<mark style="color:green;">`GET`</mark> `/api/v0/logs`

Our endpoint has support feature to retrieve sending log according to client sending event on previous process.

Log data only available after sending event from our outbound mail server. If there is no sent email recorded, emails are considered in queue list waiting to be sent.



```markup
curl -X GET https://api.mailniaga.mx/api/v0/logs?limit=100&page=1 \
-H "Content-Type: application/json" \
-H "X-API-Key: <API_Key>" 
```



This endpoint support basic pagination to handle large log records by using pagination parameter `limit` and `page`.

Query string parameters.



***

<table data-full-width="true"><thead><tr><th>Parameter</th><th>Description</th><th>Condition</th></tr></thead><tbody><tr><td><code>limit</code></td><td>Limit record to fetch for each page. By default API will use 100 if not set.</td><td>Optional</td></tr><tr><td><code>page</code></td><td>Record page. This parameter is required to navigate and jump between page within pagination.</td><td><mark style="color:red;">Required</mark></td></tr></tbody></table>

***



JSON structure response.



```json
{
    "error": false,
    "status_code": 200,
    "message": "OK",
    "data": {
        "data": [
            {
                "_id": "64b7287eb7862e3f6f59458f",
                "id": "1896b7565ae00006b2",
                "user": "b76827cb24abfb5a2a110f6af1c965a0796db231",
                "domain": "mailniaga.com",
                "to": "demo_user@mailniaga.com",
                "status": {
                    "delivered": true,
                    "ip": "100.100.1001.100",
                    "mx": "mta7.am0.demo-client.net",
                    "response": "250 ok dirdel"
                },
                "sending_zone": "default",
                "interface": "api",
                "from": "mailniaga@newsletter.com.my",
                "zone_address": {
                    "address": "100.100.1001.100",
                    "name": "mailniaga-mx06.com",
                    "ratio": 0.3333333333333333
                },
                "created_at": "2023-07-19T00:04:14.362Z"
            },
            {
                "_id": "64b7287b2b08e08e63dceab5",
                "id": "1896b75753b000e61b",
                "user": "b76827cb24abfb5a2a110f6af1c965a0796db231",
                "domain": "mailniaga.com",
                "to": "demo@demo.com",
                "status": {
                    "delivered": true,
                    "ip": "139.99.84.189",
                    "mx": "mta7.am0.demo-client.net",
                    "response": "250 ok dirdel"
                },
                "sending_zone": "default",
                "interface": "api",
                "from": "mailniaga@newsletter.com.my",
                "zone_address": {
                    "address": "139.99.84.189",
                    "name": "mailniaga-mx05.com",
                    "ratio": 0.3333333333333333
                },
                "created_at": "2023-07-19T00:04:11.549Z"
            }
        ],
        "total_record": 1229,
        "total_page": 615,
        "current_page": 2,
        "limit": 2
    }
}
```

