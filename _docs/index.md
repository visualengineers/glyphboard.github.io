---
title: Welcome
permalink: /home/
redirect_from: /glyphboard-doc/
---

## Getting started

[Glyphboard](https://github.com/visualengineers/glyphboard) is an open tool for visual analysis of high-dimensional data. The prototype was developed at Technische Universität Dresden in cooperation with Mercateo AG, chemmedia AG, and deecoob Technology GmbH as part of the [VANDA project](https://vanda-project.de/). If you want to test the application, please visit [itv21.informatik.htw-dresden.de:4200/](http://itv21.informatik.htw-dresden.de:4200/).

### Prerequisites

#### Install Node 

Download and install [NodeJS](https://nodejs.org/en/download/). Verify that you are running at least node 4.x.x and npm 3.x.x by running `node -v` and `npm -v` in a terminal/console window. Older versions produce errors, but newer versions are fine.

#### Install Angular for Frontend

Download and install command line interface of [Angular.IO](https://angular.io/) via NPM. We are using [Angular CLI](https://github.com/angular/angular-cli) version 1.0.0-beta.32.3.

`npm install -g @angular/cli`

#### Install Python for Data Backend

Please refer to [glyphboard-backend](https://github.com/visualengineers/glyphboard-backend) documentation.

#### Build and Run

Clone project and submodules [Glyphboard](https://github.com/visualengineers/glyphboard):

```
$ git clone --recursive git@github.com:visualengineers/glyphboard.git
```

This should yield the following directory structure of the project:

```
glyphboard/
├── backend/         --> python backend (see above)
├── node_modules/    --> created after npm install
├── e2e/ 
└── src/
    ├── app/
    │   ├── home/    --> main component
    │   └── shared/  --> components
    ├── assets/      --> static files
    └── environments/
```

Enter directory and run `npm install`

Run `npm start` for a dev server inside the project directory. Navigate to `http://localhost:4200/` for the client and `http://localhost:4201/` to test the backend. The app will automatically reload if you change any of the source files, but you will have to restart manually if you change the python backend.
