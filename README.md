# Metachain Quorum Quickstart


## Table of Contents
1. [Prerequisites](#prerequisites)
2. [Usage](#usage)

## Prerequisites

To run these tutorials, you must have the following installed:

- [Docker and Docker-compose](https://docs.docker.com/compose/install/)

| ⚠️ **Note**: If on MacOS or Windows, please ensure that you allow docker to use upto 4G of memory or 6G if running Privacy examples under the _Resources_ section. The [Docker for Mac](https://docs.docker.com/docker-for-mac/) and [Docker Desktop](https://docs.docker.com/docker-for-windows/) sites have details on how to do this at the "Resources" heading       |
| ---                                                                                                                                                                                                                                                                                                                                                                                |


| ⚠️ **Note**: This has only been tested on Windows 10 Build 18362 and Docker >= 17.12.2                                                                                                                                                                                                                                                                                              |
| ---                                                                                                                                                                                                                                                                                                                                                                                |

- On Windows ensure that the drive that this repo is cloned onto is a "Shared Drive" with Docker Desktop
- On Windows we recommend running all commands from GitBash
- On Windows, WSL2 kernels prior to 5.10 have time drift issues which can impact block timestamps. To update the kernel, `wsl --shutdown` and then enable "Windows Update > Advanced Options > Receive updates for other Microsoft products when you update Windows". 
- [Nodejs](https://nodejs.org/en/download/) or [Yarn](https://yarnpkg.com/cli/node)



## Usage 

Create the docker-compose file and artifacts with 

```
$> npx metachain-quorum-quickstart
 
       ___            _          _            _                    _
      / _ \   _   _  (_)   ___  | | __  ___  | |_    __ _   _ __  | |_
     | | | | | | | | | |  / __| | |/ / / __| | __|  / _' | | '__| | __|
     | |_| | | |_| | | | | (__  |   <  \__ \ | |_  | (_| | | |    | |_ 
      \__\_\  \__,_| |_|  \___| |_|\_\ |___/  \__|  \__,_| |_|     \__|


Welcome to the Metachain Quorum Quickstart utility. This tool can be used
to rapidly generate local Quorum blockchain networks for production/development purposes
using tools like GoQuorum, Besu, and Codefi Orchestrate.

To get started, be sure that you have both Docker and Docker Compose
installed, then answer the following questions.

Which Ethereum client would you like to run? Default: [1]
	1. Hyperledger Besu
	2. GoQuorum
  ...
  Do you want to try out Codefi Orchestrate? [Y/n]
  ...
  Do you want to try out Quorum Key Manager? [Y/n]
  ...
  Do you wish to enable support for private transactions? [Y/n]
  ...
  Do you wish to enable support for logging with Splunk or ELK (Elasticsearch, Logstash & Kibana)? Default: [1]
	1. None
	2. Splunk
	3. ELK
...
Where should we create the config files for this network? Please
choose either an empty directory, or a path to a new directory that does
not yet exist. Default: ./quorum-test-network
```

This prompts you to pick a quorum variant, whether you would like to try Privacy and the location for the artifacts. By 
default artifact files are stored at `./metchain-quorum-network`, change directory to the artifacts folder: 

```
$> cd metachain-quorum-network
``` 


Alternatively, you can use cli options and skip the prompt above like so:

```
npx metachain-quorum-quickstart --clientType besu --outputPath ./metachain-quorum-network --monitoring default --privacy true --orchestrate false --quorumKeyManager false
```

The arguments ```--privacy``` and ```--clientType``` are required, the others contain defaults if left blank.

**To start services and the network:**

Follow the README.md file of select artifact:
1. [Hyperledger Besu](./files/besu/README.md)
2. [GoQuorum](./files/goquorum/README.md)
3. [Codefi Orchestrate](./files/orchestrate/README.md)
3. [Quorum Key Manager](./files/quorum-key-manager/README.md)
