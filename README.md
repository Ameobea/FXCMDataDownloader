# FXCM NodeJS/Java Data Downloader + API Interface
This application creates a Java server that communicates with a NodeJS client using Redis PubSub.  It currently contains functionality to both download historical data as well as subscribe to live tick updates.

## Installation
First, check out `IMPORTANT.md` (https://github.com/Ameobea/FXCMDataDownloader/blob/master/server/src/tickrecorder/IMPORTANT.md) for some info on how to initialize Java for running the server.  There are some weird dependencies that need to be installed (included in `/server/dist/lib`).  In addition, you'll have to update `PrivateConfig.java` in `/server/src/tickrecorder` with your FXCM credentials.  And no, the ones I left in there are for an expired trial account so don't waste your time.

You'll need a Redis server installed to serve as the link between the client and the server running on the default port with no password auth.  It's only used for message passing so it shouldn't need more than a few MB of memory as it never actually stores anything.  Oh and make sure to lock it down with a firewall of suffer the consequences.

The NodeJS client should run as-is on any modern Node environment.  Simply edit lines 30-32 in `client/download.js` (yeah no command line arguments yet) to your desired values and then run it with `node

## Contributing
Feel free to drop in a PR/submit an issue for any problems/questions you have.  I hope you can find this useful in some way!
