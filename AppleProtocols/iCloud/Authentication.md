# Authentication

## Getting Authentication Token

iCloud-API: [`getAuthToken`](https://github.com/MauriceConrad/iCloud-API/blob/7edb504f1727066192178c8dd4cdb1d09742333f/setup.js#L13)

POST to `https://idmsa.apple.com/appleauth/auth/signin`

Request Headers:
```js
{
    'Content-Type': 'application/json',
    'Referer': 'https://idmsa.apple.com/appleauth/auth/signin',
    'Accept': 'application/json, text/javascript, */*; q=0.01',
    'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/603.3.1 (KHTML, like Gecko) Version/10.1.2 Safari/603.3.1',
    'Origin': 'https://idmsa.apple.com',
    'X-Apple-Widget-Key': '83545bf919730e51dbfba24e7e8a78d2', // Keep this in a variable
    'X-Requested-With': 'XMLHttpRequest',
    'X-Apple-I-FD-Client-Info': { // JSON object
        {
            "U": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/603.3.1 (KHTML, like Gecko) Version/10.1.2 Safari/603.3.1",
            "L": "en_US", // Keep this in a variable
            "Z": "GMT+02:00",
            "V": "1.1",
            "F": ""
        }
    }
}
```

Request Body (JSON):

```js
{
    "accountName": /* Apple ID */,
    "password": /* Password */,
    "rememberMe": true,
    "trustTokens": []
}
```

Hopefully, you should get headers `x-apple-session-token`, `x-apple-session-id`, and `scnt` and a JSON object with the properties `authType`

## Login

iCloud-API: [`accountLogin`](https://github.com/MauriceConrad/iCloud-API/blob/7edb504f1727066192178c8dd4cdb1d09742333f/setup.js#L79)

POST to `https://setup.icloud.com/setup/ws/1/accountLogin` with URL paramaters (`?` and `&`):

```js
{
    "clientBuildNumber": "2018Project35",
    "clientId": /* A string of 8, then 4, 4, 4, 12 hex characters, separated by hyphens: XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX */,
    "clientMasteringNumber": "2018B29"
}
```

Headers:
```js
{
    'Content-Type': 'text/plain',
    'Referer': 'https://www.icloud.com/',
    'Accept': '*/*',
    'User-Agent': 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/603.3.1 (KHTML, like Gecko) Version/10.1.2 Safari/603.3.1',
    'Origin': 'https://www.icloud.com'
}
```
