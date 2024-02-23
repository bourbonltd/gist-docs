---
description: The Cordova implementation makes use of the Gist web library.
---

# Cordova

### Installation

#### NPM

Install the [NPM package](https://www.npmjs.com/package/@gistproduct/web)

```bash
npm install --save @gistproduct/web
```

To import and use Gist into your Cordova application you must copy the `dist/gist.min.js` file. You can use a utility like [cordova-import-npm](https://www.npmjs.com/package/cordova-import-npm) to automate the process.

#### Manual Download

Download the latest version of [Gist Web](web.md#installation) and add the script to your `index.html`

### Adding The Script

```markup
<script src="js/res/gist.min.js"></script>
```

### Setup

Inside your `config.xml` file add the following for both iOS & Android.

```markup
<platform name="android">
    <allow-navigation href="https://*gist.build*" />
...
```

```markup
<platform name="ios">
    <allow-navigation href="https://*gist.build*" />
...
```

To complete your setup, please follow the [Web](../api/webhook.md#setup) library setup guide.

### Important

The System action type does not work on Cordova, this is because internally, System actions behave as links with `target="blank"`. As an alternative, change System actions to Application, Add a listener on the `messageAction` event, and invoke them manually.
