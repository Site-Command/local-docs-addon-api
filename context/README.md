## ```context.environment```

Includes the following properties:

* **appPath:** Path to running Pressmatic.app
* **userHome:** Path to current user home directory
* **phpVersion:** Available PHP versions in Pressmatic
* **version:** Pressmatic version
* **dockerPath:** Path to Docker binary in Pressmatic.app
* **userDataPath:** Path to Pressmatic user data folder. On Mac OS X this defaults to ~/Library/Application Support/Pressmatic

## ```context.hooks```

Use context.hooks to run actions at certain times. Hooks are especially useful when adding in element with ```context.React```.

## ```context.electron```

Exposes [Electron API](http://electron.atom.io/docs/api/). The available methods and classes will differ based on whether or not this is ran from the main process or renderer process.

With the Electron API you can create dialogs, open new windows, and more.

## ```context.request```

[request](https://www.npmjs.com/package/request) npm package which makes it very easy to send HTTP/HTTPS requests.

## ```context.fileSystem```

[fs-extra](https://www.npmjs.com/package/fs-extra) npm package which extends the native [fs API](https://nodejs.org/api/fs.html) in Node.js.

## ```context.fileSystemJetpack```

[fs-jetpack](https://www.npmjs.com/package/fs-jetpack) npm package. Some may prefer it over the native [fs API](https://nodejs.org/api/fs.html) in Node.js.

## ```context.notifier```

[node-notifier](https://www.npmjs.com/package/node-notifier) npm package. The main method in this class is ```notify```.

#### Example

```js
context.notifier.notify({
  title: 'Notification Title',
  message: 'This is an example notification message.'
});
```

## ```context.process```
Node.js [process](https://nodejs.org/api/process.html) object.

## ```context.jQuery```
**Renderer Only**

[jQuery](http://api.jquery.com/) 3.0.x

## ```context.React```
**Renderer Only**

```context.React``` to required to use JSX in your renderer entry point. You can also use context.React to access React's [Top-Level API](http://facebook.github.io/react/docs/top-level-api.html).

For more information about React in Pressmatic addons please see [Using React.js](references/using_reactjs.md).

## ```context.docker```

Use ```context.docker``` to run Docker commands.

#### Example (ES6, needs transpiled to ES5)

```js
context.docker(`start ${container}`).then(stdout => {
    //Success
}).catch(({stdout, stderr}) => {
    //Something bad happened
});
```