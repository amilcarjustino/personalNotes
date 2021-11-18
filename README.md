# personalNotes
Some personal notes, about coding tips

# Note: package.son tips
*from "https://davidwells.io/blog/advanced-package-json-tips"

`{
  "name": "advanced-package-json",
  "version": "0.1.0",
  "private": true,
  "config": {
    "SESSION_ENDPOINT": "my-value"
  },
  "dependencies": {
    "react": "^15.6.1",
  },
  "scripts": {
    "pass-arg": "node scripts/lol.js --name=$npm_config_name",
    "set-env": "REACT_APP_ENDPOINT=$npm_package_config_ENDPOINT react-scripts start",
    "cross-env": "cross-env NODE_ENV=prod OTHERFLAG=xyz webpack --config webpack.js",
    "my-script": "esw src/components",
    "pass-flags-to-other-script": "npm run my-script -- --watch",
  },
  "devDependencies": {
    "react-scripts": "^1.1.4",
    "cross-env": "^1.1.4"
  }
}`

#To get the script arguments inside g.js file
`"scripts":{
    "gitty": "node g.js"
}`
In the command line:
*npm run gitty -- real updated message*
In the g.js file:
`let args = process.argv;
// arg[0] has "node"
// arg[1] has "g.js"
// arg[2] has "real"
// arg[3] has "updated"
// arg[4] has "message"
args.splice(0,2);
`
