# Reproduced bug #17

This bug is reported here: [Bug #17] (https://github.com/luxbet/ember-cli-llama-table/issues/17)

## Prerequisites

You will need the following things properly installed on your computer.

* [Git](http://git-scm.com/)
* [Node.js](http://nodejs.org/) (with NPM)
* [Bower](http://bower.io/)
* [Ember CLI](http://www.ember-cli.com/)
* [PhantomJS](http://phantomjs.org/)

## Installation

* `git clone https://github.com/szachara/llama-table-bug--17` this repository
* change into the new directory
* the bug is reproduced at branch `bug-#17`
* checkout that branch: `git co bug-#17`
* `npm install`
* `bower install`

## Running / Development

* `ember server`
* Visit your app at [http://localhost:4200](http://localhost:4200).

### Code Generators

Make use of the many generators for code, try `ember help generate` for more details

## How to reproduce this bug

- first install this repo, as is described in the `Installation` section above
- start server `ember serve`
- visit page [http://localhost:4200/users](http://localhost:4200/users)
  - as you can see any errors in console
- terminate ember serve
- install ember-cli-llama-table
  - `npm install ember-cli-llama-table --save-dev`
- start server `ember serve` again
- now visit again page [http://localhost:4200/users](http://localhost:4200/users)
  - on this route isn't used any `llama-table` code, not even in the __controller__ or in the __template__
- as you can see, there is error in console: `Error while processing route: users undefined is not a function TypeError: undefined is not a function`
- at the route [http://localhost:4200/test](http://localhost:4200/test) is used default llama-table example from Github's README.md
  - as you can see, the same error in console
- it doesn't matter on which page you are, or if on the current route the llama-table is used or not, when this addon is installed, the error occurs on every page
