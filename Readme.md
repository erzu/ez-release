# ez-release

Release npm packages easily.

`ez-release` is a command that combines common tasks about package publishments.

1. Generate changelog via `git changelog` command from [git-extras][1].
2. Update the `version` field in `package.json`.
3. Commit these two files.
4. Tag current version.
5. Push commit and tag onto remote.
6. Publish the package.

Here's the list of commands that will be executed.

```bash
$ ez-release patch --dryrun
     $ npm version patch --no-git-tag-version
     $ git changelog --tag 0.1.2
     $ git add package.json
     $ git commit -m 0.1.2
     $ git tag v0.1.2
     $ git push origin
     $ git push origin --tags
     $ npm publish
```

Running all the steps listed above manually can be tiresome and error prone.
So `ez-release` come to rescue. All you have to do is specify the new version,
whether it's a major, minor, or patch version bump. Then edit the generated
changelog. You are good to go.


## Install

```bash
$ brew install git-extras       # tested with version 3.0.0
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


[1]: https://github.com/tj/git-extras
