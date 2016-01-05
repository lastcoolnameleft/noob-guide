# NodeJS

[NodeJS](https://nodejs.org) is a runtime environment for [Javascript](https://en.wikipedia.org/wiki/JavaScript).  This topic will discuss both NodeJS and JS.  If there's enough content, I will split them out into separate discussions.

## Starting from Scratch

* [Node School](http://nodeschool.io) - All node topics
* [Learn You Node](https://github.com/workshopper/learnyounode) - A good walkthrough of NodeJS
* [Stack Overflow - Getting started with node](http://stackoverflow.com/questions/2353818/how-do-i-get-started-with-node-js)
* [Art of Node](https://github.com/maxogden/art-of-node)
	
## Packaging

The main package manager for NodeJS is [NPM](https://www.npmjs.com/)

## Opinions

### What I like:
* Very easily customizable
* REPL
  * http://derickbailey.com/2014/07/02/build-your-own-app-specific-repl-for-your-nodejs-app/
  * http://docs.nodejitsu.com/articles/REPL/how-to-create-a-custom-repl
  * https://nodejs.org/api/repl.html
* Easy to manipulate Data 
* NPM
  * There's a package for almost anything
* Promises
* ES6 is cleaning a lot up, and ES7 will finish the cleanup


### What I don't like:
* Customizing REPL is basically adding functionality any good REPL should have
  * Like RELOADING, DAMMIT!
* async design can lead to callback hell
	* http://stackabuse.com/avoiding-callback-hell-in-node-js/
* async design renders repl useless in any non-trivial case
	* investigate: https://www.npmjs.com/package/otaat-repl
	* which encourages creating testcase, which could be a good thing for conditioned dev
* Can't fucking reload modules in REPL!!!! (require twice doesn't reload)
	* _ is a reserved REPL word!  WTF!  _.js is huge and long-outlives node
* Unable to define same method with different signatures.  
	* That's F'ing annoying.
	* Workaround:  http://www.bennadel.com/blog/2008-overloading-javascript-functions-using-a-sub-function-approach.htm
* What if you want to conditionally .then a promise?!?!  What then, batman?!  What then?!
* Testing async code involves adding logic to TC.
	* since EVERYTHING is async -> TC's are as likely to be buggy as code
	* Spend 4+ hours debugging random test failures, to determine code was fine, tests were buggy
* Multiple Testing Frameworks
  * Mocha is most basic
  * testacular -> karma, but video still references testacular (lame!)

## Experiences
* REPL is almost useless for trying async.  Everything is async
	* Can't fetch value from async func and explore in repl due to callback
* Can use framework to manage a lot for you, but for what we do, almost better to piece together what you want (conf, http, mysql)
* Many small, focused modules 
* Install modules to package or globally (mainly for execs)
* JSON parsing can be fucking pedantic.  (no trailing , on key/val)
* Tried Mancy "a better REPL"  Separate app that crashes when loading module
  * has potential, but far from it
* Callbacks are easy, but become complex QUICKLY
	* promises are hard, but remain simple

## To become a better dev:
* JS Async
  [https://github.com/caolan/async](async lib)
* Promises
  [https://github.com/petkaantonov/bluebird](promise library)
  

## Libraries
* [Knex](http://knexjs.org) - Database DSL

## Frameworks

A review of NodeJS Frameworks can be found [here](http://nodeframework.com/)

Here's the main ones I reviewed:
* Express
  * minimal, but popular
* Sails
  * Rails-like
  * convention over configuration
  * hosts your hand to install, but then drops it
  * looks like primarily from one person
* Meteor
  * MongoDB for tutorial?  
  * ORM
* Touchdown - Yahoo
  * React + Express
  
## For me to investigate
* https://nodejs.org/docs/latest/api/repl.html#repl_event_exit 
	* reloading repl from scratch
* https://github.com/caolan/async - nodejs async
* https://tonicdev.com/  SUPER NEAT, but not applicable to ECS
	* browser based repl with visualizations of data
* https://www.npmjs.com/package/otaat-repl - repl mod
* date formatting: http://momentjs.com/
* REPL so you can inspect running instance https://www.npmjs.com/package/node-repl#installation


