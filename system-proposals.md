# System proposals

## LMVC-Patat ([on GitHub](https://github.com/scandio/lmvc-patat))

LMVC Patat is a small web based application build using parts HTML5, CSS3 and JavaScript development stack.
It tries to ease the way of finding a fast-food restaurant near by (25km radius) by listing advertised dishes (three per restaurant). For this purpose it uses geo-location to find the potential customer's longitude and latitude and then performs minor calculations to find restaurants nearby.
Moreover, every restaurant has its own "domain-page" which lists normal and advertised dishes plus location and a map showing to route to the restaurant itself. For restaurants being able to administrate their menu it offers a secured administration backend to edit data and upload images.

From a technical point to view, LMVC Patat is build using the micro [LMVC-Framework](https://github.com/scandio/lmvc) and its [module system](https://github.com/scandio/lmvc-modules), especially the [asset pipeline](https://github.com/scandio/lmvc-modules/tree/master/lib/Scandio/lmvc/modules/assetpipeline) which are all written in PHP 5.4.

**Cons in picking this**

Pitfalls are that [cloc](http://cloc.sourceforge.net/) told me that the project over all has *24720 sloc- of which probably *20k- is library source code. Anyhow, taking the underlying module-system, ORM-layer and the library itself gives us a decent amount to work with.

**Pros in picking this**

The group has one member knowing the libraries involved and the whole language stack. I would not mind teaching and giving short introductions on how stuff is wired. Moreover, the product and the libraries have areas in which they can evolve - this system has potential.

**Addition and changes to the system might inlcude**

- [ ] [posponed] Migrating the database to [Postgres](http://www.postgresql.org/) or [MongoDB](http://www.mongodb.org/) for easier geo-spartial queries
   - This might include extending the ORM-Layer ([Troba](https://github.com/scandio/troba))
- [x] GUI enhancements and migration to [Twitter Bootstrap 3](http://getbootstrap.com/)
- Rewrite and extensions to underlying frameworks
   - [x] Find a better solution for snippet support (resuable UI-components for LMVC's views)
   - [ ] [posponed] Optimising the [asset pipeline](https://github.com/scandio/lmvc-modules/tree/master/lib/Scandio/lmvc/modules/assetpipeline)
- [x] Rewrite view handling in [LVMC](https://github.com/scandio/lmvc)
   - [x] Allow nested views, not just master-to-subtemplate
   - [x] Extract and decouple views from controllers and make it an
   - [x] Allow for dynamic binding of other template engines like twig, handlebars, Smarty
own component with hierarchies and lazy re-rendering
- [ ] [posponed] Transforming it into a [single page web application](https://en.wikipedia.org/wiki/Single-page_application)
- [x] Build a dynamic REST controller to use in [Backbone](http://backbonejs.org/#Sync) e.g. /sync/<ModelClass> which runs basic CRUD on an existing model-class without programming
   - [x] Including a clean validation using LMVC forms module - which should therefore also be renamed to validation module
- [ ] (ponponed) Test modules and components (TDD, BDD frameworks and integrate it with a CI service such as [TravisCI](https://travis-ci.org/))
- [x] I18n component/module for views and application in general
   - [x] Make language a url paramter suffix/prefix (...com/en/controller/…params)
- [x] E-Mail module for e.g. verfication during signup process
- [x] Limit restaurants to only be able to have three offerings
- [x] Logging module allowing multiple level logging and maybe DevTools integration
   - [x] There is a [PSR-3 standard](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-3-logger-interface.md) describing a possible implementation
   - [x] Logging to DevTools could be a level/flag and integrate with e.g. [ChromeLogger](http://craig.is/writing/chrome-logger)
- <del>Fix AssetPipeline to have original file-handle at process-time, not cache file-handle</del>
- [ ] [posponed] Add some data-scraping from existing sites in a configurable manner
- [ ] (needs thought) Add lmvc support for named url parameters e.g /users/id:3 vs. /users/id/3
- [ ] [posponed] Add scaffolding from Shell for mvc-skeletons
- [ ] [undiscussed] Add local storage integration for lmvc-troba
   - Optimistic UI, transmission via ajax and local storage sync in background

## Diaspora [on GitHub](https://github.com/diaspora/diaspora)

[Diaspora](https://joindiaspora.com/) is a a privacy aware, distributed, open source social network. Single installations of the software are in the form of [nodes](http://podupti.me/) (termed "pods") which make up the distributed Diaspora social network. The thrilling part here is that it is not centralised but completely de-centralised and everybody can host his own node.
For more information I suggest reading the article on [wikipedia](http://en.wikipedia.org/wiki/Diaspora_(software). It may seems awfully confusing at first but the idea is almost too novel.

Looking at it from a technical perspective means having a complete web application where all server-side code is written in Ruby and the front-end parts are written in [JavaScript](https://github.com/diaspora/diaspora/tree/develop/app/assets/javascripts) without supporting frameworks.

**Cons in picking this**

Challenging from a technical standpoint. No group member knows Ruby and the learning curve might be flat. Features requested are mostly boundled components such as chat-functionality which might be hard to divide into minor parts.

**Pros in picking this**

The novelty of the system and its potential learning outcome. If the group is willing to learn Ruby as a language which also means putting in some extra effort this system could yield a high learning outcome from a technical perspective.

**Possible additions and changes**

A list of possible features can be found on their [project site](https://wiki.diasporafoundation.org/Known_Issues_and_Feature_Requests).

## Huboard [on GitHub](https://github.com/rauhryan/huboard)

Huboard is an instant project management tool which integrates with GitHub. The integration includes loading all issues from a project's issue tracker (e.g. [Huboard's](https://github.com/rauhryan/huboard/issues)). These will then be listed in Huboard and are manageable on its lightweight Kanban board. The Kanban board moreover allows for assigning people and managing tags and milestones. Its main feature nevertheless is dragging and dropping issues across the board while assigning people to them. Lastly, it is possible to manage issues and their milestones visually while prioritising milestones.

The interessing part here is that we could integrate learnings from the agile course into the project. The project overall seems to have a solid foundation and gained some tracktion when it came out but lacked contribution ever since.

After all, it's all written in Ruby with the usual additions of JavaScript and CSS on the client-side.

**Cons in picking this**

Personally only from a language perspective if everybody has no problem in learning another language an putting in extra hours this system can be a lot of fun.

**Pros in picking this**

We can incorporate learning from the Agile Development course and might have an lower entry cost thereby. The product itself seems to have a solid base but not a whole lot of features. It has a good balence between being good enough and offering opportunities. Especially as we can use the product during its own development (integration with GitHub) - how cool's that!

**Possible additions and changes**

The author references the open [issue tracker](https://github.com/rauhryan/huboard/issues) and encourages fixing general bugs. Moreover, there is a `please-contribute`-tag ([link](https://github.com/rauhryan/huboard/issues?labels=Please+contribute&page=1&state=open)) which lists possible features and migrations. Lastly, we can always add own features.

## TravelGuide ([on GitHub](https://github.com/bhagya85/TravelGuide))

TravelGuide is an Android application designed to serve the purpose of providing tourist attractions, hotels, restaurants at a chosen location.
Users enter their choice of location and radius within to display tourist attractions. The application uses Google Places API to gather the tourist attractions at the given place. The Google Places API request returns an XML file, which is parsed to fetch the required fields. The fields displayed in the App are "Name of the Attraction", "Address of the attraction" and "the rating of the attraction". The App displays approximately around "20" attractions for a given location.

**Points that speak for this system proposal**

- we could further improve our skills in Android app development,
- benefit from Tobi's domain knowledge and use reference apps as help to come up with requirements
- and get to know the Google Places API.

**Possible additions and changes**

Few improvements have already been suggested by the inital developers:
- A favourties page, where users would be able to save their favourite attractions.
- A field that would return the distance from the current location to the tourist attraction, and also the phone number of the attraction.
- An option to show directions to the chosen attraction from the current location.

But I am sure that we could come up with far more requirements considering that we have Tobi as domain expert and a bunch of reference apps.

## ScrumIt ([on GitHub](https://github.com/ti-dev/Scrum-it))

ScrumIt is a digitial Scrum board that supports Scrum teams in managing projects, team members, sprints, userstories, tasks and the burn down chart.
It is said to use modern and multi-touch (whatever that means) technologies such as HTML5 / CSS3, jQuery and jQuery Mobile and the backend system with Java EE, Tomcat, MySQL, Hibernate, Envers. I (Dani) have only experience with Java EE and Hibernate.

**Points that speak for this system proposal**

- we could benefit from the knowledge we have been building since the Agile Software Development course
- use the system for our own organziation or the organization of further projects
- and get to know a lot of technologies at once

**Possible additions and changes**

This is the bad news. There are no open issues on GitHub. That means that we have to use our brains to come up with plenty requirements.

## BlueJ ([on GitHub](https://github.com/neomatrix369/BlueJ))

BlueJ is a simplified IDE for Java programming and developed mainly for teaching purposes. It has bit different design from the regular development
environments - the main screen shows graphically the class structure similarly to an UML diagram.

**Pros**

- since it is a development environment we should all be familiar with the domain + it's java
- it is developed for educational purpose so it might be bit more intuitive and easier to work with

**Cons**

- the domain itself might not be that much interesting

**Possible additions and changes**
It is said to have a good and flexible extension system - we would only need ideas for plug-ins.
