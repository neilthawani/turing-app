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
* What we'll do: Create a bare Ember application, using the build pipeline but without any of the addons that the ecosystem has (stubbing fixtures for tests ember-cli-mirage, Bootstrap, Liquid Fire for animations, external projects like shared code between repos)

## Prepare & Warm Up

### Make sure you have all of the following installed:
* [Node.js](http://nodejs.org)
* [ember-cli](http://www.ember-cli.com/) (You may need to use `sudo` depending on how your environment is configured.)
* The [Ember Inspector](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)

Also: Clone a copy of [this repository][greattipper]. We'll be using it during the Code-Along and Pair Practice segments of the lesson.

## Lecture

* The technology that makes up Ember (Handlebars, Ember Runtime, Ember Metal, RSVP)
* The tooling around Ember (the Ember Inspector, ember-cli, Ember Data)
* Convention over configuration to build tools:
Broccoli, folder structure, ES6 modules, ES6 support with Babel, testing framework (QUnit is default), npm/bower dependencies, asset management in ember-cli-build.js.
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

```shell
> npm install ember-cli -g
> ember new project-name
> ember s
```

Some Ember CLI conventions will remind you of Ruby on Rails.
Let's open the IDE and go over the structure of the application.

* Everything we will write is in ```app```.
* ```bower_components``` and ```node_modules``` contain our bower/npm packages.
* ```config``` contains environment.js, for dev/test/prod setup and some addon management.
* ```dist``` and ```tmp``` contain minified files.
* You can put assets in ```public``` and ```vendor``` and tests in ```tests```.

We're going to learn how to do the following things in our new application:
* Create an application folder in app/ with route, controller, template.
* We can invoke components and decorate them with custom HTML/attributes using HTMLBars.
* Create an array in the controller and run through it in an ```#each``` loop in the template.
* Create a component with ```file-name-hyphenated``` using generators. Touch upon pods, routable components, and data down, actions up.
* Create a form with a decorated input tag helper in the template. Create a button with an ```{{action}}```.
* In the ```action```, add an object to the array using ```.get(object)``` and ```array.pushObject(object)```.
* Data will usually come from an AJAX call. ```model()``` in the ```route.js``` file returns a ```model``` object to its controller. I would rather do ```this.controller.set('variable', data)``` for explicitness.
* We can stub a JSON file in ```public/``` and issue an AJAX call. Set the variable in the controller, pass it into a component. We can send an action from the component to the controller using ```sendAction```.

### Pair Practice

Can you add any of the following to your application?

* A function that observes the tip price and displays a message when someone is being a cheapskate?
* Presets calculations for 15%, 18%, and 20%. When the user clicks a button, the tip percentage is automatically set to that amount.
* Automatic calculations for 15%, 18%, and 20%. When the user enters an amount for the cost of the meal, they should automatically see these three values.
* **Challenge**: The user wants to be able to dial in an amount and a tip and save it to an array and see all of their recent meals in a table (bonus points if you store the data using `localStorage`).

## Wrap Up

What are some of the similarities between Ember's object models and Ruby's? Is there anything you like better? Is there anything you wish Ember stole from Ruby (and/or Rails)?

===

https://guides.emberjs.com/v2.5.0/object-model/
Objects in Ember
Classes and Instances
Reopening Classes and Instances
Computed Properties
Observers
Bindings
Enumerables

===

Basic Concepts:
Routes - application state is stored in the URL
Models - routes have models, containing the data for the app. Ember Data is a common library used for handling serialization of JSON objects
Templates - build the app's HTML using HTMLBars (Handlebars syntax and web component rendering)
Components - custom HTML tags with bound attributes/class names/properties - send data down into components, actions up to the controller/router from components
Services - singleton objects to hold things like user session data

Dependency injection, two-way data binding, computed properties, automagically updating templates.

Culminate in the Ember Object Model

Lifecycle hooks for components
Rendering engine: Glimmer (external link to Ember Conf) - creates a virtual tree of rendered areas and diffs them like React

#### Ember Data
* Like an ORM with a RESTful JSON API so it can interface with a multitude of languages (PHP, Node.js, Python, Go, .NET, Java)

#### Ember Inspector
* Extension available for Firefox and Chrome
* See which templates are being rendered, properties of an Ember Object with UI that computes bindings/computed properties
* See the records for each model if you're using Ember Data
* Another tool to use in addition to console.logs/breakpoints

### Release cycle
* Ember RFCs are submitted to Github and reviewed by the community.
* Approximately every six weeks, the next Ember version and its beta are released

#### Semantic Versioning
* Breaking changes introduced at major version numbers
* New features, deprecations added at point releases
* Tooling to streamline this process is under development

## Resources

* [Core team meeting minutes](https://github.com/emberjs/core-notes)
* [EmberJS subreddit](https://www.reddit.com/r/emberjs)
* [Ember RFCs](https://github.com/emberjs/rfcs)
* [Major changes for Ember go through the RFC process)
* [Ember Weekly Newsletter](http://emberweekly.com/)
* [Monthly Online Global Ember Meetup](https://www.bigmarker.com/communities/global-ember-meetup/about)
* [Great Tipper][greattipper]

[greattipper]: https://github.com/neilthawani/great-tipper

Ember Screencasts
Ember Global Meetup
Ember Sherpa