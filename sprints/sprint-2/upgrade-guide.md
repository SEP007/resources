# Sprint 2 Upgrade Guide

## Dependencies

- Checkout `master` in lmvc, lmvc-modules and lmvc-utils
- Run `php composer.phar update`

## Database

- Import followings dumps
  - `https://github.com/SEP007/lmvc-patat/blob/master/docs/emailverification.sql`

## Configuration

- Add rendering entry from `sample-config.json` to your `config.json`
- Add emails entry from `sample-config.json` to your `config.json`
- Add ChromeScribe to Logger entry from `sample-config.json` to your `config.json` if you want to use ChromePHP

## Patat update

- Run `git pull origin master` from within `lmvc-patat`-folder