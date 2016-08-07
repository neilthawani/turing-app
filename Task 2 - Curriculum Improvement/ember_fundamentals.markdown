---
title: Ember Fundamentals
length: 120
tags: javascript, ember
---

## Why Ember?

* What Ember actually is and does
* Its history and lineage

### What is Ember?

* An open-source JS web framework
* Create SPAs with a common language
* Like Ruby, it's clean code and separation of concerns with a highly opinionated structure - Convention over Configuration, DRY

### History
* 2007: Development began on Sproutcore 1.0, a widget library created by Yehuda Katz
* May 2011: Sproutcore 2.0 emerged as an application library for the new web
* December 2011 - Sproutcore 2.0 becomes Ember to reduce confusion between the Sproutcore 1.0 widget library and Ember

### Current Ecosystem
* Founders: Yehuda Katz and Tom Dale (Tomhuda Katzdale)
* Ember App Kit to Ember CLI
* Stability without stagnation - an LTS release twice a year.
* This is the idea that backward compatibility is important and can be maintained while still innovating and evolving the framework.
* Promises, web components, ES6 support with Babel
* Future web standards in mind
* Katz is a member on TC39, which is the committee responsible for future versions of the Javascript language.

### Who uses Ember?

| Twitch | Urbanspoon | Infegy | TED
| Zenefits | Netflix | Heroku | Microsoft
| LinkedIn | Esri | Kickstarter | [More...](http://emberjs.com/ember-users/) |

## Learning Goals

* Understand how Ember's object model works
* Create two-way data bindings
* Implement computed properties on the controller level
* Invoke components and send actions back to the controller
* What we'll do: Create a bare Ember application, using the build pipeline but without any of the addons that the ecosystem has (stubbing fixtures for tests ember-cli-mirage, Bootstrap, external projects like shared code between repos)

## Warm Up

Make sure you have all of the following installed:

* [Node.js](http://nodejs.org)
* [ember-cli](http://www.ember-cli.com/) (You may need to use `sudo` depending on how your environment is configured.)
* The [Ember Inspector](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)

Also: Clone a copy of [this repository][greattipper]. We'll be using it during the Code-Along and Pair Practice segments of the lesson.

## Lecture

We'll cover the following topics:

* The technology that makes up Ember (Handlebars, Ember Runtime, Ember Metal, RSVP)
* The tooling around Ember (the Ember Inspector, ember-cli, Ember Data)
* The Ember object model
  * Classes and instances
  * Initializing an object (and calling `this._super()`)
  * Computed properties
  * Observers
  * Working with arrays
  * Bindings
  * Template helpers
  * Components and actions

## Workshop

### Code Along

We're going to implement the basic functionality of [Great Tipper][greattipper]. Follow along!

### Pair Practice

Can you add any of the following to your application?

* A function that observes the tip price and displays a message when someone is being a cheapskate?
* Presets calculations for 15%, 18%, and 20%. When the user clicks a button, the tip percentage is automatically set to that amount.
* Automatic calculations for 15%, 18%, and 20%. When the user enters an amount for the cost of the meal, they should automatically see these three values.
* **Challenge**: The user wants to be able to dial in an amount and a tip and save it to an array and see all of their recent meals in a table (bonus points if you store the data using `localStorage`).

## Wrap Up

What are some of the similarities between Ember's object models and Ruby's? Is there anything you like better? Is there anything you wish Ember stole from Ruby (and/or Rails)?

===

https://www.youtube.com/watch?v=53OpEYA4zPQ
List concepts before covering everything.
Cover it in the means of MVC or routable components flow.
Data down, actions up.

Node.js installed
npm install ember-cli -g
Create new Ember CLI project.
Can do ember s
Files and folders structure overview, then go to index.html and application.hbs
Walk through file, do #each loop, note that index can be put into block
How component interacts, talk about generators but do pods structure for routable components and talk about how your folder structure is easier than MVC and accommodates better for the concept of routable components
Form helpers - input tag and decorating bindings
Button with action for form
Add object to array using .get(object) and array.pushObject(obj)
Can we do ember g component bear-list (for #each from before) or should we indicate something about pods again?
Note that the array of data won't come from app - it'll come from AJAX
Go into route - go to model() and issue an AJAX request - model() returns to the controller.js object "model," but we'd rather do this.controller.set('var', data);
Stub a JSON file in public/ and that's fine like that
Pass param into bears-list component from Ajax reply
Create a new action and do "sendAction" from the component
Maybe have a save action in the router.
Data down, actions up.

===

https://guides.emberjs.com/v2.5.0/object-model/
* Classes and instances
  * Initializing an object (and calling `this._super()`)
  * Computed properties
  * Observers
  * Working with arrays
  * Bindings
  * Template helpers
  * Components and actions

Outside Resources
Ember Screencasts
Ember Global Meetup
Ember Sherpa

===

Basic concepts:
Routes - application state is stored in the URL
Models - routes have models, containing the data for the app. Ember Data is a common library used for handling serialization of JSON objects
Templates - build the app's HTML using HTMLBars (Handlebars syntax and web component rendering)
Components - custom HTML tags with bound attributes/class names/properties - send data down into components, actions up to the controller/router from components
Services - singleton objects to hold things like user session data

Dependency injection, two-way data binding, computed properties, automagically updating templates.

Culminate in the Ember Object Model

https://en.wikipedia.org/wiki/Ember.js#Ember_2.0

Lifecycle hooks for components
Rendering engine: Glimmer (external link to Ember Conf) - creates a virtual tree of rendered areas and diffs them like React

https://en.wikipedia.org/wiki/Ember.js#Ember_Software_Stack

Convention over configuration to build tools:
Broccoli, folder structure, ES6 modules, ES6 support with Babel, testing framework (QUnit is default), npm/bower dependencies, asset management in ember-cli-build.js.

Ember Data

Like an ORM with a RESTful JSON API so it can interface with a multitude of languages (PHP, Node.js, Python, Go, .NET, Java)

Ember Inspector

Extension available for Firefox and Chrome
See which templates are being rendered, properties of an Ember Object with UI that computes bindings/computed properties
See the records for each model if you're using Ember Data

Ask: What other things do we use to debug our applications? console functions and breakpoints.

Release cycle

Approximately every six weeks - Ember RFCs are submitted to Github and reviewed by the community. Next version release and beta for the one after that are released.

Semver
Breaking changes introduced at major version numbers
New features, deprecations added at point releases
Tooling to streamline this process is under development

Relevant Resources:
Core team meeting minutes
EmberJS subreddit
Major changes for Ember go through the RFC process
http://emberweekly.com/

Liquid fire? ***

## Resources

* [Great Tipper][greattipper]

[greattipper]: https://github.com/neilthawani/great-tipper