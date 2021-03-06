# Kitsunemimi-Project-Meta

This repository is only to keep an overview of my public and private repositories. With this the version of library requirements should be in sync. Beside this it is for issue tickets, which affect all repositories.

For the case that you ask, why it is named `Kitsunemimi-Project`: Its is not related to the content of the repositories. Originally I searched for a name schema for the libraries to differentiation them from other libraries. For this and because my private domain was already `kitsunemimi.moe`, I decided to name my libraries `libKitsunemimi...` and after some time I decided to make this as to the project name and collect all my sub-projects under this name, because kitsunemimi are moe. ;) 

Contact for questions: tobias.anker@kitsunemimi.moe

## Overview

The following diagramm shows the relations of the library and tools with each other. I know its not a vaild UML-diagramm, but I wanted to reduce the complexety to keep it a bit smaller. 

<p align="center">
  <img src=".pictures/overview.png?raw=true" alt="Overview"/>
</p>

### Main-Project (still private)

This is the main-project here, but it is still far away to be usable for any task, so its still private. In the core it provides an artificial neural network based on a concept created by myself. 

[KyoukoMind](#KyoukoMind)

[ToriiGateway](#ToriiGateway)

[MiyuMonitoring](#MiyuMonitoring)

[MikoClient](#MikoClient)

[MiraiControl](#MiraiControl)

[libKitsunemimiAiParser](#libKitsunemimiAiParser)

### Side-Projects

[SakuraTree](#SakuraTree) (paused)

Documentation of latest tagged version: https://files.kitsunemimi.moe/docs/SakuraTree-Documentation_0_4_1.pdf

### generic project libraries

Libraries for common usage inside of the Kitsunemimi-Project. 

[libKitsunemimiSakuraNetwork](#libKitsunemimiSakuraNetwork)

[libKitsunemimiSakuraLang](#libKitsunemimiSakuraLang)

[libKitsunemimiSakuraMessaging](#libKitsunemimiSakuraMessaging)

[libKitsunemimiSakuraGui](#libKitsunemimiSakuraGui)

### generic libraries

These simple generic libraries with wrapper, parser and functionalities I often use. Most of these stuff like CLI-argument-parser and so on, already exist in various implementations on github, but I wanded to create my own versions to have maximum control over the requirements and to have only a minimal set of funtions, which I really need.

[libKitsunemimiObj](#libKitsunemimiObj)

[libKitsunemimiOpencl](#libKitsunemimiOpencl)

[libKitsunemimiConfig](#libKitsunemimiConfig)

[libKitsunemimiArgs](#libKitsunemimiArgs)

[libKitsunemimiNetwork](#libKitsunemimiNetwork)

[libKitsunemimiJinja2](#libKitsunemimiJinja2)

[libKitsunemimiIni](#libKitsunemimiIni)

[libKitsunemimiJson](#libKitsunemimiJson)

[libKitsunemimiPersistence](#libKitsunemimiPersistence)

[libKitsunemimiCommon](#libKitsunemimiCommon)


## Repositories

__________

### KyoukoMind

#### Metadata

- **content**: Provides an artificial neural network based on a concept created by myself. It is way more dynamic than the commonly used deep-learning networks. Core characteristics:
    - No fully meshed random connections between nodes at the beginning. All connections are only created while learning new information.
    - No strict layer structure. Layers are only optional and can also be partially or completely disabled.
    - No limitation for to the range [0.0, 1.0] for input- and output-values. So no normalizing of input-values necessary.

- **additional commentary**: Actual tests with the MNIST handwritten digits dataset came up to 95.0% correct matches. This doesn't seems to the very good, but there is much potential for improvements in the parameters and initializing- and lerning-process, so the result is quite acceptable for the moment.

- **current version**: `0.3.0`

- **language**: `C++14`

- **visibility**: `private`

- **location**: `self-hosted Gitlab`

#### required tools to build

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | >= 3.0 | Build the parser-code together with the lexer-code.
xxd | xxd | >= 1.10 | converts text files into source code files

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system
ssl library | libssl-dev | 1.1.x | encryption for tls connections

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.18.0 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.1 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git
libKitsunemimiJson | v0.10.5 | https://github.com/kitsudaiki/libKitsunemimiJson.git
libKitsunemimiJinja2 | v0.8.0 | https://github.com/kitsudaiki/libKitsunemimiJinja2.git
libKitsunemimiIni | v0.4.6 | https://github.com/kitsudaiki/libKitsunemimiIni.git
libKitsunemimiArgs | v0.2.1 | https://github.com/kitsudaiki/libKitsunemimiArgs.git
libKitsunemimiConfig | v0.2.3 | https://github.com/kitsudaiki/libKitsunemimiConfig.git
libKitsunemimiSakuraLang | v0.7.2 | https://github.com/kitsudaiki/libKitsunemimiSakuraLang.git
libKitsunemimiNetwork | v0.6.5 | https://github.com/kitsudaiki/libKitsunemimiNetwork.git
libKitsunemimiSakuraNetwork | v0.5.0 | https://github.com/kitsudaiki/libKitsunemimiSakuraNetwork.git
libKitsunemimiObj | v0.1.1| https://github.com/kitsudaiki/libKitsunemimiObj.git
libKitsunemimiOpencl | v0.2.0| https://github.com/kitsudaiki/libKitsunemimiOpencl.git
libKitsunemimiSakuraMessaging | v0.4.0 | -
libKitsunemimiAiParser | v0.2.0 | -

__________

### ToriiGateway

#### Metadata

- **content**: Proxy for networking communication between the components.

- **current version**: `0.2.0`

- **language**: `C++14`

- **visibility**: `private`

- **location**: `Github`

#### required tools to build

name | repository | version | task
--- | --- | --- | ---
clang++ | clang++ | >= 4.0 | Compiler for the C++ code. (compared to the other Kitsunemimi-repositories this project requires clang++ instead of g++ because of some special stuff in the boost beast library)
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | >= 3.0 | Build the parser-code together with the lexer-code.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system
boost-beast library | (compiled form source) | 1.7x | provides http-server and websocket-server
ssl library | libssl-dev | 1.1.x | encryption for tls connections

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.18.0 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.1 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git
libKitsunemimiJson | v0.10.5 | https://github.com/kitsudaiki/libKitsunemimiJson.git
libKitsunemimiJinja2 | v0.8.0 | https://github.com/kitsudaiki/libKitsunemimiJinja2.git
libKitsunemimiIni | v0.4.6 | https://github.com/kitsudaiki/libKitsunemimiIni.git
libKitsunemimiArgs | v0.2.1 | https://github.com/kitsudaiki/libKitsunemimiArgs.git
libKitsunemimiConfig | v0.2.3 | https://github.com/kitsudaiki/libKitsunemimiConfig.git
libKitsunemimiSakuraLang | v0.7.2 | https://github.com/kitsudaiki/libKitsunemimiSakuraLang.git
libKitsunemimiNetwork | v0.6.5 | https://github.com/kitsudaiki/libKitsunemimiNetwork.git
libKitsunemimiSakuraNetwork | v0.5.0 | https://github.com/kitsudaiki/libKitsunemimiSakuraNetwork.git
libKitsunemimiSakuraMessaging | v0.4.0 | -

__________

### MiyuMonitoring

#### Metadata

- **content**: Graphical monitoring tool for visualization of the activity inside of the KyoukoMind-instance.

- **current version**: `0.1.1`

- **language**: `JavaScript + HTML + CSS`

- **visibility**: `private`

- **location**: `Github`

#### required official libraries

repository-name | version | task
--- | --- | ---
bootstrap | 4.5.3 | styling for basic objects like tables

#### Kitsunemimi-repositories

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiSakuraGui | v0.1.0 | -

__________

### MikoClient

#### Metadata

- **content**: Client to directly interact with the KyoukoMind-instance.

- **current version**: `0.1.0`

- **language**: `JavaScript + HTML + CSS`

- **visibility**: `private`

- **location**: `Github`

#### required official libraries

repository-name | version | task
--- | --- | ---
bootstrap | 4.5.3 | styling for basic objects like tables

#### Kitsunemimi-repositories

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiSakuraGui | v0.1.0 | -

__________

### MiraiControl

#### Metadata

- **content**: Controlling client to interact with a backend to check and set configurations.

- **current version**: -

- **language**: `go`

- **visibility**: `private`

- **location**: `Github`

#### required tools to build

name | repository | version | task
--- | --- | --- | ---
go | golang | >= 1.7 | Compiler for the go code.

__________

### libKitsunemimiAiParser

#### Metadata

- **content**: Parser-library for the input-files of KyoukoMind.

- **current version**: `0.2.0`

- **language**: `C++14`

- **visibility**: `private`

- **location**: `self-hosted Gitlab`

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | >= 3.0 | Build the parser-code together with the lexer-code.

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.18.0 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.1 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git
libKitsunemimiIni | v0.4.4 | https://github.com/kitsudaiki/libKitsunemimiIni.git

__________

### SakuraTree

(This project is actually paused.)

SakuraTree provides an automation tool to deploy applications, with high performance thanks to some features like easy parallelism of tasks and a self-created file syntax. It was primary created for the components of the Kyouko-Project and beside this also to automate different tasks on my deployment at home.

Documentation of current version: https://files.kitsunemimi.moe/docs/SakuraTree-Documentation_0_4_1.pdf

#### Metadata

- **content**: This is/should become a simple-to-use and fast automation tool to deploy tools and files on multiple nodes.

- **current version**: `0.4.1`

- **license**: `Apache 2`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/SakuraTree.git

#### required tools to build

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | >= 3.0 | Build the parser-code together with the lexer-code.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.15.1 | https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.0 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git
libKitsunemimiArgs | v0.2.1 | https://github.com/kitsudaiki/libKitsunemimiArgs.git
libKitsunemimiJson | v0.10.4 | https://github.com/kitsudaiki/libKitsunemimiJson.git
libKitsunemimiJinja2 | v0.8.0 | https://github.com/kitsudaiki/libKitsunemimiJinja2.git
libKitsunemimiIni | v0.4.5 | https://github.com/kitsudaiki/libKitsunemimiIni.git
libKitsunemimiSakuraLang | v0.5.1 | https://github.com/kitsudaiki/libKitsunemimiSakuraLang.git

__________

### libKitsunemimiSakuraNetwork

#### Metadata

- **content**: Self-created session-layer-protocol for network-communication in the Kitsunemimi-projects.

- **current version**: `0.5.0`

- **license**: `Apache 2`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiSakuraNetwork.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system
ssl library | libssl-dev | 1.1.x | encryption for tls connections

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.16.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.1 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git
libKitsunemimiNetwork | v0.6.5 | https://github.com/kitsudaiki/libKitsunemimiNetwork.git

__________

### libKitsunemimiSakuraLang

#### Metadata

- **content**: The library `libKitsunemimiSakuraLang` provides a simple script-language created by myself. It is packed as library for easy used in different tools. Originally it was created exclusively for the SakuraTree project (https://github.com/kitsudaiki/SakuraTree), but in the end it become generic and flexible enough to be also interesting for other upcoming projects, so it was moved into its own library.

- **current version**: `0.7.2`

- **license**: `Apache 2`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiSakuraLang.git

#### required tools to build

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | >= 3.0 | Build the parser-code together with the lexer-code.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.18.0 | https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.1 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git
libKitsunemimiJson | v0.10.5 | https://github.com/kitsudaiki/libKitsunemimiJson.git
libKitsunemimiJinja2 | v0.8.0 | https://github.com/kitsudaiki/libKitsunemimiJinja2.git

__________

### libKitsunemimiSakuraMessaging

#### Metadata

- **content**: Additional application-layer of the project related network stack.

- **current version**: `0.4.0`

- **license**: `Apache 2`

- **language**: `C++14`

- **visibility**: `private`

- **location**: `Github`

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | >= 3.0 | Build the parser-code together with the lexer-code.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system
ssl library | libssl-dev | 1.1.x | encryption for tls connections

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.16.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.1 |  https://github.com/kitsudaiki/libKitsunemimiPersistence.git
libKitsunemimiJson | v0.10.5 |  https://github.com/kitsudaiki/libKitsunemimiJson.git
libKitsunemimiJinja2 | v0.8.0 |  https://github.com/kitsudaiki/libKitsunemimiJinja2.git
libKitsunemimiIni | v0.4.6 |  https://github.com/kitsudaiki/libKitsunemimiIni.git
libKitsunemimiConfig | v0.2.3 |  https://github.com/kitsudaiki/libKitsunemimiConfig.git
libKitsunemimiSakuraLang | v0.7.1 |  https://github.com/kitsudaiki/libKitsunemimiSakuraLang.git
libKitsunemimiNetwork | v0.6.5 |  https://github.com/kitsudaiki/libKitsunemimiNetwork.git
libKitsunemimiSakuraNetwork | v0.5.0 |  https://github.com/kitsudaiki/libKitsunemimiSakuraNetwork.git

__________

### libKitsunemimiSakuraGui

#### Metadata

- **content**: Commonly used web-gui elements.

- **current version**: `0.1.0`

- **language**: `JavaScript + CSS`

- **visibility**: `private`

- **location**: `Github`

__________

### libKitsunemimiObj

#### Metadata

- **content**: This library provides a simple and minimal wavefront obj-parser and creator to generate the content of such files.

- **current version**: `0.1.1`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiObj.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.15.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.0 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git

__________

### libKitsunemimiOpencl

#### Metadata

- **content**: Simple wrapper-library for some commonly used OpenCL-functionallities.

- **current version**: `0.2.0`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiOpencl.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system
opencl-headers  | opencl-headers | 2.x | Header-files for opencl
ocl-icd-opencl-dev | ocl-icd-opencl-dev | 2.x | libraries for opencl

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.16.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.1 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git

__________

### libKitsunemimiConfig

#### Metadata

- **content**: Parser for cli-arguments.

- **current version**: `0.2.3`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiConfig.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | 3.x | Build the parser-code together with the lexer-code.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.15.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.0 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git
libKitsunemimiIni | v0.4.4 | https://github.com/kitsudaiki/libKitsunemimiIni.git

__________

### libKitsunemimiArgs

#### Metadata

- **content**: Small and easy to use parser for CLI-arguments.

- **current version**: `0.2.1`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiArgs.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.15.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.20.0 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git

__________

### libKitsunemimiNetwork

#### Metadata

- **content**: This is a small library for network connections. It provides servers and clients for unix-domain-sockets, tcp-sockets and ssl encrypted tcp-sockets.

- **current version**: `0.6.5`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiNetwork.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system
ssl library | libssl-dev | 1.1.x | encryption for tls connections

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.16.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiPersistence | v0.10.1 | https://github.com/kitsudaiki/libKitsunemimiPersistence.git

__________

### libKitsunemimiJinja2

#### Metadata

- **content**: Simple but imcomplete converter for jinja2-templates.

- **current version**: `0.8.0`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiJinja2.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | 3.x | Build the parser-code together with the lexer-code.

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.15.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git
libKitsunemimiJson | v0.10.4 |  https://github.com/kitsudaiki/libKitsunemimiJson.git

__________

### libKitsunemimiIni

#### Metadata

- **content**: Parser for the content of ini-files.

- **current version**: `0.4.6`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiIni.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | 3.x | Build the parser-code together with the lexer-code.

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.15.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git

__________

### libKitsunemimiJson

#### Metadata

- **content**: Parser for the content of json-files.

- **current version**: `0.10.5`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiJson.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.
FLEX | flex | >= 2.6 | Build the lexer-code for all used parser.
GNU Bison | bison | 3.x | Build the parser-code together with the lexer-code.

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.16.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git

__________

### libKitsunemimiPersistence

#### Metadata

- **content**: This library contains all my functions for interactions with the storage. At the moment its the smalest of my projects and only contains functionality to read, modify and write binaray- and text- files, handle an sqlite3-database and write log-files.

- **current version**: `0.10.1`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiPersistence.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.

#### Required generic libraries

name | repository | version | task
--- | --- | --- | ---
boost-filesystem library | libboost-filesystem-dev | 1.6x | interactions with files and directories on the system
sqlite3 library | libsqlite3-dev | 3.x | handling of sqlite databases (only when build with sqlite)

#### Required kitsunemimi libraries

Repository-Name | Version-Tag | Download-Path
--- | --- | ---
libKitsunemimiCommon | v0.16.1 |  https://github.com/kitsudaiki/libKitsunemimiCommon.git

__________

### libKitsunemimiCommon 

#### Metadata

- **content**: Simple C++ library with commenly used functions for memory-handling, thread-handling, data representation and testing. 

- **current version**: `0.18.0`

- **license**: `MIT`

- **language**: `C++14`

- **visibility**: `public`

- **location**: `Github`

- **repo-path**: https://github.com/kitsudaiki/libKitsunemimiCommon.git

#### Required build tools

name | repository | version | task
--- | --- | --- | ---
g++ | g++ | >= 6.0 | Compiler for the C++ code.
make | make | >= 4.0 | process the make-file, which is created by qmake to build the programm with g++
qmake | qt5-qmake | >= 5.0 | This package provides the tool qmake, which is similar to cmake and create the make-file for compilation.

