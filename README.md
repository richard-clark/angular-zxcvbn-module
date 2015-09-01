# Angular ZXCVBN Module

Provides an Angular module Dropbox's [zxcvbn](https://github.com/dropbox/zxcvbn) password strength indicator without requiring that ``zxcvbn`` be defined globally.

## Installation

Using ``npm``:

```bash
npm install --save angular-zxcvbn-module
```

Using ``bower``:

```bash
bower install --save angular-zxcvbn-module
```

## Building

This releases uses version 3.2.2 of zxcvbn.

To use a different release, update ``package.json`` with the appropriate version, and run:

```bash
npm install
npm run build
```

## Usage

Watch a ``$scope`` variable named password and sets the ``passwordStrength`` ``$scope`` property whenever the password changes:

```javascript
angular.module('app', [
  'angular-zxcvbn-module'
]);

angular.module('controllers', [])
  .controller('SomeController', ["$scope", "zxcvbn"], function($scope, zxcvbn){
    $scope.$watch("password", function() {
      $scope.passwordStrength = zxcvbn($scope.password);
    });
  });
```
