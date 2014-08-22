# Backbone.Github.js

Backbone.Github.js provides a Backbone models/collections for User, Repository, Branches/Tags, Tree and Content APIs.
  
## Installation

TBD

## Usage

Create a Github instance.

```js
var github = new Github({
  username: "YOUR_USER",
  token: "YOUR_TOKEN"
});
```


[Github API OAuth Overview] (http://developer.github.com/v3/oauth)
## User API
```js
var logedInUser = github.getUser();

var anyUser = github.getUser(username);
```

## Repository API

```js
// Backbone.Collection
var userRepos = user.getRepositories(); // return repositories collection [not initialized]
var repo = github.getRepositories(username); // return repositories collection for specific user [not initialized]

// request repository without collection fetch:
var repoItem = userRepos.getRepository('REPO_NAME'); // Backbone.Model
repoItem.fetch();


// Fetch all repositories from Gtihub
userRepos.fetch({
  success: function() {
  },
  error: functinon() {
  }
});
```

## Branches API
