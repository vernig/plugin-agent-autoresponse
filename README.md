# Agent Canned and Auto-responses Example

There are two main files in this example:

```
src/AgentAutoResponsePlugin.js
src/CannedResponsesSelect.js
```

The main file is the `AgentAutoResponsePlugin.js` file, and contains many comments describing how the auto-response example is achieved. In addition, it appends the Canned Responses component in `CannedResponsesSelect.js` to Chat/SMS conversations.

While the canned-responses are static in this example, you might build on this example and call-out to your own server to retrieve your curated list of canned responses before rendering them in the Flex UI.

---

When you run this plugin - you'll see a pre-defined message sent by the answering agent as soon as they accept the task.

Additionally, you'll see new UI added below the Chat Input field which is a Select menu and will let you select from a list of pre-defined canned responses. When selecting any message in the select menu - it will automatically be sent into the chat/sms channel.

## Screenshot

![Screenshot](https://indigo-bombay-5783.twil.io/assets/auto-response-canned.png)

## Setup

Make sure you have [Node.js](https://nodejs.org) as well as [`npm`](https://npmjs.com) installed.

Afterwards install the dependencies by running `npm install`:

```bash
cd plugin-agent-autoresponse

# If you use npm
npm install
```

## Development

In order to develop locally, you can use the Webpack Dev Server by running:

```bash
npm start
```

This will automatically start up the Webpack Dev Server and open the browser for you. Your app will run on `http://localhost:8080`. If you want to change that you can do this by setting the `PORT` environment variable:

```bash
PORT=3000 npm start
```

When you make changes to your code, the browser window will be automatically refreshed.

## Deploy

Once you are happy with your plugin, you have to bundle it, in order to deply it to Twilio Flex.

Run the following command to start the bundling:

```bash
npm run build
```

Afterwards, you'll find in your project a `build/` folder that contains a file with the name of your plugin project. For example `plugin-example.js`. Take this file and upload it into the Assets part of your Twilio Runtime.

Note: Common packages like `React`, `ReactDOM`, `Redux` and `ReactRedux` are not bundled with the build because they are treated as external dependencies so the plugin will depend on Flex which would provide them globally.