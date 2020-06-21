# Node-Samba-Client

[![npm version](https://badge.fury.io/js/%40juangm%2Fsamba-client.svg)](https://badge.fury.io/js/%40juangm%2Fsamba-client)
[![Known Vulnerabilities](https://snyk.io/test/npm/@juangm/samba-client/badge.svg)](https://snyk.io/test/npm/@juangm/samba-client)

## Overview

- **node-samba-client** is a wrapper for smbclient for linux systems to interact with **SMB/CIFS** file sharing protocol.

## Requirements

- Requires Node.js 10+
- Smbclient must be installed.
- This can be installed on Ubuntu with `apt install smbclient`.

## Installation

Just run >>> `npm install @juangm/samba-client`

## Example (using Typescript)

```javascript
    import { SambaClient } from '@juangm/samba-client'

    const config: SmbConfig = {
        address: '//server/folder',
        domain: 'WORKGROUP',
        username: 'guest',
        password: 'test'
        path: '...',
        others: '...',
    };

    const client = new SambaClient(config);

    // send a file
    await client.sendFile('somePath/file', 'destinationFolder/name');

    // get a file
    await client.getFile('someRemotePath/file', 'destinationFolder/name');
```

## Future Plans

- [ ] Add support for Mac using `smbutil`
- [ ] Implement tests to check basic functionality
- [ ] Create CI with github actions
