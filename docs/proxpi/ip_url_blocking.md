---
id: blocking
title: IP/URL Blocking
---

<img src="https://raw.githubusercontent.com/fredysomy/HealthApp/master/img/23.54.43.23__1_-removebg.png"></img>

- ProxPi makes it easier to block IP adresses and URL's from accessing your Public API. When a unauthorized req froma blocked IP/URL is made it will be logged in the Error log tab in dashboard.

- If you have provided the sites and IP adress to block in the dashboard they will not be allowed to complete the req

```javascript
if (
  !(
    x.blocked_site.includes(req.headers.origin) || x.blocked_ip.includes(req.ip)
  )
) {
  makerequest();
} else {
  reject();
}
```

- see the whole function in action here [proxpi/backend/routes/api.js](https://github.com/proxpi/proxpi/blob/184bc04d7d02c1c3f4cc284f0506a37d7b6e49be/backend/routes/api.js#L29)
