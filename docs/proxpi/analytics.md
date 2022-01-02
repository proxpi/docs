---
id: analytics
title: Analytics
---


## ProxPi provides two analytics methods

### 1) Daily Analytics

<img src="https://raw.githubusercontent.com/fredysomy/HealthApp/master/img/Untitled_design__1_-removebg.png"></img>

* ProxPi provides you detailed analytics of your API. Daily analytics is visualisable in chart form. 

* Each time the Proxy endpoint is hit a function send the data to server .

```javascript
 RegisterPerDayRequests((key = req.params.id));
```
* The function can be found [proxpi/backend/utils/RegisterPerDayReq.js ](https://github.com/proxpi/proxpi/blob/master/backend/utils/RegisterPerDayReq.js)

### 2) Geo Spatial Analytics

* Geo Spatial Analytics gives the user a vague idea from where there endpoint is called and is visualisable in a map. Analytics feature is free for all users.

* Each time you make a req your IP is passed into a function for location.

```javascript
  RegisterGeoDataReq((key = req.params.id), (ip = req.ip));
```

* The function can be found [proxpi/backend/utils/RegisterGeoDataReq.js ](https://github.com/proxpi/proxpi/blob/master/backend/utils/RegisterGeoDataReq.js)

