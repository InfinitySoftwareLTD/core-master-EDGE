## Create your Node Hedge and become a delegate

<p align="center">
    <img src="https://raw.githubusercontent.com/Plusid/core-master/chore/bridgechain-changes/banner.png" />
</p>

[![License: MIT](https://badgen.now.sh/badge/license/MIT/green)](https://opensource.org/licenses/MIT)

> Lead Maintainer: [Infinity developers](https://github.com/Plusid)


## Introduction

#### Manual installation Node Relay

#### Server Prerequisites

- minimum VPS recommended 
        4 vCPUs 8GB / 160GB Disk
- Ubuntu 20.04 (LTS) x64

On a fresh Ubuntu installation, follow these commands.

### 1. Update and Upgrade

Always ensure your server has the latest set of updates, due to performance and security considerations.

```
sudo apt-get update && sudo apt-get upgrade
```

### 2. Add a New User and Add to the Sudo Group

```
sudo adduser {username}
sudo usermod -aG sudo {username}
```



### 3. Switch to the New User

Switch to the new user account and go to the base directory.

```
sudo su {username}
```



## Setup


### 4. Install

Install_Relay_EDGE
###### *You can't be on ROOT*
```
cd ~
git clone https://github.com/InfinitySoftwareLTD/core-master-EDGE.git
cd core-master-EDGE
bash install.sh
```
You will be asked to input your current users password for sudo privileges. Write or paste it and press enter to start installation process.
 
###### if "username is not in the sudoers file.  This incident will be reported"


### 5. Choose a network "Mainnet"

we are setting `mainnet` node select it. This can be achieved by pressing `up` or `down` arrow keys and confirming selection with `enter`.
After you made your selection you will need to confirm by pressing `y` and confirm with `enter`.



### 6. Configuring Database

You will be presented with a prompt:
```
Would you like to configure the database? [y/N]:
```
Choice "y" and follow the exemple below:

```
Enter the database username: infinityhedge
Enter the database password: password
Enter the database name: edge_mainnet
```

This database will store the blockchain infinity.

### 7. Start the relay

Start_Relay
```
cd
cd core-master-EDGE
infinityhedge relay:start
```

### 8. Checking the relay

Status
```
pm2 status
```

Logs_relay
```
pm2 logs infinityhedge-relay
```
##### The database is updating 🎉 congratulation

Get out "Control (Ctrl) + C"


## Become a delegate "Become forger!"


### 9. Configuration forger

Entry_your_delegate_wallet_passphrase_as_forger
```
infinityhedge config:forger
```

###Choose a network
Mainnet
Start_Forging
```
infinityhedge forger:start
```
Your node will start to forge 
if the relay is synchronized with the blockchain, 
your wallet is registered as a delegate and 
you have enough votes to be delegates.


## Status and logs relay and delegate


### 10. Checking to See if Everything Is Working

Status
```
pm2 status
```

Logs_relay
```
pm2 logs infinityhedge-relay
```

Logs_forging
```
pm2 logs infinityhedge-forger
```


### 11. The last step

```
pm2 restart all --update-env
```


## API Test

> Please note that API will be available when the node has synced with the network
> 
Now that the relay node has been configured, you should head over to the JSON-RPC Getting Started


### 11. Test your API  

```
http://your_ip_server:4003
```
######     🎉 congratulation
      {"data":"Hello World!"}

###### Are there peers?
```
http://your_ip_server:4003/api/peers
```
######     🎉 congratulation
meta": {
"count": 24,
"pageCount": 1,
"totalCount": 24,
"next": null,
"previous": null,
"self": "/peers?page=1&limit=100",
"first": "/peers?page=1&limit=100",
"last": "/peers?page=1&limit=100"
},
...

###### Check your node configuration

```
http://your_ip_server:4003/api/node/configuration
```

## GitHub Development Bounty

-   Get involved with the development and start earning INFI : https://bounty.infinitysoftware.io



## Security

If you discover a security vulnerability within this package, please send an e-mail to security@infinitysoftware.io. All security vulnerabilities will be promptly addressed.



## License

[MIT](LICENSE) © [INFINITY Ecosystem](https://infinitysoftware.io)
