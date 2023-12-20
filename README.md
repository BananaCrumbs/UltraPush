# UltraPush
UltraPush Documentation

## Base URL
The base URL is currently:
`https://ultrapush.bananacrumbs.us`

In the future, this may change to ultrapush.app.  The old URL will still work; however, please be aware of this potential change.

## API Endpoints

Note that there are currently no rate limits; however, rate limits will be imposed in the future, and there will be
a limit of messages per day which can be sent to a specific user.

Please subscribe to the repository to be notified of changes when this happens.

### POST /push

Headers:
```
Authorization: Bearer <token>
```

Where `<token>` is the token on the UltraPush app.

POST data:
```json
{
    "title": "(REQUIRED) title of the notification (usually the name of the app notifying)",
    "body": "(REQUIRED) body of the notification",
    "subtitle": "notification subtitle",
    "sound": "Will be added in a future release",
    "badge": 1,
    "data": {
        "url": "optional url to auto-redirect the user if they have it enabled",
        "html": "body of the notification users will see in-app.  Supports HTML and secure-only connections to images."
    }
}
```

You will receive 200 OK on success, or 404 Not Found if the token is not valid.
