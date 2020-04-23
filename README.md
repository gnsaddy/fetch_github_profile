# Progressive Web App to fetch GitHub user profile.

```ProgressiveWebApp

Progressive Web App build using vanilla js, HTML, bootstrap, css.

Author - Aditya Raj

```
## ```Software Required```
- Nodejs 
- NPM
- VSCode
- Chrome Dev Tool
- GitHub API

## Installation
```javascript    

    $ sudo apt-get update
    $ sudo apt-get install nodejs
    $ sudo apt-get install npm
    -------------------------------------------------------------------
    Check Nodejs and NPM version

    $ nodejs -v
    $ npm -v

```

## ```npm init```
```
create a package.json file. You can add a package.json file to your package to make it easy for others to manage and install.

=> A package.json file:

- lists the packages your project depends on
- specifies versions of a package that your project can use using semantic versioning rules
- makes your build reproducible, and therefore easier to share with other developers
----------------------------------------------------------------------------
{
  "name": "fetch_github_profile",
  "version": "1.1.1",
  "description": "Fetching github particular details using Github API.",
  "main": "server.js",
  "scripts": {
    "start": "node server.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "dependencies": {
    "http-server": "0.12.1",
    "json": "9.0.6",
    "express": "4.17.1"
  },
  "keywords": [
    "pwa",
    "service-worker"
  ],
  "author": "Aditya Raj",
  "license": "ISC",
  "devDependencies": {
    "nodemon": "^2.0.3"
  }
}
```


## Install Modules with npm install
```javascript
Installing modules from npm is one of the most basic things you should learn to do when getting started with npm. 
As you dive deeper, you'll begin to learn some variations on installing modules, but here's the very core of 
what you need to know to install a standalone module into the current directory:

    $ npm install

Once you run this, npm will begin the installation process of all of the current project's dependencies which you specified in package.json
```
## Source: [Install documentation](https://nodesource.com/blog/an-absolute-beginners-guide-to-using-npm/)

## Github API
```API
This describes the resources that make up the official GitHub REST API v3.
Many of the resources on the users API provide a shortcut for getting 
information about the currently authenticated user. If a request URL does 
not include a :username parameter then the response will be for the logged
 in user (and you must pass authentication information with your request). 

The Search API helps you search for the specific item you want to find. 
For example, you can find a user or a specific file in a repository. Think 
of it the way you think of performing a search on Google. It's designed to
help you find the one result you're looking for (or maybe the few results
you're looking for). Just like searching on Google, you sometimes want 
to see a few pages of search results so that you can find the item that
best meets your needs. To satisfy that need, the GitHub Search API 
provides up to 1,000 results for each search.
```
 ```Follow the official documentation ```
## Source: [Github User Documentation](https://developer.github.com/v3/users/)
## Returning Github user details in json
```
fetch('https://api.github.com/users/<username>')
  .then((response) => {
    return response.json();
  })
  .then((data) => {
      #fetching value
    let values = Object.values(data);
    # fetching keys
    let keys = Objects.keys(data);
    for(let i=0;i<keys.length;i++){
        console.log(keys[i]);
        console.log(values[i]);
    }

    # all data
    console.log(data);
});
```
## Github user profile JSON formatted 
```
function fetchJSON() {
    fetch('https://api.github.com/users/gnsaddy')
        .then((response) => {
            return response.json();
        })
        .then((data) => {
            let container = document.getElementById('show_details');
            let login_id = document.createElement('span');
            // container.appendChild(login_id).innerHTML = ;
            let keys = Object.keys(data);
            let values = Object.values(data);
            for (let i = 0; i < keys.length; i++) {
                document.write('<table>');
                document.write(
                    '<tr>' + '<td>' + keys[i] + ' | ' + '<td>' + values[i] + '</tr>'
                );
            }
        })
        .catch((err) => {
            console.log('error ', err);
        });
}
```

## Open Chrome browser and run

```browser
    localhost:3000
```

# Tools and technology used:
``` 
1. HTML5
2. CSS3
3. vanilla Javascript
4. Http server
5. VS code
6. Git
7. Github
8. Express server
9. Nodejs and npm
10.Service Worker
11.Manifest
12.Android SDK
```
# References
## Source: [Express Server documentation](https://expressjs.com/en/5x/api.html)

## Source: [Node Server Documentation](https://nodejs.org/api/all.html)

## Source: [Github API](https://developer.github.com/v3/)

## Source: [PWA Documentation](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)