Ionic 2
===================
**Ionic2** provides a platform to web developers to build great mobile apps and Progressive Web Apps in a way that feels just like building websites. That means the standard HTML, CSS, and JavaScript you are using to build a website will help you turn it into mobile magic.

Benefits of Ionic2 are as follows:

> - Cross platform mobile development framework
> - Angular 2 powered
> - Write once, deploy on different platforms
> - Runs on browser and devices
> - Debug on browser
> - Navigation like native(Push & Pop,no url base navigation)
> - Template Synatax
> - Ionicons
> - Tooling(ionic CLI)
> - Native Look & Feel
> - ES6 and Type Script etc…

Enough of  the introduction!!! Now let’s start with installation.

### Step 1

Download and install [node.js.](https://nodejs.org/en/)

### Step 2

Install cordova ( a framework that enables development for cross patform apps with HTML, CSS and JavaScript)
```sh
npm install -g cordova (mac/linux user write sudo)
```
### Step 3

Install Ionic CLI (This installs the Ionic Command Line Interface into your workstation.)
```sh
npm install -g ionic
```
To check the details of your installed ionic, simply run
```sh
ionic info
```
### Step 4

Install Typescript (TypeScript is a superset of JavaScript, and works really well with Angular 2).
```sh
npm install -g typescript
```
### Step 5

Create ionic 2 application
```sh
ionic start myfirstapp –v2 (tab application)
```
here –v2 specifies the ionic version 2

–v1 for ionic 1

You can get a list of available templates by simply writing
```sh
ionic start –list
```
### Step 6

Run the application,first navigate to your working directory then,
```sh
ionic serve
```
or
```sh
ionic serve -l
```

CLI commands
=================
List Of Ionic2 CLI commands which might be useful when building the application

Add new Page
```sh
ionic generate page nameofthepage 
```
Add new Platform like android and ios
```sh
ionic platform add android
ionic platform add ios
ionic platform add windows
ionic platform add browser
```
Build application for particular platform

Before running on device you must configure Android studio for Android application
```sh
ionic build android
```
To build for ios, you need to be using MacOs and have xCode installed. You also need two node modules installed globally. They just help in building and deploying the app.
```sh
npm install -g ios-deploy
npm install -g ios-sim version
ionic build ios
```
Run application on devices
```sh
ionic run andorid
ionic run ios
```

[Blog](http://www.c-sharpcorner.com/article/getting-started-with-ionic-2/)
