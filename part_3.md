Part 3: 👩🏼‍💻 Netlify Dev - Newest kid on the block (Still in Beta!)
Helps immensely with the local dev capability.
Netlify Dev - [How It Works ? Check Here!](https://www.netlify.com/products/dev/#how-it-works)
[Docs](https://www.netlify.com/docs/cli/#netlify-dev-beta)
It is a dev server that powers the local replication of what Netlify Production
Platform is and allows developers to replicate it on their local env.
Whenever we are aiming for faster integration cycles and we do not want to wait for the build bot, and all we need if full control and local replication of builds before install we go for this option.

```
#Install Netlify CLI
npm i -g netlify-cli

# Start Netlify Dev
netlify dev
```

- Has an inbuilt detector as well for checking if the directory in which netlify dev is being ran is linked to some netlify deployed website already.
- Running netlify-dev spawns a full local environment as well as:
  - Detects and runs your site generator
  - Makes env variables available
  - Performs edge logic (so that redirects work)
  - Compiles and runs cloud functions

netlify dev (netlify.toml)
command
port
netlify dev (detector)
env vars
redirects
netlify dev --live (beta)
netlify functions:create
netlify functions:invoke
netlify-lambda
netlify-lambda install
netlify-lambda build

On doing netlify dev there are 2 servers that are launched mostly at localhost:1234 and localhost:8888.
1234 port has dev build of react while 8888 has production build of react.
netlify dev runs yarn start as well as build
yarn start only runs on single port and doesn't unifies everything like dev.
Click [here](https://github.com/netlify/cli/tree/master/docs) for more info and references on Netlify dev.
There is a project server at port 5000 and there is a dev server at 8888 using netlify dev we send project server
to dev server and use it at 8888 port.
Parcel starts on port 1234 and other for separate things like React.

We know that for ntl dev we can go to netlify.toml and add config command for dev so that the port will be 1234
We add port, command and publish directory i.e. the place where \_redirects file will be located.
On doing netlify dev now instead of starting the static server this command will start parcel server at 1234.
Again gives us 2 servers at 1234 and 8888. Question is why bother using 2 servers ?
`netlify functions:create` creates a function folder and gives us options to choose from things, there's a template to get started. Go to functions/<function-name> directory and run npm install before using functions.
Go to netlify Environment Variables and remember in react if you want to expose variables to user you start those
with REACT_APP and here we do not want to do so that is why we name it as MY_SECRET.
We can take that evn var and process.env inside netlify function.
On doing netlify dev, dev server is created but a .netlify/functions/hello-world also runs

This is how you run environment variables from frontend as well as via functions.
Say we select node-fetch then node-fetch installs node modules with package json and pings an API.
`yarn add -D netlify-lambda` to be added as a helper.
