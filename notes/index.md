## JWT Do and Don'ts

* **DON'T** store tokens in localStorage for convenience
    * It's safer to move them to either an http only cookie or keep 
      them in React state aka browser memory
    * localStorage is scriptable/readable
* **DON'T** keep secret keys that go into signing tokens in the browser
* **DON'T** decode the token in the client (opinion); tokens are meant for apis

* **DO** keep long, strong, unguessable secrets
* **DO** keep token payload small


## Concept of 'public fetch'
Instead of using the same fetch api for both auth & non-auth requests
define and share a `publicFetch`. (example using axios)

```javascript
import axios from 'axios';

const publicFetch = axios.create({
  baseURL: process.env.REACT_APP_API_URL
});

export { publicFetch };
```
