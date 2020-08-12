# Setup
This setup assumes that your machine has `nodejs` (with `npm`) installed. `cd` into the root directory, then run `npm i` to install the dependencies.

# Configuration
In `index.js` you'll need to update the `CLIENT_ID`, `CLIENT_SECRET` and `REDIRECT_URI` to match the application configuration in Atlas. You'll most likely want to point `ngrok`(https://ngrok.com/) at this local server, and use the HTTPS version as your redirect URI.

If using ngrok, you'll want to run `ngrok http 3000`, and set the `REDIRECT_URI` in both the Atlas application config/ in `index.js` to match the HTTPS address generated by ngrok.

```
const CLIENT_ID = "..."
const CLIENT_SECRET = "..."
const REDIRECT_URI = "https://....ngrok.io/callback"
```

# Allowlisting the application
At the moment we're feature flagging access to the new user journey. You need to send us the `CLIENT_ID` of any application that's going to be used with this new journey.

# Running the application

After the dependencies have fininshed installing, run the below block to start.
```
DEBUG=myapp:* npm start
```

To kick off a journey, go to http://localhost:3000/redirect