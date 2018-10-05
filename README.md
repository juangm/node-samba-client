# Node-Samba-Client
## Overview
- **node-samba-client** is a wrapper for smbclient for linux and MacOs systems to interact with **SMB/CIFS** file sharing protocol. 
## Requirements
* Smbclient must be installed.
* This can be installed on OSX with Homebrew [using this script](https://raw.githubusercontent.com/Homebrew/homebrew-core/1fd22fea2426e1ae34e85177234c6e59f63add58/Formula/samba.rb) and on Ubuntu with `sudo apt install smbclient`.

## Installation
Just run >>> `npm install @juangm/samba-client`

## Example (using Typescript)

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
