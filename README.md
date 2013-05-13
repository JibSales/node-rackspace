<<<<<<< HEAD
#Rackspace API for Node.js
##Developer's Note
This library is not officialy supported by Rackspace. Though I use it in production, its advised that you do so at your own risk. Please see the included LICENCE file for license details.

Please create an issue for any bugs you may experience and I will gladly accept pull requests if they fit the goals of the project. 

##Design
`node-rackspace` aims to be a wrapper library for the following Rackspace Cloud APIs:
  
  * [Cloud Files (including CDN management)](http://docs.rackspace.com/files/api/v1/cf-devguide/content/Overview-d1e70.html)
  * [Cloud DNS](http://docs.rackspace.com/cdns/api/v1.0/cdns-devguide/content/overview.html)

Though `node-rackspace` is framework agnostic, it exposes Connect compatible middleware for easy authentication with the Rackspace identity server.

Most interactions with the Rackspace API will require chaining requests together and thus will lead to complex and unreadable "callback nesting", a concept that should not be foreign to the experienced Nodejs hacker. `node-rackspace` is designed to use a method chaining API to clean up requests and eliminate nested callbacks. Rest assure, all requests and operations are performed asyncronously despite the APIs appearance.

##Getting Started
### Installation
To install `node-rackspace` for use in your project, use npm:

```
~$ npm install node-rackspace
```
### Example as Express middleware

```
var rackspace = require('node-rackspace'),
    express   = require('express'),
    app       = module.exports = express();

// Options hash to load Rackspace credentials
var options = {
  username: "captain",
  apikey: "XXXXXXXXXXXXXXXXXXX"
}

app.use(rackspace.init(options));
app.use(app.router);

-- or --

app.get('/some/route', rackspace.init(options), function (req, res, next) {
  rackspace
    .createContainer('MyContainer')
    .exec(…)
});

```

When used as middleware, `node-rackspace` automatically tracks and renews your API token.

###Use as stand alone wrapper
```
var rackspace = require('node-rackspace');

// Options hash to load Rackspace credentials
var options = {
  username: "captain",
  apikey: "XXXXXXXXXXXXXXXXXXX"
}

rackspace.auth(options, function (err) {
  rackspace
    .createContainer('MyContainer')
    .exec(…);
});
```

##API
###Cloud Files
######Containers

=======
node-rackspace
==============

A nodejs client library for the Rackspace Cloud APIs
>>>>>>> 1f1aba21f52a61735b0cdf56a15aaf8ba48e5435
