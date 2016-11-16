FORMAT: 1A
HOST: http://api.gpsinsight.com/v3/

# GPS Insight V3

Third installment of the GPSI API.

## Group Driver

## Messages [/driver/messages]

### Get All Messages [GET]

+ Request

    + Headers
    
            Session: <Valid session token>
            Since: 2015-08-05T08:40:51
            Until: 2015-08-05T08:40:52

+ Response 200 (application/json)

    ```js
        [
            {
                "id": "870h8dfhs9d8fg",
                "timestamp": "2015-08-05T08:40:51",
                "from": "John Somebody",
                "message": "Some message that is really important."
            }
        ]
    ```

## Message [/driver/message]

### Send Message [POST]

+ Request (application/json)

    + Headers
    
            Session: <Valid session token>
    
    + Body
    
    ```js
            [
                {
                    "to": "user",
                    "from": "Sum Yung Gai",
                    "from_type": "driver",
                    "device_type": "mobile",
                    "message": "A message"
                }
            ]
     ```

+ Response 200

## Dispatch [/driver/dispatch]

### Get All Dispatches [GET]

+ Request

    + Headers
    
            Session: <Valid session token>
            Since: 2015-08-05T08:40:51

+ Response 200 (application/json)

    ```json
        [
            {
                "id": "<Dispatch ID>",
                "latitude": 121.191,
                "longitude": -100.231,
                "address": "3210 N Butte St. Bremerton, WA 96753",
                "note": "A really important note. Their dog will murder you.",
                "timestamp": "2015-08-05T08:40:51"
            }
        ]
    ```

## Dispatch Receipt [/driver/dispatch/receipt]

### Send Dispatch Receipt [POST]

+ Request

    + Headers
    
            Session: <Valid session token>
            
    + Body
    
        ```json
            "DispatchID"
        ```

+ Response 200