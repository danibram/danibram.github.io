+++
date = "2015-03-17T20:35:49+01:00"
description = "A little helper for dustjs to load your i18n translations in a dynamic way."
project_url = ""
title = "translator helper dustjs"
version = "v1.0.1"

+++

A little helper for dustjs to load i18n translations dynamically, with variables, based on https://github.com/mikesparr/Kraken_Example_i18n_Helper. Feel free to comment, copy or burn this code =P

## Getting Started
Install the module with: `npm install translator-helper-dustjs`

Its important to add a global variable to pass the kraken config to the module, i put in my index.js this after load kraken config
```javascript
...
app = module.exports = express();
app.use(kraken(options));
GLOBAL._app = app;
...
```
On your controllers file or wethever you load dust, add the helper like another.

```javascript
...
var dust = require('dustjs-linkedin');
require('dustjs-helpers');
require('translator-helper-dustjs');
...
```


## Examples
On your properties files (index.properties)
```javascript
...
jobs.acme.title=Company Acme
jobs.hernes.title=Company Hernes
...
```

On your dust template files, pass to the t helper the key (jobs.acme.title -> companyName = "acme"), the properties file (index in this case), and the lang (in my case "EN_us")
```javascript
...
{@t key="jobs.{companyName}.title" bundle="index" lang="{lang}" /}
...
```
And the result will be
```javascript
...
Company Acme
...
```

## Contributing
Please fell free to contribute, i´m not a real expert of dustJs

## Release History
_(Nothing yet)_

## License
Copyright (c) 2014 Daniel Biedma Ramos
Licensed under the MIT license.