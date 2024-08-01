# Account

***

<mark style="color:blue;">`GET`</mark> `/api/v0/user`



Get basic information for authenticate user via API key.



```markup
curl -X GET https://api.mailniaga.mx/api/v0/user \
-H "Content-Type: application/json" \
-H "X-API-Key: <API_Key>"
```



JSON structured response.



```json
{
    "error": false,
    "status_code": 200,
    "data": {
            "organisation": "Mail Niaga MX",
            "email": "demo@mailniaga.mx",
            "suspended": false,
            "smtp_username": "2fa2ef89f8b305d581976",
            "limit_quota": "2358490",
            "total_usage": 813,
            "credit_balance": 2357677
    },
    "message": "OK"
}
```

