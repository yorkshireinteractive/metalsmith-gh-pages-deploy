# Metalsmith GitHub Pages Deployment Script

A shell deployment script for deploying metalsmith sites to GitHub pages.

## Why

[Metalsmith](http://metalsmith.io) is awesome. Yorkshire Interactive has used
it on 3 sites in just the past month. However, if you're wanting to deploy your
static site you built with Metalsmith there's no clean way to do it as far as
we could find. So, with a bit of hacking we came up with a deployment script.

## How

The tl;dr of how the script works is that it builds your files, goes into the
`build` directory, makes it a git repo, commits all the files and finally force
pushes all those files to your `gh-pages` branch.

## Setup

First of all, make sure you have ai git remote named `origin` that you have
access to.

Next, this script assumes your build script is at the root and called
`build.js`. If that isn't the case for you, just change the `node build.js`
line to call your build script.

Once you have that the simplest way to run this is just copying the file
to your project in the root and running it like `./deploy.sh`.

Or, if you prefer your scripts going through `npm` you could do something like
this which is what we do:

```json
{
  "name": "A project",
  "version": "1.0.0",
  "scripts": {
    "deploy": "./deploy.sh"
  },
  "author": "Yorkshire Interactive",
  "license": "MIT",
  "dependencies": {
    "metalsmith": "^2.1.0"
  }
}
```

This let's us call `npm run deploy` and it will kick off the script.

## Contributing

We're still new to Metalsmith so if there's a better deployment script or you
have ideas or comments about this one feel free to open a ticket or send a PR!

## Roadmap

Below are options we want to add to it:

- Pass a git remote URL instead of it assuming `origin`
- Pass your build command
- Change your build path
- Set your project root path
