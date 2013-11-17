# Sprint 1 Upgrade Guide

## Dependencies

- Set all git's `origin` of lmvc lmvc-modules to `https://github.com/SEP007/lmvc.git` and `https://github.com/SEP007/lmvc-modules.git`
- Checkout `master` in lmvc and lmvc-modules
- Run `php composer.phar update`

## Database

- Import followings dumps
  - `https://github.com/SEP007/lmvc-patat/blob/master/docs/groups.sql`
  - `https://github.com/SEP007/lmvc-patat/blob/master/docs/customers.sql`
  - `https://github.com/SEP007/lmvc-patat/blob/master/docs/131031-dish_categories.sql`

## Configuration

- Add logger entry from `sample-config.json` to your `config.json`

## Patat update

- Run `git pull origin master` from within `lmvc-patat`-folder