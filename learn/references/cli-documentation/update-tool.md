---
layout: ballerina-cli-documentation-left-nav-pages-swanlake
title: Update Tool
description: Learn how to maintain your Ballerina programming language installation and keep it up to date with the latest releases.
keywords: ballerina, programming language, release, update
permalink: /learn/cli-documentation/update-tool/
active: update-tool
intro: This guide explains how to maintain your Ballerina installation up to date with the latest patch and minor releases.
redirect_from:
  - /learn/how-to-keep-ballerina-up-to-date
  - /learn/how-to-keep-ballerina-up-to-date/
  - /learn/keeping-ballerina-up-to-date/
  - /learn/keeping-ballerina-up-to-date
  - /swan-lake/learn/keeping-ballerina-up-to-date/
  - /swan-lake/learn/keeping-ballerina-up-to-date
  - /learn/tooling-guide/cli-tools/update-tool
  - /learn/tooling-guide/cli-tools/update-tool/
  - /learn/cli-documentation/update-tool
---

### Understanding Ballerina Distributions 

The Ballerina compiler is a software program, which validates the Ballerina source code and translates it to an executable program. Ballerina has a stable and production-ready official compiler called jBallerina, which targets the JVM.

Also, there is a plan to develop a native compiler called nBallerina in the future, which will target platforms such as Linux, Windows, and macOS.

Ballerina distribution is a term, which refers to these jBallerina and nBallerina compilers.

### Getting to Know the Release Channels

Ballerina distributions are released via two different release channels at the moment. Swan Lake release channel is the primary release channel and the other one is the 1.x release channel. It is recommended to use Swan Lake release channel, if you are new to Ballerina.

Ballerina yet does not have a release channel for nightly builds that give you access to the latest perhaps unstable features.

#### Patch Releases

Patch releases of Ballerina distributions contain bug fixes and fixes for critical stability and security related issues. Occasionally, you would see on-demand patch releases for 1.2.x.

*Example patch releases: 1.0.6, 1.1.5, 1.1.10*

## Installing Ballerina

If you haven’t installed Ballerina yet, see [Installing Ballerina](/learn/installing-ballerina/) for the instructions.

Once the installation is complete, you would see the directory structure below inside the installation directory.

```sh
.
├── bin
│   └── bal
├── dependencies
│   └── jdk-11.0.8+10-jre
├── distributions
│   ├── ballerina-slalpha3
│   ├── ballerina-slalpha4
│   ├── jballerina-1.1.0
│   ├── jballerina-1.2.8
│   └── ballerina-version
└── lib
    └── ballerina-command-1.3.1.jar
```

The `distributions` is the directory, in which all your installed distributions are maintained. Only one distribution from the above list can be active at a given time. 

> **Note:** The Ballerina Tool delegates most of the user requests to the active distribution. The commands such as `build`, `test`, `run`, `pull`, and `push` are delegated to the active distribution, while the commands such as `dist` and `version` are handled by the tool itself.
  
  E.g., when you invoke `bal build`, the Ballerina Tool dispatches this request to the active distribution.

You can [change this active distribution](#changing-the-active-distribution) at any time or manage it using the Ballerina Tool. However, first, you need to update the Ballerina Tool to its latest version.

### Updating the Ballerina Tool

The `bal update` command updates the Ballerina Tool itself to the latest version. Ballerina Tool versions are independent of the Ballerina distribution versions. These tool updates are expected to be rare compared to distribution releases.

```sh
→ bal update
Fetching the latest tool version from the remote server...
Downloading ballerina-command-1.3.3 100% [=====================================================================================================================================================================] 1/1 MB (0:00:01 / 0:00:00) 
Updating environment variables
The ‘ballerina’ command was changed to ‘bal’. Please use ‘bal’ command from now onwards.
Ie : $ bal build
     $ bal dist list
     $ bal dist update
Tool version updated to the latest version: 1.3.3
Cleaning old files...
Update successfully completed

If you want to update the Ballerina distribution, use 'bal dist update'
```

## Managing your Ballerina Distributions

After updating the Ballerina Tool, you can use the `bal dist` command of it to manage Ballerina distributions. The `bal help dist` output below shows all the details about the `bal dist` command.

```sh
→ bal help dist
NAME
       bal-dist - Manage Ballerina distributions

SYNOPSIS
       bal dist <command> <-h | --help>
       bal dist <command> [<args>]


DESCRIPTION
       Dist enables you to install, update, and switch among Ballerina distributions
       from patch and minor release channels.


OPTIONS
       -h, --help
           Print usage details of a command.


BALLERINA COMMANDS
       Here is a list of available subcommands:

       update     Update to the latest patch version of the active distribution
       pull       Fetch a distribution and set it as the active version
       use        Set a distribution as the active distribution
       list       List locally and remotely available distributions
       remove     Remove distributions in your local environment


Use 'bal help dist <command>' for more information on a specific command.
```

Most of these subcommands are self-explanatory. Therefore, the sections below introduce them briefly.

### Listing All Local and Remote Distributions

The `bal dist list` command lists the installed distributions in your local environment. It also lists the distributions available for you to download.

```sh
→ bal dist list
Distributions available locally: 

  [slalpha4] Alpha 3
* [slalpha5] Alpha 4

Distributions available remotely:

1.* channel

  [1.0.0] jballerina version 1.0.0
  [1.0.1] jballerina version 1.0.1
  [1.0.2] jballerina version 1.0.2
  [1.0.3] jballerina version 1.0.3
  [1.0.4] jballerina version 1.0.4
  [1.0.5] jballerina version 1.0.5
  [1.1.0] jballerina version 1.1.0
  [1.1.1] jballerina version 1.1.1
  [1.1.2] jballerina version 1.1.2
  [1.1.3] jballerina version 1.1.3
  [1.1.4] jballerina version 1.1.4
  [1.2.0] jballerina version 1.2.0
  [1.2.1] jballerina version 1.2.1
  [1.2.2] jballerina version 1.2.2
  [1.2.3] jballerina version 1.2.3
  [1.2.4] jballerina version 1.2.4
  [1.2.5] jballerina version 1.2.5
  [1.2.6] jballerina version 1.2.6
  [1.2.7] jballerina version 1.2.7
  [1.2.8] jballerina version 1.2.8
  [1.2.9]  jballerina version 1.2.9
  [1.2.10] jballerina version 1.2.10
  [1.2.11] jballerina version 1.2.11
  [1.2.12] jballerina version 1.2.12
  [1.2.13] jballerina version 1.2.13

Swan Lake channel

  [slp1] Preview 1
  [slp2] Preview 2
  [slp3] Preview 3
  [slp4] Preview 4
  [slp5] Preview 5
  [slp7] Preview 7
  [slp8] Preview 8
  [slalpha1] Alpha 1
  [slalpha2] Alpha 2
  [slalpha3] Alpha 3
  [slalpha4] Alpha 4
* [slalpha5] Alpha 5

Use 'bal help dist' for more information on specific commands.
```

> **Note:** The star (*) indicates the active distribution.

### Removing a Distribution

The `bal dist remove <distribution>` command allows you to delete a particular distribution from your local environment. If you’ve been updating Ballerina regularly, you may have accumulated many unused distribution versions. This command helps you to clean them up.

```sh
→ bal dist remove slalpha5
Distribution 'slalpha5' successfully removed
```

### Updating to the Latest Preview/Patch Version

The `bal dist update` command updates your active distribution to the latest patch version.

```sh
→ sudo bal dist update
Fetching the latest patch distribution for 'ballerina-slalpha4' from the remote server...
Fetching the 'slalpha5' distribution from the remote server...
Downloading slalpha5 100% [================================================================================================================================================================================] 319/319 MB (0:01:21 / 0:00:00) 

Fetching the dependencies for 'slalpha5' from the remote server...
Dependency 'jdk-11.0.8+10-jre' is already available locally
Successfully set the latest patch distribution 'slalpha5' as the active distribution
```

>**Note:** If the active distribution in your environment is `slp4`, it will bump to the next Swan Lake Preview version, which is `slp5`, and will update to it.

### Pulling a Specific Distribution

The `bal dist pull <distribution>` command downloads a particular distribution and stores it in your local environment. It also sets the fetched distribution as the active distribution.

```sh
→ bal dist pull slalpha4
Fetching the 'slalpha4' distribution from the remote server...
Downloading slalpha4 100% [================================================================================================================================================================================] 287/287 MB (0:01:26 / 0:00:00) 
  
Fetching the dependencies for 'slalpha4' from the remote server...
Dependency 'jdk-11.0.8+10-jre' is already available locally
'slalpha4' successfully set as the active distribution
```

### Changing the Active Distribution

The `bal dist use <distribution>` command sets a particular distribution version as the active one.

```sh
→ bal dist use slalpha3
'slalpha3' successfully set as the active distribution
```
