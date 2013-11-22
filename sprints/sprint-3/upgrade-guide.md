# Sprint 3 Upgrade Guide

## Database

- Import followings dumps
  - `https://github.com/SEP007/lmvc-patat/blob/master/docs/english-dishes.sql`
  - `https://github.com/SEP007/lmvc-patat/blob/master/docs/english-locations.sql`
  - `https://github.com/SEP007/lmvc-patat/blob/master/docs/english-users.sql`

- Internationalization (i18n)
  - Copy the modules and I18n section from sample-config.js to your config.js
  - Execute `php composer.phar update`
