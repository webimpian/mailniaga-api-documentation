# Message

***

<mark style="color:green;">`POST`</mark> `/api/v0/messages`



Submission of email through API.



***

<table data-full-width="true"><thead><tr><th>Name</th><th>Description</th><th>Condition</th></tr></thead><tbody><tr><td><code>from</code></td><td>Email address for <code>From</code> header. If not present, default will be used.</td><td>Optional</td></tr><tr><td><code>to</code></td><td>Recipient email address. Use commas to separate multiple recipients.</td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>reply_to</code></td><td>Email address for recipient reply. Also used for return path for bounced email. </td><td>Optional</td></tr><tr><td><code>unsubscribe_link</code></td><td>Unsubscribe link is a link within your email campaign, often placed in the footer.</td><td>Optional (Recommended)</td></tr><tr><td><code>subject</code></td><td>Email subject.</td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>as_html</code></td><td>By default we use plain text as email content. However you may set <code>as_html=1</code> for sending HTML content.</td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>content</code></td><td>Plain text or HTML content.</td><td><mark style="color:red;">Required</mark></td></tr><tr><td><code>headers</code></td><td>Additional mail header.</td><td>Optional</td></tr></tbody></table>

***



Example of JSON body to be prepared during email submission via API.



```json
{
    "from": "Demo <demo@webimpian.com>",
    
    // Use comma for multiple recipient, limit up to 1,000 in single request
    "to": [
        "Name 1 <demo@purpose-1.io>",
        "Name 2 <demo@purpose-2.io>"
    ], 
    "reply_to": "support@customer.dot",
    "unsubscribe_link": "https://newsletter.mailniaga.com/unsubscribe/UClRDVU763NX75ohJhys7PIg",
    "subject": "Your Campaign Subject",
    "as_html": 1,
    "content": "<p>This is demo HTML.</p>"
}
```



Sending via command line using cURL.



```markup
curl -X POST https://api.mailniaga.mx/api/v0/messages \
-H "Content-Type: application/json" \
-H "X-API-Key: <API_Key>" \
-D '{
    "from": "Demo <demo@webimpian.com>",
    
    // Use comma for multiple recipient, limit up to 1,000 in single request
    "to": [
        "Name 1 <demo@purpose-1.io>",
        "Name 2 <demo@purpose-2.io>"
    ], 
    "reply_to": "support@customer.dot",
    "unsubscribe_link": "https://newsletter.mailniaga.com/unsubscribe/UClRDVU763NX75ohJhys7PIg",
    "subject": "Your Campaign Subject",
    "as_html": 1,
    "content": "<p>This is demo HTML.</p>"
}'
```



JSON structured response.



```json
{
    "error": false, 
    "status_code": 200,
    "message": "OK",
    "data":{
        "total_recipient": 2
    }
}
```

