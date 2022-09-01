# Vue部署包讀取外部config

## 目錄
- [Purpose](#purpose)
- [Environment](#environment)
- [Folder Structure](#folder-structure)
- [External Config](#external-config)
- [Build Deploy Package](#build-deploy-package)

## Purpose
In order not to re-build deploy package caused by changing api url, read the external config.js into vue project as solution. 

為了不因api url的變動而重複建立部署包，將外部config讀入部屬包作為解決方案

## Environment
Vue 3

## Folder Structure
![](https://i.imgur.com/p75ahqI.png)

## External Config
```
(function (window) {
  window.__env = window.__env || {};

  window.__env.url = {
      BASE_HOST: 'API_URL',
  };
})(this);
```

## Vue project include config.js file
```
<script src="<%= BASE_URL %>config/config.js"></script>
```
![](https://i.imgur.com/awXm4dB.png)

## Build Deploy Package
```
npm run build
```
![](https://i.imgur.com/skD54yB.png)


