xoauth2
=======

XOAuth2 token generation with node.js

## Installation

    npm install xoauth2

## Usage

xoauth2 generates XOAUTH2 login tokens from provided Client and User credentials

User xoauth2.createXOAuth2Generator(options) to initialize Token Generator

Possible options values:

  * **user** User e-mail address
  * **accessUrl** Optional Endpoint for token genration (defaults to *https://accounts.google.com/o/oauth2/token*)
  * **clientId** Client ID value
  * **clientSecret** Client secret value
  * **refreshToken** Refresh token for an user

See https://developers.google.com/accounts/docs/OAuth2WebServer#offline for generating the required credentials

### Example

    var xoauth2 = require("xoauth2"),
        xoauth2gen;

    xoauth2gen = xoauth2.createXOAuth2Generator({
        user: "user@gmail.com",
        clientId: "{Client ID}",
        clientId: "{Client Secret}",
        refreshToken: "{User Refresh Token}"
    });

    xoauth2gen.getToken(function(err, token){
        if(err){
            return console.log(err);
        }
        console.log("Base64 encoded XOAUTH2 auth string: " + token);
    });

## License

**MIT**