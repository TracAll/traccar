# [Traccar](https://www.traccar.org)

## Overview

Traccar is an open source GPS tracking system. This repository contains Java-based back-end service. It supports more than 200 GPS protocols and more than 2000 models of GPS tracking devices. Traccar can be used with any major SQL database system. It also provides easy to use [REST API](https://www.traccar.org/traccar-api/).

Other parts of Traccar solution include:

- [Traccar web app](https://github.com/traccar/traccar-web)
- [Traccar Manager Android app](https://github.com/traccar/traccar-manager-android)
- [Traccar Manager iOS app](https://github.com/traccar/traccar-manager-ios)

There is also a set of mobile apps that you can use for tracking mobile devices:

- [Traccar Client Android app](https://github.com/traccar/traccar-client-android)
- [Traccar Client iOS app](https://github.com/traccar/traccar-client-ios)

## Features

Some of the available features include:

- Real-time GPS tracking
- Driver behaviour monitoring
- Detailed and summary reports
- Geofencing functionality
- Alarms and notifications
- Account and device management
- Email and SMS support

## Build

Please read [build from source documentation](https://www.traccar.org/build/) on the official website.

Build from Source

Traccar server consists of a server and a web interface. Make sure you get both repositories if you want web interface to work. Web interface is a git submodule in the main Traccar repository, so you can checkout everything you need with a single git command:

git clone --recursive https://github.com/traccar/traccar.git

Build process contains of two parts. First is compiling server back-end from Java source code. Second one is creating installation files for various operating systems. Second part is the most complicated and it's not required unless you want to distribute your application.

In most cases all you need is to build Traccar from source code and replace original files on the server with newly compiled ones.

Following instructions are only for building server side. Android and iOS apps are standard Android Studio and Xcode projects, so there are no special instructions required.
Integrated Development Environment (IDE)

We recommend using IntelliJ IDEA when working with Traccar code, especially if you are only working on the server Java code. IntelliJ IDEA has a free and open source community edition that should be more than enough for server work.

    IntelliJ IDEA (recommended)
    NetBeans
    Eclipse is not recommended

For web app you might want to use Visual Studio Code or any other common IDE with good JavaScript support.
Build Server

To build binary server JAR file use following command:

./gradlew assemble

It will automatically download all dependencies and generate tracker-server.jar in the target subfolder. Now you can just replace the file in your Traccar installation and restart the service to changes to take affect. Make sure you have a compatible version of Traccar installed. Use the latest release when using master branch for development.
Build Web Interface

Web interface is written in JavaScript, so it doesn't require compiling, but release versions of Traccar use minified version where all files are combined into one and compressed.

If you modify web interface files, there are two deployment options:

    Upload new files into the server web folder and use debug.html to load non-compressed version of the web interface
    Generate minified version of the web interface using Sencha CDM tool

Generate Installers (optional)

You almost never need to do this. The only reason you would want to generate installer is to distribute your version of Traccar server.

You need to have a Linux system as the script is designed for Linux. We recommend the latest version of Ubuntu. If you are using Windows, you can install Ubuntu in a virtual machine.

To generate installer, execute setup/package.sh shell script in the terminal. The script will check all requirements and show if anything is missing and where to download missing package.

## Team

- Anton Tananaev ([anton@traccar.org](mailto:anton@traccar.org))
- Andrey Kunitsyn ([andrey@traccar.org](mailto:andrey@traccar.org))

## License

    Apache License, Version 2.0

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
