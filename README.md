# grunt-download-atom-shell

Grunt tasks for downloading Electron, and the compatible version of `chromedriver`.
Note: older versions of Electron will download with the old name of 'atom-shell'

## Installation

Install npm package, next to your project's `Gruntfile.js` file:

```sh
npm install --save-dev grunt-download-atom-shell
```

Add this line to your project's `Gruntfile.js`:

```js
grunt.loadNpmTasks('grunt-download-atom-shell');
```

## Options

* `version` - **Required** The version of atom-shell you want to download.
* `outputDir` - **Required** Where to put the downloaded atom-shell.
* `downloadDir` - Where to find and save cached downloaded atom-shell.
* `symbols` - Download debugging symbols instead of binaries, default to `false`.
* `rebuild` - Whether to rebuild native modules after atom-shell is downloaded.
* `apm` - The path to apm.
* `token` - The [OAuth token](https://developer.github.com/v3/oauth/) to use for GitHub API requests.

### Usage

Add the necessary configuration to your `Gruntfile.js`:

```js
module.exports = function(grunt) {
  grunt.initConfig({
    'download-electron-shell': {
      version: '0.24.0',
      outputDir: 'my-dependencies'
    }
  });
};
```

or your `Gruntfile.coffee`:

```coffee
module.exports = (grunt) ->
  grunt.initConfig
    'download-electron-shell':
      version: '0.24.0'
      outputDir: 'my-dependencies'
```

**Note!**  Older versions of Electron were named 'atom-shell'.  Due to some breaking changes introduced during the rename, if you want to use a version of Electron older than ```0.24.0``` then you should use the ```download-atom-shell``` task definition instead of ```download-electron-shell```

```js
module.exports = function(grunt) {
  grunt.initConfig({
    'download-atom-shell': {
      version: '0.23.0',
      outputDir: 'my-dependencies'
    }
  });
};
```

Then you can download atom-shell to the path you specified:

```shell
$ grunt download-atom-shell
```

If you're doing selenium-testing of your atom-shell app, you'll need `chromedriver`, which is distributed with atom-shell. To download it into the atom-shell directory:

```shell
$ grunt download-atom-shell-chromedriver
```
