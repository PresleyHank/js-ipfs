<h1 align="center">
  <a href="ipfs.io">
    <img src="https://ipfs.io/ipfs/QmVk7srrwahXLNmcDYvyUEJptyoxpndnRa57YJ11L4jV26/ipfs.js.png" alt="IPFS in JavaScript logo" />
  </a>
</h1>

<h3 align="center">The JavaScript implementation of the IPFS protocol.</h3>

<p align="center">
  <a href="http://ipn.io"><img src="https://img.shields.io/badge/made%20by-Protocol%20Labs-blue.svg?style=flat-square" /></a>
  <a href="http://ipfs.io/"><img src="https://img.shields.io/badge/project-IPFS-blue.svg?style=flat-square" /></a>
  <a href="http://webchat.freenode.net/?channels=%23ipfs"><img src="https://img.shields.io/badge/freenode-%23ipfs-blue.svg?style=flat-square" /></a>
  <br> <a href="https://waffle.io/ipfs/js-ipfs"><img src="https://img.shields.io/badge/pm-waffle-blue.svg?style=flat-square" /></a>
  <a href="https://github.com/ipfs/interface-ipfs-core"><img src="https://img.shields.io/badge/interface--ipfs--core-API%20Docs-blue.svg"></a>
  <a href="https://github.com/ipfs/interface-ipfs-core/issues/55"><img src="https://img.shields.io/badge/interface--ipfs--core-Updates-blue.svg"></a>
</p>

<p align="center">
  <a href="https://app.fossa.io/projects/git%2Bhttps%3A%2F%2Fgithub.com%2Fipfs%2Fjs-ipfs?ref=badge_small" alt="FOSSA Status"><img src="https://app.fossa.io/api/projects/git%2Bhttps%3A%2F%2Fgithub.com%2Fipfs%2Fjs-ipfs.svg?type=small"/></a>
  <a href="https://travis-ci.org/ipfs/js-ipfs"><img src="https://travis-ci.org/ipfs/js-ipfs.svg?branch=master" /></a>
  <a href="https://circleci.com/gh/ipfs/js-ipfs"><img src="https://circleci.com/gh/ipfs/js-ipfs.svg?style=svg" /></a>
  <a href="https://coveralls.io/github/ipfs/js-ipfs?branch=master"><img src="https://coveralls.io/repos/github/ipfs/js-ipfs/badge.svg?branch=master"></a>
  <br>
  <a href="https://david-dm.org/ipfs/js-ipfs"><img src="https://david-dm.org/ipfs/js-ipfs.svg?style=flat-square" /></a>
  <a href="https://github.com/feross/standard"><img src="https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat-square"></a>
  <a href="https://github.com/RichardLitt/standard-readme"><img src="https://img.shields.io/badge/standard--readme-OK-green.svg?style=flat-square" /></a>
  <a href=""><img src="https://img.shields.io/badge/npm-%3E%3D3.0.0-orange.svg?style=flat-square" /></a>
  <a href=""><img src="https://img.shields.io/badge/Node.js-%3E%3D4.0.0-orange.svg?style=flat-square" /></a>
  <br>
  <!-- Hidding this until we have SauceLabs situation figured out, right now it is just misleading
  <a href="https://saucelabs.com/u/js-ipfs"><img src="https://saucelabs.com/browser-matrix/js-ipfs.svg" /></a> -->
</p>

### Project status

We've come a long way, but this project is still in Alpha, lots of development is happening, API might change, beware of the Dragons 🐉..

**Want to get started?** Check our [examples folder](/examples) to learn how to spawn an IPFS node in Node.js and in the Browser.

You can check the development status at the [Waffle Board](https://waffle.io/ipfs/js-ipfs).

[![Throughput Graph](https://graphs.waffle.io/ipfs/js-ipfs/throughput.svg)](https://waffle.io/ipfs/js-ipfs/metrics/throughput)

**Important to note:** DHT and Relay are not finalized yet, you won't have resource discovery happening by default as you get in go-ipfs, we are working actively on this pieces, please follow:
- https://github.com/ipfs/js-ipfs/pull/856
- https://github.com/ipfs/js-ipfs/issues/833

## Table of Contents

- [Install](#install)
  - [npm](#npm)
  - [Use in Node.js](#use-in-nodejs)
  - [Through command line tool](#through-command-line-tool)
  - [Use in the browser](#use-in-the-browser)
- [Usage](#usage)
  - [CLI](#cli)
  - [HTTP-API](#http-api)
  - [IPFS Core (use IPFS as a module in Node.js or in the Browser)](#ipfs-core-examples-use-ipfs-as-a-module)
    - [Create a IPFS node instance](#create-a-ipfs-node-instance)
  - [Tutorials and Examples](#tutorials-and-examples)
  - [API](#api)
    - [Files API](#files)
    - [DAG API](#dag)
    - [PubSub API](#pubsub)
    - [libp2p API](#libp2p)
    - [Miscellaneous API](#miscellaneous-operations)
    - [Bitswap API](#bitswap)
    - [Block API](#block)
    - [Config API](#config)
    - [Bootstrap API](#bootstrap)
    - [Repo API](#repo)
    - [Swarm API](#swarm)
    - [Object API](#object)
    - [Domain data types](#domain-data-types)
- [Packages](#packages)
- [Development](#development)
  - [Clone](#clone)
  - [Install Dependencies](#install-dependencies)
  - [Run Tests](#run-tests)
  - [Lint](#lint)
  - [Build a dist version](#build-a-dist-version)
- [Contribute](#contribute)
  - [Want to hack on IPFS?](#want-to-hack-on-ipfs)
- [License](#license)

## Install

This project is available through [npm](https://www.npmjs.com/). To install run

```bash
> npm install ipfs --save
```

Requires npm@3 and node >= 4.5, tested on OSX & Linux, expected to work on Windows.

### Use in Node.js

To include this project programmatically:

```JavaScript
const IPFS = require('ipfs')
const node = new IPFS()
```

### Through command line tool

In order to use js-ipfs as a CLI, you must install it with the `global` flag. Run the following (even if you have ipfs installed locally):

```bash
> npm install ipfs --global
```

The CLI is available by using the command `jsipfs` in your terminal. This is aliased, instead of using `ipfs`, to make sure it does not conflict with the [Go implementation](https://github.com/ipfs/go-ipfs).

### Use in the browser

Learn how to bundle with browserify and webpack in the [`examples`](https://github.com/ipfs/js-ipfs/tree/master/examples) folder.


You can also load it using a `<script>` using the [unpkg](https://unpkg.com) CDN. Inserting one of the following lines will make a `Ipfs` object available in the global namespace.

```html
<script src="https://unpkg.com/ipfs/dist/index.min.js"></script> <!-- loading the minified version -->
<script src="https://unpkg.com/ipfs/dist/index.js"></script>     <!-- loading the human-readable (not minified) version -->
```

## Usage

### CLI

The `jsipfs` CLI, available when `js-ipfs` is installed globally, follows(should, it is a WIP) the same interface defined by `go-ipfs`, you can always use the `help` command for help menus.

```sh
# Install js-ipfs globally
> npm install ipfs --global
> jsipfs --help
Commands:
  bitswap               A set of commands to manipulate the bitswap agent.
  block                 Manipulate raw IPFS blocks.
  bootstrap             Show or edit the list of bootstrap peers.
  commands              List all available commands
  config <key> [value]  Get and set IPFS config values
  daemon                Start a long-running daemon process
# ...
```

`js-ipfs` uses some different default config values, so that they don't clash directly with a go-ipfs node running in the same machine. These are:

- default repo location: `~/.jsipfs` (can be changed with env variable `IPFS_PATH`)
- default swarm port: `4002`
- default API port: `5002`
- default Bootstrap is off, to enable it set `IPFS_BOOTSTRAP=1`

If you want to use WebRTC in your local daemon, you will need to install it separatly by installing globally one of the following modules:

- [wrtc](https://npmjs.org/wrtc)
- [electron-webrtc](https://npmjs.org/electron-webrtc)

This is a separate step because there isn't still a good open source WebRTC implementation for Node.js that runs in all the envinronments correctly.
Example: `npm install electron-webrtc --global`. 

### HTTP-API

The HTTP-API exposed by the js-ipfs daemon follows the [`http-api-spec`](https://github.com/ipfs/http-api-spec). You can use any of the IPFS HTTP-API client libraries with it, such as: [js-ipfs-api](https://github.com/ipfs/js-ipfs-api).

### IPFS Core (use IPFS as a module)

#### Create a IPFS node instance

Creating an IPFS instance couldn't be easier, all you have to do is:

```JavaScript
// Create the IPFS node instance
const node = new IPFS()

node.on('ready', () => {
  // Your node is now ready to use \o/

  // stopping a node
  node.stop(() => {
    // node is now 'offline'
  })
})
```

#### Advanced options when creating an IPFS node.

When starting a node, you can:

```JavaScript
// IPFS will need a repo, it can create one for you or you can pass
// it a repo instance of the type IPFS Repo
// https://github.com/ipfs/js-ipfs-repo
const repo = <IPFS Repo instance or repo path>

// If you want to use the WebRTC transport in Node.js, you have to add it separately. Note, WebRTC comes out of the box in the Browser!
const wrtc = require('wrtc') // or require('electron-webrtc')()
const WStar = require('libp2p-webrtc-star')
const wstar = WStar({ wrtc: wrtc })

const node = new IPFS({
  repo: repo,
  init: true, // default
  // init: false,
  // init: {
  //   bits: 1024 // size of the RSA key generated
  // },
  start: true,
  // start: false,
  EXPERIMENTAL: { // enable experimental features
    pubsub: true,
    sharding: true, // enable dir sharding
    wrtcLinuxWindows: true, // use unstable wrtc module on Linux or Windows with Node.js,
    dht: true // enable KadDHT, currently not interopable with go-ipfs
  },
  config: { // overload the default config
    Addresses: {
      Swarm: [
        '/ip4/127.0.0.1/tcp/1337'
      ]
    }
  },
  libp2p: { // add custom modules to the libp2p stack of your node
    modules: { // here we show how to add WebRTC. Note, WebRTC comes out of the box in the Browser! You just need to do this for Node.js
      transport: [wstar]
      discovery: [wstar.discovery]
    }
  }
})

// Events

node.on('ready', () => {})    // Node is ready to use when you first create it
node.on('error', (err) => {}) // Node has hit some error while initing/starting

node.on('init', () => {})     // Node has successfully finished initing the repo
node.on('start', () => {})    // Node has started
node.on('stop', () => {})     // Node has stopped
```

### [Tutorials and Examples](/examples)

You can find some examples and tutorials in the [examples](/examples) folder, these exist to help you get started using `js-ipfs`.

### API

[![](https://github.com/ipfs/interface-ipfs-core/raw/master/img/badge.png)](https://github.com/ipfs/interface-ipfs-core)

A complete API definition is in the works. Meanwhile, you can learn how to you use js-ipfs through the standard interface at [![](https://img.shields.io/badge/interface--ipfs--core-API%20Docs-blue.svg)](https://github.com/ipfs/interface-ipfs-core).

##### [files](https://github.com/ipfs/interface-ipfs-core/tree/master/API/files)

- [`ipfs.files.add(data, [options], [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/files#add)
- [`ipfs.files.createAddStream([options], [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/files#createaddstream)
- [`ipfs.files.cat(multihash, [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/files#cat)
- [`ipfs.files.get(hash, [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/files#get)

##### [dag](https://github.com/ipfs/interface-ipfs-core/tree/master/API/dag)

- [`ipfs.dag.put(dagNode, options, callback)`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/dag#dagput)
- [`ipfs.dag.get(cid [, path, options], callback)`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/dag#dagget)
- [`ipfs.dag.tree(cid [, path, options], callback)`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/dag#dagtree)

##### [pubsub](https://github.com/ipfs/interface-ipfs-core/tree/master/API/pubsub)

- [`ipfs.pubsub.subscribe(topic, options, handler, callback)`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/pubsub#pubsubsubscribe)
- [`ipfs.pubsub.unsubscribe(topic, handler)`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/pubsub#pubsubunsubscribe)
- [`ipfs.pubsub.publish(topic, data, callback)`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/pubsub#pubsubpublish)
- [`ipfs.pubsub.ls(topic, callback)`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/pubsub#pubsubls)
- [`ipfs.pubsub.peers(topic, callback)`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/pubsub#pubsubpeers)

##### [libp2p](https://github.com/libp2p/interface-libp2p)

Every IPFS instance also exposes the libp2p API at `ipfs.libp2p`. The formal interface for this API hasn't been defined by you can find documentation at its implementations:

- [Node.js bundle](./src/core/runtime/libp2p-nodejs.js)
- [Browser Bungle](./src/code/runtime/libp2p-browser.js)
- [libp2p baseclass](https://github.com/libp2p/js-libp2p)

##### [miscellaneous operations](https://github.com/ipfs/interface-ipfs-core/tree/master/API/generic)

- [`ipfs.id([callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/generic#id)
- [`ipfs.version([callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/generic#version)
- `ipfs.ping()`
- `ipfs.init([options], callback)`
- `ipfs.start([callback])`
- `ipfs.stop([callback])`
- `ipfs.isOnline()`

##### [bitswap](https://github.com/ipfs/interface-ipfs-core/tree/master/API/)

- `ipfs.bitswap.wantlist()`
- `ipfs.bitswap.stat()`
- `ipfs.bitswap.unwant()`

##### [block](https://github.com/ipfs/interface-ipfs-core/tree/master/API/block)

- [`ipfs.block.get(cid, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/block#get)
- [`ipfs.block.put(block, cid, [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/block#put)
- [`ipfs.block.stat(cid, [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/block#stat)

##### [config](https://github.com/ipfs/interface-ipfs-core/tree/master/API/config)

- [`ipfs.config.get([key, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/config#configget)
- [`ipfs.config.set(key, value, [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/config#configset)
- [`ipfs.config.replace(config, [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/config#configreplace)

##### [bootstrap](https://github.com/ipfs/interface-ipfs-core/tree/master/API/)

- `ipfs.bootstrap.list`
- `ipfs.bootstrap.add`
- `ipfs.bootstrap.rm`

##### [repo](https://github.com/ipfs/interface-ipfs-core/tree/master/API/)

- `ipfs.repo.init`
- `ipfs.repo.version`
- `ipfs.repo.gc` (not implemented, yet!)

##### [swarm](https://github.com/ipfs/interface-ipfs-core/tree/master/API/swarm)

- [`ipfs.swarm.addrs([callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/swarm#addrs)
- [`ipfs.swarm.connect(addr, [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/swarm#connect)
- [`ipfs.swarm.disconnect(addr, [callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/swarm#disconnect)
- [`ipfs.swarm.peers([opts] [, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/swarm#peers)

##### [object](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object)

> Consider using the [dag API](#dag) API instead.

- [`ipfs.object.new([template][, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectnew)
- [`ipfs.object.put(obj, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectput)
- [`ipfs.object.get(multihash, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectget)
- [`ipfs.object.data(multihash, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectdata)
- [`ipfs.object.links(multihash, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectlinks)
- [`ipfs.object.stat(multihash, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectstat)
- [`ipfs.object.patch.addLink(multihash, DAGLink, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectpatchaddlink)
- [`ipfs.object.patch.rmLink(multihash, DAGLink, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectpatchrmlink)
- [`ipfs.object.patch.appendData(multihash, data, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectpatchappenddata)
- [`ipfs.object.patch.setData(multihash, data, [options, callback])`](https://github.com/ipfs/interface-ipfs-core/tree/master/API/object#objectpatchsetdata)

##### Domain data types

A set of data types are exposed directly from the IPFS instance under `ipfs.types`. That way you're not required to import/require the following.

- [`ipfs.types.Buffer`](https://www.npmjs.com/package/buffer)
- [`ipfs.types.PeerId`](https://github.com/libp2p/js-peer-id)
- [`ipfs.types.PeerInfo`](https://github.com/libp2p/js-peer-info)
- [`ipfs.types.multiaddr`](https://github.com/multiformats/js-multiaddr)
- [`ipfs.types.multihash`](https://github.com/multiformats/js-multihash)
- [`ipfs.types.CID`](https://github.com/ipld/js-cid)

##### [dht (not implemented, yet!)](https://github.com/ipfs/interface-ipfs-core/tree/master/API/)

##### [pin (not implemented, yet!)](https://github.com/ipfs/interface-ipfs-core/tree/master/API/)

## FAQ

> Is there WebRTC support for js-ipfs with Node.js?

Yes there is, however, Linux and Windows support is limited/unstable. For Linux users, you need to follow the install the extra packages for Linux listed on the [`wrtc` npm page](http://npmjs.org/wrtc) and then, when doing initing the repo, do:

```sh
> IPFS_WRTC_LINUX_WINDOWS=1 jsipfs init
```

This will create a repo with a config file that contains a WebRTC multiaddr.

## Packages

| Package | Version | Deps | DevDeps | Build |
|---------|---------|--------------|-----------------|-----------|
| **API Specs**                                      |
| [`interface-ipfs-core`](github.com/ipfs/interface-ipfs-core) | [![npm](img.shields.io/npm/v/interface-ipfs-core.svg?maxAge=86400&style=flat-square)](//github.com/ipfs/js-ipfs-repo/releases) | [![](david-dm.org/ipfs/interface-ipfs-core.svg?style=flat-square)](david-dm.org/ipfs/interface-ipfs-core) | [![](david-dm.org/ipfs/interface-ipfs-core/dev-status.svg?style=flat-square)](david-dm.org/ipfs/interface-ipfs-core?type=dev) | [![](travis-ci.org/ipfs/interface-ipfs-core.svg?branch=master)](travis-ci.org/ipfs/interface-ipfs-core) |
| [`http-api-spec`](github.com/ipfs/http-api-spec) |
| [`cli spec`](github.com/ipfs/specs/tree/master/public-api/cli) |
| **Repo**                                           |
| [`ipfs-repo`](//github.com/ipfs/js-ipfs-repo) | [![npm](img.shields.io/npm/v/ipfs-repo.svg?maxAge=86400&style=flat-square)](//github.com/ipfs/js-ipfs-repo/releases) | [![](david-dm.org/ipfs/js-ipfs-repo.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-repo) | [![](david-dm.org/ipfs/js-ipfs-repo/dev-status.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-repo?type=dev) | [![](travis-ci.org/ipfs/js-ipfs-repo.svg?branch=master)](travis-ci.org/ipfs/js-ipfs-repo) |
| **DAG**                                            |
| [`ipld-resolver`](github.com/ipld/js-ipld-resolver) | [![npm](img.shields.io/npm/v/ipld-resolver.svg?maxAge=86400&style=flat-square)](//github.com/ipld/js-ipfs-repo/releases) | [![](david-dm.org/ipld/js-ipld-resolver.svg?style=flat-square)](david-dm.org/ipld/js-ipld-resolver) | [![](david-dm.org/ipld/js-ipld-resolver/dev-status.svg?style=flat-square)](david-dm.org/ipld/js-ipld-resolver?type=dev) | [![](travis-ci.org/ipld/js-ipld-resolver.svg?branch=master)](travis-ci.org/ipld/js-ipld-resolver) |
| [`ipld-dag-pb`](github.com/ipld/js-ipld-dag-pb) | [![npm](img.shields.io/npm/v/ipld-dag-pb.svg?maxAge=86400&style=flat-square)](//github.com/ipld/js-ipld-dag-pb/releases) | [![](david-dm.org/ipld/js-ipld-dag-pb.svg?style=flat-square)](david-dm.org/ipld/js-ipld-dag-pb) | [![](david-dm.org/ipld/js-ipld-dag-pb/dev-status.svg?style=flat-square)](david-dm.org/ipld/js-ipld-dag-pb?type=dev) | [![](travis-ci.org/ipld/js-ipld-dag-pb.svg?branch=master)](travis-ci.org/ipld/js-ipld-dag-pb) |
| [`ipld-dag-cbor`](github.com/ipld/js-ipld-dag-cbor) | [![npm](img.shields.io/npm/v/ipld-dag-cbor.svg?maxAge=86400&style=flat-square)](//github.com/ipld/js-ipld-dag-cbor/releases) | [![](david-dm.org/ipld/js-ipld-dag-cbor.svg?style=flat-square)](david-dm.org/ipld/js-ipld-dag-cbor) | [![](david-dm.org/ipld/js-ipld-dag-cbor/dev-status.svg?style=flat-square)](david-dm.org/ipld/js-ipld-dag-cbor?type=dev) | [![](travis-ci.org/ipld/js-ipld-dag-cbor.svg?branch=master)](travis-ci.org/ipld/js-ipld-dag-cbor) |
| **Files**                                          |
| [`ipfs-unixfs-engine`](//github.com/ipfs/js-ipfs-unixfs-engine) | [![npm](img.shields.io/npm/v/ipfs-unixfs-engine.svg?maxAge=86400&style=flat-square)](//github.com/ipfs/js-ipfs-unixfs-engine/releases) | [![](david-dm.org/ipfs/js-ipfs-unixfs-engine.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-unixfs-engine) | [![](david-dm.org/ipfs/js-ipfs-unixfs-engine/dev-status.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-unixfs-engine?type=dev) | [![](travis-ci.org/ipfs/js-ipfs-unixfs-engine.svg?branch=master)](travis-ci.org/ipfs/js-ipfs-unixfs-engine) |
| **Exchange**                                       |
| [`ipfs-block-service`](//github.com/ipfs/js-ipfs-block-service) | [![npm](img.shields.io/npm/v/ipfs-block-service.svg?maxAge=86400&style=flat-square)](//github.com/ipfs/js-ipfs-block-service/releases) | [![](david-dm.org/ipfs/js-ipfs-block-service.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-block-service) | [![](david-dm.org/ipfs/js-ipfs-block-service/dev-status.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-block-service?type=dev) | [![](travis-ci.org/ipfs/js-ipfs-block-service.svg?branch=master)](travis-ci.org/ipfs/js-ipfs-block-service) |
| **Swarm/libp2p**                                   |
| [`js-libp2p`](github.com/libp2p/js-libp2p) | [![npm](img.shields.io/npm/v/libp2p.svg?maxAge=86400&style=flat-square)](//github.com/libp2p/js-libp2p/releases) | [![](david-dm.org/libp2p/js-libp2p.svg?style=flat-square)](david-dm.org/libp2p/js-libp2p) | [![](david-dm.org/libp2p/js-libp2p/dev-status.svg?style=flat-square)](david-dm.org/libp2p/js-libp2p?type=dev) | [![](travis-ci.org/libp2p/js-libp2p.svg?branch=master)](travis-ci.org/libp2p/js-libp2p) |
| [`libp2p-ipfs-nodejs`](//github.com/ipfs/js-libp2p-ipfs-nodejs) | [![npm](img.shields.io/npm/v/libp2p-ipfs-nodejs.svg?maxAge=86400&style=flat-square)](//github.com/ipfs/js-libp2p-ipfs-nodejs/releases) | [![](david-dm.org/ipfs/js-libp2p-ipfs-nodejs.svg?style=flat-square)](david-dm.org/ipfs/js-libp2p-ipfs-nodejs) | [![](david-dm.org/ipfs/js-libp2p-ipfs-nodejs/dev-status.svg?style=flat-square)](david-dm.org/ipfs/js-libp2p-ipfs-nodejs?type=dev) | [![](travis-ci.org/ipfs/js-libp2p-ipfs-nodejs.svg?branch=master)](travis-ci.org/ipfs/js-libp2p-ipfs-nodejs) |
| [`libp2p-ipfs-browser`](//github.com/ipfs/js-libp2p-ipfs-browser) | [![npm](img.shields.io/npm/v/libp2p-ipfs-browser.svg?maxAge=86400&style=flat-square)](//github.com/ipfs/js-libp2p-ipfs-browser/releases) | [![](david-dm.org/ipfs/js-libp2p-ipfs-browser.svg?style=flat-square)](david-dm.org/ipfs/js-libp2p-ipfs-browser) | [![](david-dm.org/ipfs/js-libp2p-ipfs-browser/dev-status.svg?style=flat-square)](david-dm.org/ipfs/js-libp2p-ipfs-browser?type=dev) | [![](travis-ci.org/ipfs/js-libp2p-ipfs-browser.svg?branch=master)](travis-ci.org/ipfs/js-libp2p-ipfs-browser) |
| **Data Types**                                     |
| [`ipfs-block`](//github.com/ipfs/js-ipfs-block) | [![npm](img.shields.io/npm/v/ipfs-block.svg?maxAge=86400&style=flat-square)](//github.com/ipfs/js-ipfs-block/releases) | [![](david-dm.org/ipfs/js-ipfs-block.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-block) | [![](david-dm.org/ipfs/js-ipfs-block/dev-status.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-block?type=dev) | [![](travis-ci.org/ipfs/js-ipfs-block.svg?branch=master)](travis-ci.org/ipfs/js-ipfs-block) |
| [`ipfs-unixfs`](//github.com/ipfs/js-ipfs-unixfs) | [![npm](img.shields.io/npm/v/ipfs-unixfs.svg?maxAge=86400&style=flat-square)](//github.com/ipfs/js-ipfs-unixfs/releases) | [![](david-dm.org/ipfs/js-ipfs-unixfs.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-unixfs) | [![](david-dm.org/ipfs/js-ipfs-unixfs/dev-status.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-unixfs?type=dev) | [![](travis-ci.org/ipfs/js-ipfs-unixfs.svg?branch=master)](travis-ci.org/ipfs/js-ipfs-unixfs) |
| [`peer-id`](//github.com/libp2p/js-peer-id) | [![npm](img.shields.io/npm/v/peer-id.svg?maxAge=86400&style=flat-square)](//github.com/libp2p/js-peer-id/releases) | [![](david-dm.org/libp2p/js-peer-id.svg?style=flat-square)](david-dm.org/libp2p/js-peer-id) | [![](david-dm.org/libp2p/js-peer-id/dev-status.svg?style=flat-square)](david-dm.org/libp2p/js-peer-id?type=dev) | [![](travis-ci.org/libp2p/js-peer-id.svg?branch=master)](travis-ci.org/libp2p/js-peer-id) |
| [`peer-info`](//github.com/libp2p/js-peer-info) | [![npm](img.shields.io/npm/v/peer-info.svg?maxAge=86400&style=flat-square)](//github.com/libp2p/js-peer-info/releases) | [![](david-dm.org/libp2p/js-peer-info.svg?style=flat-square)](david-dm.org/libp2p/js-peer-info) | [![](david-dm.org/libp2p/js-peer-info/dev-status.svg?style=flat-square)](david-dm.org/libp2p/js-peer-info?type=dev) | [![](travis-ci.org/libp2p/js-peer-info.svg?branch=master)](travis-ci.org/libp2p/js-peer-info) |
| [`multiaddr`](//github.com/multiformats/js-multiaddr) | [![npm](img.shields.io/npm/v/multiaddr.svg?maxAge=86400&style=flat-square)](//github.com/multiformats/js-multiaddr/releases) | [![](david-dm.org/multiformats/js-multiaddr.svg?style=flat-square)](david-dm.org/multiformats/js-multiaddr) | [![](david-dm.org/multiformats/js-multiaddr/dev-status.svg?style=flat-square)](david-dm.org/multiformats/js-multiaddr?type=dev) | [![](travis-ci.org/multiformats/js-multiaddr.svg?branch=master)](travis-ci.org/multiformats/js-multiaddr) |
| [`multihashes`](//github.com/multiformats/js-multihash) | [![npm](img.shields.io/npm/v/multihashes.svg?maxAge=86400&style=flat-square)](//github.com/multiformats/js-multihash/releases) | [![](david-dm.org/multiformats/js-multihash.svg?style=flat-square)](david-dm.org/multiformats/js-multihash) | [![](david-dm.org/multiformats/js-multihash/dev-status.svg?style=flat-square)](david-dm.org/multiformats/js-multihash?type=dev) | [![](travis-ci.org/multiformats/js-multihash.svg?branch=master)](travis-ci.org/multiformats/js-multihash) |
| **Generics/Utils**                                 |
| [`ipfs-api`](//github.com/ipfs/js-ipfs-api) | [![npm](img.shields.io/npm/v/ipfs-api.svg?maxAge=86400&style=flat-square)](//github.com/ipfs/js-ipfs-api/releases) | [![](david-dm.org/ipfs/js-ipfs-api.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-api) | [![](david-dm.org/ipfs/js-ipfs-api/dev-status.svg?style=flat-square)](david-dm.org/ipfs/js-ipfs-api?type=dev) | [![](travis-ci.org/ipfs/js-ipfs-api.svg?branch=master)](travis-ci.org/ipfs/js-ipfs-api) |
| [`ipfs-multipart`](//github.com/xicombd/ipfs-multipart) | [![npm](img.shields.io/npm/v/ipfs-multipart.svg?maxAge=86400&style=flat-square)](//github.com/xicombd/ipfs-multipart/releases) | [![](david-dm.org/xicombd/ipfs-multipart.svg?style=flat-square)](david-dm.org/xicombd/ipfs-multipart) | [![](david-dm.org/xicombd/ipfs-multipart/dev-status.svg?style=flat-square)](david-dm.org/xicombd/ipfs-multipart?type=dev) | [![](travis-ci.org/xicombd/ipfs-multipart.svg?branch=master)](travis-ci.org/xicombd/ipfs-multipart) |
| [`multihashing`](//github.com/multiformats/js-multihashing) | [![npm](img.shields.io/npm/v/multihashing.svg?maxAge=86400&style=flat-square)](//github.com/multiformats/js-multihashing/releases) | [![](david-dm.org/multiformats/js-multihashing.svg?style=flat-square)](david-dm.org/multiformats/js-multihashing) | [![](david-dm.org/multiformats/js-multihashing/dev-status.svg?style=flat-square)](david-dm.org/multiformats/js-multihashing?type=dev) | [![](travis-ci.org/multiformats/js-multihashing.svg?branch=master)](travis-ci.org/multiformats/js-multihashing) |
| [`mafmt`](//github.com/whyrusleeping/js-mafmt) | [![npm](img.shields.io/npm/v/mafmt.svg?maxAge=86400&style=flat-square)](//github.com/whyrusleeping/js-mafmt/releases) | [![](david-dm.org/whyrusleeping/js-mafmt.svg?style=flat-square)](david-dm.org/whyrusleeping/js-mafmt) | [![](david-dm.org/whyrusleeping/js-mafmt/dev-status.svg?style=flat-square)](david-dm.org/whyrusleeping/js-mafmt?type=dev) | [![](travis-ci.org/whyrusleeping/js-mafmt.svg?branch=master)](travis-ci.org/whyrusleeping/js-mafmt) |

## Development

### Clone and install dependencies

```sh
> git clone https://github.com/ipfs/js-ipfs.git
> cd js-ipfs
> npm install
```

### Run unit tests

```sh
# run all the unit tsts
> npm test

# run just IPFS tests in Node.js
> npm run test:unit:node:core

# run just IPFS core tests
> npm run test:unit:node:core

# run just IPFS HTTP-API tests
> npm run test:unit:node:http

# run just IPFS CLI tests
> npm run test:unit:node:cli

# run just IPFS core tests in the Browser (Chrome)
> npm run test:unit:browser
```

### Run interop tests

```sh
# run all the interop tsts
> npm run test:interop

# run just IPFS interop tests in Node.js using one go-ipfs daemon and one js-ipfs daemon
> npm run test:interop:node

# run just IPFS interop testsin the Browser (Chrome) using one instance in the browser and one go-ipfs daemon
> npm run test:interop:browser
```

### Run benchmark tests

```sh
# run all the interop tsts
> npm run test:benchmark

# run just IPFS benchmarks in Node.js
> npm run test:benchmark:node

# run just IPFS benchmarks in Node.js for an IPFS instance
> npm run test:benchmark:node:core

# run just IPFS benchmarks in Node.js for an IPFS daemon
> npm run test:benchmark:node:http

# run just IPFS benchmarks in the browser (Chrome)
> npm run test:benchmark:browser
```

### Lint

*Conforming to linting rules is a prerequisite to commit to js-ipfs.*

```sh
> npm run lint
```

### Build a dist version

```
> npm run build
```

### [Runtime Support](https://github.com/ipfs/js-ipfs/issues/536)

### Code Architecture and folder Structure

![](/img/overview.png)

##### Source code

```Bash
> tree src -L 2
src                 # Main source code folder
├── cli             # Implementation of the IPFS CLI
│   └── ...
├── http-api        # The HTTP-API implementation of IPFS as defined by http-api-spec
├── core            # IPFS implementation, the core (what gets loaded in browser)
│   ├── components  # Each of IPFS subcomponent
│   └── ...
└── ...
```

### IPFS Core Architecture

![](/img/core.png)

What does this image explain?

- IPFS uses `ipfs-repo` which picks `fs` or `indexeddb` as its storage drivers, depending if it is running in Node.js or in the Browser.
- The exchange protocol, `bitswap`, uses the Block Service which in turn uses the Repo, offering a get and put of blocks to the IPFS implementation.
- The DAG api (previously Object) comes from the IPLD Resolver, it can support several IPLD Formats (i.e: dag-pb, dag-cbor, etc).
- The Files API uses `ipfs-unixfs-engine` to import and export files to and from IPFS.
- Swarm, the component that offers a network API, uses libp2p to dial and listen for connections, use the DHT, discovery mechanisms and more. libp2p-ipfs-nodejs is used in case of running in Node.js and libp2p-ipfs-browser is used in the case of the Browser.

## Contribute

IPFS implementation in JavaScript is a work in progress. As such, there's a few things you can do right now to help out:

  * Go through the modules below and **check out existing issues**. This would be especially useful for modules in active development. Some knowledge of IPFS may be required, as well as the infrastructure behind it - for instance, you may need to read up on p2p and more complex operations like muxing to be able to help technically.
  * **Perform code reviews**. More eyes will help a) speed the project along b) ensure quality and c) reduce possible future bugs.
  * Take a look at go-ipfs and some of the planning repositories or issues: for instance, the libp2p spec [here](https://github.com/ipfs/specs/pull/19). Contributions here that would be most helpful are **top-level comments** about how it should look based on our understanding. Again, the more eyes the better.
  * **Add tests**. There can never be enough tests.
  * **Contribute to the [FAQ repository](https://github.com/ipfs/faq/issues)** with any questions you have about IPFS or any of the relevant technology. A good example would be asking, 'What is a merkledag tree?'. If you don't know a term, odds are, someone else doesn't either. Eventually, we should have a good understanding of where we need to improve communications and teaching together to make IPFS and IPN better.

### Want to hack on IPFS?

[![](https://cdn.rawgit.com/jbenet/contribute-ipfs-gif/master/img/contribute.gif)](https://github.com/ipfs/community/blob/master/contributing.md)

## License

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bhttps%3A%2F%2Fgithub.com%2Fipfs%2Fjs-ipfs.svg?type=large)](https://app.fossa.io/projects/git%2Bhttps%3A%2F%2Fgithub.com%2Fipfs%2Fjs-ipfs?ref=badge_large)
