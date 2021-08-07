---
id: headers
title: Headers
---

* All the headers of your API given is Encrypted with a Secret key and is only decrypted in the Backend for API request and to be shown in frontend

* The crypt function can be found here [proxpi/backend/core/crypt.js](https://github.com/proxpi/proxpi/blob/master/backend/core/crypt.js)

```javascript
encrypt() //function encrypts the data
decrypt() //function decrypts the encrypted data

```