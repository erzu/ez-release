# ez-release

Release npm packages easily.


## Install

```bash
$ npm install ez-release -g
```


## Usage

```bash
$ ez-release patch -m 'Upgrade to %s for reasons'
$ ez-release patch --dryrun             # see what commands will be executed
```

```bash
$ ez-release --help
Usage ez-release [<newversion> | patch | minor | major | prepatch | preminor | premajor | prerelease]


  Options:

    --message, -m   The message for the commit of version and changelog. If the
                    message contains %s then that will be replaced with the
                    resulting version number.

    --dryrun, -d    Test run.

```


### Specify npm

```bash
$ NPM=cnpm ez-release
```
