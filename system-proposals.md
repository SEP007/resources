# System proposals

## LMVC-Patat ([on GitHub](https://github.com/scandio/lmvc-patat))

LMVC Patat is a small web based application build using parts HTML5, CSS3 and JavaScript development stack.
It tries to ease the way of finding a fast-food restaurant near by (25km radius) by listing advertised dishes (three per restaurant). For this purpose it uses geo-location to find the potential customer's longitude and latitude and then performs minor calculations to find restaurants nearby.
Moreover, every restaurant has its own "domain-page" which lists normal and advertised dishes plus location and a map showing to route to the restaurant itself. For restaurants being able to administrate their menu it offers a secured administration backend to edit data and upload images.

From a technical point to view, LMVC Patat is build using the micro [LMVC-Framework](https://github.com/scandio/lmvc) and its [module system](https://github.com/scandio/lmvc-modules), especially the [asset pipeline](https://github.com/scandio/lmvc-modules/tree/master/lib/Scandio/lmvc/modules/assetpipeline) which are all written in PHP 5.4.

Pitfalls are that [cloc](http://cloc.sourceforge.net/) told me that the project over all has *24720 sloc* of which probably *20k* is library source code.

**Addition and changes to the system might inlcude:**

* Migrating the database to [Postgres](http://www.postgresql.org/) or [MongoDB](http://www.mongodb.org/) for easier geo-spartial queries
   * This might include extending the ORM-Layer ([Troba](https://github.com/scandio/troba))
* GUI enhancements and migration to [Twitter Bootstrap 3](http://getbootstrap.com/)
* Rewrite and extensions to underlying frameworks
   * View handling in [LVMC](https://github.com/scandio/lmvc) - allowing nested views
   * Find a better solution for snippet support (resuable UI-components for LMVC's views)
   * Optimising the [asset pipeline](https://github.com/scandio/lmvc-modules/tree/master/lib/Scandio/lmvc/modules/assetpipeline)
* Transforming it into a [single page web application](https://en.wikipedia.org/wiki/Single-page_application)
   * Extending LMVC to integrate easier with [Backbone](http://backbonejs.org/) or any other framework

## Diaspora [on GitHub](https://github.com/diaspora/diaspora)

[Diaspora](https://joindiaspora.com/) is a a privacy aware, distributed, open source social network. Single installations of the software are in the form of [nodes](http://podupti.me/) (termed "pods") which make up the distributed Diaspora social network. The thrilling part here is that it is not centralised but completely de-centralised and everybody can host his own node.
For more information I suggest reading the article on [wikipedia](http://en.wikipedia.org/wiki/Diaspora_(software). It may seems awkfully confusing at first but the idea is almost too novel.

Looking at it from a technical perspective means having a complete web application where all server-side code is written in Ruby and the front-end parts are written in [JavaScript](https://github.com/diaspora/diaspora/tree/develop/app/assets/javascripts) without supporting frameworks.

A list of possible features can be found on their [project site](https://wiki.diasporafoundation.org/Known_Issues_and_Feature_Requests).

