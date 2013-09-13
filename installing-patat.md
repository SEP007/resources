# Installation Instructions

LMVC Patat is based upon [LMVC](https://github.com/SEP007/lmvc) and more specifically [LMVC Afresh](https://github.com/scandio/lmvc-afresh) as the boilerplate project.

## Download app and dependencies

1. To install your own version just clone the repo into your htdocs
   - `git clone https://github.com/scandio/lmvc-patat.git`
2. Then
   - `cd lmvc-patat && sh bootstrap.sh`
2. This will load all *composer* dependencies and setup caching-directories for the [Asset Pipeline](https://github.com/SEP007/lmvc-modules/tree/master/lib/Scandio/lmvc/modules/assetpipeline).

## Setup the database

1. Setup a new database in your own MySQL and select it
2. Import the security module [database](https://github.com/SEP007/lmvc-modules/blob/master/lib/Scandio/lmvc/modules/security/docs/DatabasePrincipal.sql)
3. Import the patat [database](https://github.com/SEP007/lmvc-patat/blob/master/docs/lmvc-patat.sql)

## Setup the app

1. Copy the contents of the [sample-config.json](https://github.com/SEP007/lmvc-patat/blob/master/sample-config.json) into a file named `config.json` and adjust its values if needed
   - Meaning change database-name and credentials
2. Now copy the contents of the [.-sample-htaccess-file](https://github.com/SEP007/lmvc-patat/blob/master/.sample-htaccess) into a new `.htaccess`
3. Now copy the contents of the [/app/javascripts/sample-config.js](https://github.com/SEP007/lmvc-patat/blob/master/app/javascripts/sample-config.js) into a new *config.js* and set the app's root to whereever the app resides on your own *localhost* too.

Launch the app in the browser e.g. [localhost/lmvc-patat](http://localhost/lmvc-patat).