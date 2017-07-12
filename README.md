# micro-auth0

Helper to get user using Auth0

## Installation

```bash
npm install --save micro-auth0
```

## Usage

```js
const { send } = require('micro');
const auth0 = require('micro-auth0')({
  domain: process.env.AUTH0_DOMAIN
});

module.exports = async (req,res) => {
  const user = await auth0(req);
  if(!user) return send(res,403,{ error: "Forbidden" });
  return {
      date: new Date(),
      user: user
    };
};
```
# micro-auth0