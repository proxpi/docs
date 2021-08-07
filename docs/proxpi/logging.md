---
id: logging
title: Request Logging
---

<img src="https://raw.githubusercontent.com/fredysomy/HealthApp/master/img/Untitled_design__1_-removebg.png"></img>

### 1) Request logging

* All the requests excluding the ones which caused errors are logged.(Along with time,date,IP,URL)

```javascript
LogRequests(
      (requests = req),
      (key = req.params.id),
      (resptime = new Date() - date)
    );
```
* The function can be found [proxpi/backend/utils/LogRequests.js](https://github.com/proxpi/proxpi/blob/master/backend/utils/LogRequests.js)

### 2) Error logging

* The requests which causes errors are logged here.
* Error logs are calssified as two
  * Some errors happen while making request (API key invalid etc)
 
    * ```javascript
  await ErrorLogger({
              name: "Request error , A error happened while making request",
              request_url: req.headers.origin,
              ip: req.ip,
              time: moment().format("llll"),
              key: req.params.id,
              errLog: err,
            });
    ```
    * The error logs can be accessed in the logs button
  * Some errors happen when blocked sources access API
 
    * ```javascript
  await ErrorLogger({
          name: "Error , Tried accessing API from Blocked sources ",
          request_url: req.headers.origin,
          ip: req.ip,
          time: moment().format("llll"),
          key: req.params.id,
          errLog: {},
        });
    ```
* * The function can be found [proxpi/backend/utils/ErrorLogger.js /](https://github.com/proxpi/proxpi/blob/master/backend/utils/ErrorLogger.js)      