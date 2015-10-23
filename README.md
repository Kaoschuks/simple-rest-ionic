# Changing the Simple REST with ionic to Another Model
In this branch we are changing the master brach so it will work with a different model.
Instead of items object we are using the courses object. The do this we need to go to the ItemsModel service, DashboardCtrl controller and dashboard template, and change them to refer to courses courser instead of items. Here are the [changes](https://github.com/backand/simple-rest-ionic/commit/d8c3ce6d8a9e47117c203b55c530603e590ab2f7) made in the code for that.


## Prerequisites
You will need:
* [Git](http://git-scm.com/)
* [NodeJS and NPM](https://gist.github.com/isaacs/579814)

## Getting Started ##
1. Create new App in Backand with the following model (or just keep the default Model):

```json
[
  {
    "name": "courses",
    "fields": {
      "name": {
        "type": "string"
      },
      "description": {
        "type": "text"
      },
      "user": {
        "object": "users"
      },
      "tasks": {
        "collection": "tasks",
        "via": "course"
      },
      "task1": {
        "type": "string"
      },
      "task2": {
        "type": "string"
      }
    }
  },
  {
    "name": "tasks",
    "fields": {
      "description": {
        "type": "text"
      },
      "dueDate": {
        "type": "datetime"
      },
      "course": {
        "object": "courses"
      }
    }
  },
  {
    "name": "users",
    "fields": {
      "email": {
        "type": "string"
      },
      "firstName": {
        "type": "string"
      },
      "lastName": {
        "type": "string"
      },
      "courses": {
        "collection": "courses",
        "via": "user"
      }
    }
  }
]

```
2. Once the App is ready, run the following commands:

  ```bash
  $ git clone git@github.com:backand/simple-rest-ionic.git
  $ cd simple-rest-ionic
  $ npm install
  $ bower install
  ```
    
3. Ensure you have ionic installed:
  ```bash
  $ npm install -g cordova ionic
  ```
  
4. You can run ionic in the browser or simulator:

  Run in the web browser:
  ```bash
  $ ionic serve
  ```
  or 
  
  Run in an iOS simulator:
  ```bash
  $ ionic platform add ios
  $ ionic build ios
  $ ionic emulate ios
  ```

Ionic's [Getting Started](http://ionicframework.com/getting-started/) pages provide more help getting-started.
