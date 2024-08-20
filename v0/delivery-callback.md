# Delivery Callback

***



Optionally you can set delivery callback URL at Dashboard > SMTP > Callback URL. Our server will retry up to 5 times attempt.



JSON structured response.



```json
{
    "id": "19170ec04e5000f93d",
    "domain": "gmail.com",
    "to": "hai@mailniaga.com",
    "address": "210.79.174.88",
    "user" : "tJQnc0u3f5OWQak170IZCpuvq1Eetp",
    "interface": "api",
    "from" : "from-api@mailniaga.com",
    "delivered": true,
    "delivery_response": "250 2.0.0 OK 1724176407 d9443c01a7336-201f03b15fbsi24823855ad.546 - gsmtp",
    "ip": "210.79.174.88",
    "mx": "gmail-smtp-in.l.google.com"
}
```

