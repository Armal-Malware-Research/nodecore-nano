# NodeCore-Nano
A client library used to interface with NanoCore 1.2.2.0 servers
| NOTE: This library is in early development, many features are still missing |
| --- |

## Installation
Use npm to install the library
```sh
npm install --save @armal/nodecore-nano
```

## Build from source
Use git to pull the package and build using tsc

```sh
git clone https://github.com/Armal-Malware-Research/nodecore-nano
cd nodecore-nano 
npm install
npx tsc
```

### Install from source
Use npm install with the path to your cloned directory
```sh
npm install <path-to-nodecore-nano>
```

# Usage
```js
const { NodeCoreClient } = require('@armal/nodecore-nano');

const client = new NodeCoreClient({
    hostname: '127.0.0.1',
    port: 1604
});

// Add event handlers here

// Example event: Reconnect on socket error
client.on('shutdown', e => {
    if (e.error) {
        e.cancel(); 
    }
});

client.connect();
```

## License
[MIT](https://choosealicense.com/licenses/mit/)
