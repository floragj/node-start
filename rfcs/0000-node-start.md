# Node Start Buildpack

## Proposal

Create a buildpack that will require `node` to be in the app image and that will write a start command.

## Motivation

To support users that have Node.js applications that require no external `node modules` and does not contain a `package.json`.

## Implementation

Detection will pass if there is a .js file in the application source.

During the build, the buildpack will write the start command `node server.js`. `server.js` was selected as the default because it is the default application name chosen by `npm start` if the user does not specify a start command.

## Source Material (Optional)

[npm-start docs](https://docs.npmjs.com/cli/start.html)

## Unresolved Questions

Should we support a user's ability to specify an app filename other than `server.js` in our initial implementation?

{{REMOVE THIS SECTION BEFORE RATIFICATION!}}
