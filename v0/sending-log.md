# Sending Log

***

<mark style="color:blue;">`GET`</mark> `/api/v0/logs`



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

<table data-full-width="true"><thead><tr><th>Parameter</th><th>Description</th><th>Condition</th></tr></thead><tbody><tr><td><code>limit</code></td><td>Limit record to fetch for each page. By default API will use 100 if not set.</td><td>Optional</td></tr><tr><td><code>page</code></td><td>Record page. This parameter is optional to navigate and jump between page within pagination.</td><td>Optional</td></tr></tbody></table>

***



JSON structure response.



```json
{
    "error": false,
    "status_code": 200,
    "data": {
        "data": [
            {
                "created_at": "2023-07-19T00:04:14.362Z",
                "enveloper_id": "1896b7565ae00006b2",
                "interface": "api",
                "domain": "mailniaga.com",
                "from": "hai@mailniaga.com",
                "to": "demo_user@mailniaga.com",
                "delivered": 1,
                "status": "{\"delivered\":true,\"ip\":\"139.99.84.121\",\"mx\":\"aspmx.l.google.com\",\"response\":\"250 2.0.0 OK 1719976296 d9443c01a7336-1fb0e952da5si13548855ad.414 - gsmtp\"}"
            }
        ],
        "total_records": 862912,
        "total_pages": 862912,
        "current_page": 2,
        "limit": 2
    },
    "message": "OK"
}
```

