
# ion-tree-list [![Bower version](https://badge.fury.io/bo/ion-tree-list.svg)](http://badge.fury.io/bo/ion-tree-list)

Ionic directive for displaying nested list ionic items.

Check [demo](http://fer.github.io/ion-tree-list/) link.

## Installation

```
bower install ion-tree-list --save
```

Add somewhere in your HEAD tag:

```
<script src="lib/ion-tree-list/ion-tree-list.js"></script>
```

You'll need to add ```ion-tree-list``` as a dependency on your Ionic app:

```
angular.module('starter', [
    'ionic', 
    'controllers', 
    'services', 
    'ion-tree-list'
])
```

In your ```controller.js```:

```
  $scope.tasks = [
    {
      name: 'first task 1',
      tree: [
        {
          name: 'first task 1.1'
        }
      ]
    },
    {
      name: 'first task 2'
    }
  ];    
```


In your ```view.html```:

```
<ion-tree-list items="tasks" collapsed="true"></ion-tree-list>
```

## Custom templates

Imagine your tasks in ```$scope.tasks``` in your ```controller.js``` has an extra attribute as ```checked```:

```
  $scope.tasks = [
    {
      name: 'first task 1',
      checked: false,
      tree: [
        {
          name: 'first task 1.1',
          checked: true
        },
      ]
    },
    {
      name: 'first task 2',
      checked: true
    }
  ];
```

In order to consume the ```checked``` value in your view, create a ```ion-item.tmpl.html``` file in 
your www folder containing the following:

```
<input type="checkbox" ng-model="item.checked"/>
{{item.name}}
```

Add an extra ```template-url``` attribute for your custom template:
 
```
<ion-tree-list items="tasks" template-url="'ion-item.tmpl.html'"></ion-tree-list>
```
# Contribute

[![Stories in Ready](https://badge.waffle.io/fer/ion-tree-list.png?label=ready&title=Ready)](https://waffle.io/fer/ion-tree-list)


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/fer/ion-tree-list/trend.png)](https://bitdeli.com/free "Bitdeli Badge")
