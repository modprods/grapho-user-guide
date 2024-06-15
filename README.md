# grapho-user-guide

![graphobymod-black](img/graphobymod-black.png)

User guide for the Grapho data science + storytelling toolkit

# Table of Contents

- [Introduction](#introduction)
- [Grapho XR](#grapho-xr)
  - [Quickstart](#quickstart-for-grapho-xr)
  - [Interactivity](#interactivity)
- [Grapho VM](#grapho-vm)
- [Online Services](#online-services)
  - [Dashboard](#dashboard)
  - [API](#graphoapi)
  - [Integrations](#integrations)
  - [Importers](#importer)
- [Troubleshooting](#troubleshooting)
- [Change Log](#changelog)

# Introduction

Welcome to the user guide for Grapho - a toolkit for data science + storytelling.

In 2024 data science is having a moment with the explosion in generative AI fuelled by deep learning techniques and vast data collections. But the reality is that for all the technical advances, it comes back to humans. How are we collecting data? Why are we collecting it? What are our motivations for using it? How do we communicate? Getting to grips with modern data still requires that ancient skillset we've evolved - storytelling - and how we tell stories is changing. 

This toolkit is for anyone anyone working with graph data. It empowers users to create data stories and draw connections in real-time within immersive virtual worlds. Explore and query graphs using parameters relevant to you. Grapho producitivity tools make taking a deep dive into complex data sets more accessible and engaging. It brings connections to life.  

Return to [Table of Contents](#table-of-contents).

# History

Grapho started life as a spatial knowledge graph interface for a VR documentary [A Clever Label](https://acleverlabel.com) released on Steam in 2021 using a Neo4j backend. This was then spun out as a white label tool  [Grapho XR](#Grapho-XR) in 2022 for applied data science. Our first customer was [APNIC](https://www.apnic.net/). 

In 2024 a new ISO database language standard [Graph Query Language](https://www.iso.org/standard/76120.html) was published (the first in 37 years since SQL) that defines data structures and basic operations on property graphs largely.

Return to [Table of Contents](#table-of-contents).

# Roadmap

Grapho is available through Mod's SaaS and consulting service.

[Contact us](https://mod.studio/where/) for more information.

Return to [Table of Contents](#table-of-contents).

# Grapho XR

Grapho XR is a visualisation tool and a new way to manage and present graph data. It's an interactive experience that feels like Minority Report meets 60 Minutes. Grapho provides flexibility to switch between data sets and between visual themes, ensuring the look is right for your audience. Display and take control of your data. Share knowledge in a hands-on intuitive way. Use it on-set as an interactive in-camera VFX solution. 

See the [Grapho XR Roadmap](https://trello.com/b/aIg9JRxM/grapho-roadmap-graphoapp) for more details

Return to [Table of Contents](#table-of-contents).

## Quickstart for Grapho XR

### PCVR

* Run Meta Quest Link for Windows 
* Connect your Quest to PC via OculusLink (USB-C cable) or AirLink (Wifi gen6 only)
* Unzip Grapho build ZIP
* Run Grapho.exe direct or use provided BAT file to specify VR or Desktop mode
    * RunGraphoVR.bat
        * start ./Grapho.exe -vr (default)
    * RunGraphoDesktop.bat
        * start ./Grapho.exe -noxrstereo (Desktop is for users without VR)

### Mobile VR

* Unzip Grapho build ZIP
* Connect your Quest to PC via OculusLink (USB-C cable) or AirLink (Wifi gen6 only)
* Double click installer 
    * Android/Install_Grapho-Android-Shipping-arm64.bat

Return to [Table of Contents](#table-of-contents).

### Induction

* Reach out and grab the disk "Enter The Matrix" with the GRAB button
* Flip it upside down to open
* Grab nodes with the GRAB button
* Use the joystick to TELEPORT
* Use [FORCE PULL](#ForcePull) to grab nodes from a distance
* See [​GraphSummitSydney2024-induction](https://vimeo.com/943161258/f7311ebf2c) for explainer video of the core mechanic using Meta Quest 3
* See Change Log for recent updates

Return to [Table of Contents](#table-of-contents).

## System Requirements

Grapho XR builds are available for the following platforms.

* PCVR
* Mobile VR

Grapho XR is available as plugins for third party development with the following frameworks 
* [Unreal Engine](https://unrealengine.com/) 5.4

Return to [Table of Contents](#table-of-contents).

### PCVR

* Windows 10 or 11
* 16 GB RAM or better
* Intel Core i7-3930K/AMD FX 8350 equivalent or better
* NVIDIA GeForce GTX 970, AMD Radeon R9 290 equivalent or better
* 1 GB available space
* Oculus or Steam VR compatible HMD (for PCVR)
    * Quest 2 / Quest Pro / Quest 3
    * Valve Index
    * HTC Vive / Vive Pro / Vive Pro 2 / Vive Focus 3 / Vive Elite XR

NOTE Grapho XR's "desktop mode" (non-XR) support on Windows is provided for backwards compatibility, accessibility, and testing. We only recommend use of 3D visualisation on 3D displays for professional use given given research findings that 2D visualisation works better on a 2D displays. See [Dashboard](#dashboard) options for off-the-shelf and custom options. 

### Mobile VR

* Quest 2 / Quest Pro / Quest 3
* Vive Focus 3 / Vive Elite XR
* Controllers required

We don't currently recommend hand tracking for precise manipulation of graph data for professional use.

Hand tracking support on request. 

Return to [Table of Contents](#table-of-contents).

## Interactivity

### Teleport

![teleport](img/grapho-teleport.png)

Push LEFT or RIGHT joystick forward to show reticule and direction arrow on the ground plane. Rotate joystick to change direction of the arrow. This determines what direction you teleport. Release joystick to teleport. 

NOTE Users new to VR can get confused if they trigger teleport by mistake. You can change Settings > Teleport delay to adjust how responsive the joysticks are if this is a problem. 

### Grab

![grab](img/grapho-grab-button.png)

Use GRIP button to grab object (handle, node, relationship).

### Force Pull

![force-pull](img/grapho-force-pull.png)

Force pull is a telekinesis-like feature that lets you quickly grab an object regardless of its distance from you.

VR mode:
* Force pull - select object with the laser point extending from your virtual hand, pull TRIGGER and flick your wrist upward or to the side (like pulling a line on a fishing rod)
Desktop mode:
* Grab a node from a distance pressing G key and it will be force pulled towards the camera automatically

### Bump

Use natural hand movements to move objects out of the way

### Open Graph

![handle-open](img/grapho-handle-open.png)

Grab Handle. Flip Handle upside down to open graph nodes (run a query).

A Handle is a special type of node that is a convenient handle to a section of a graph that speeds up navigation and helps manage clutter.

You can think of it as a graph bookmark but technically it signposts a specify database query. I.e. the graph data returned may change.

Flip again to close graph nodes.

![handle-close](img/grapho-handle-close.png)

### Open Node

![node-open](img/grapho-datapad.png)

Press TRIGGER button to toggle opening and closing of a node to reveal its "Datapad" which shows the properties of a node. 

Settings > Open Datapad on Grab checkbox controls whether this happens automatically on GRAB. It can get annoying sometimes to have this on but useful as a default for new starters.

### Open Context Menu

![context-menu](img/grapho-context-menu.png)

Additional functionality is available while holding a node.

GRAB + <FACE BUTTON #1> opens a floating menu of buttons  

While keeping buttons pressed, move hand over the buttons to highlight them

Release <FACE BUTTON #1> to select highlight action.

Move your hand off the menu and release <FACE BUTTON #1> to close menu without doing an action.

#### Expand

Context Menu | Expand 

Any neighbouring node not already visible are spawned

#### Collapse

Any neighbouring node that was previously expanded (but not part of original query) is hidden

#### Hide

The node is hidden. 

To reveal node again you currently have to Close Graph and Open Graph again using the Handle

#### Hide Unselected

![hide-unselected](img/grapho-hide-unselected.png)

#### Pin
The node is pinned in place - moving neighbouring parts of the graph will have no effect on it

#### Unpin

The node is unpinned - moving neighbouring parts of the graph will effect its position

#### Bookmark

Not yet implemented. Sorry about that!

#### Settings Menu

![settings](img/grapho-settings.png)

Press SETTINGS button or FACE BUTTON #2 to toggle a menu

NOTE - Changed settings are saved to your local device. There is currently no Reset Settings feature

![settings](img/grapho-settings-options.png)

* Restart (button) - restart application
* Arrange by type (toggle) - Check this to cluster all nodes by their given types (labels in Neo4j speak).
* Max nodes (spinbox) - limit how many nodes can be displayed at any time
* API URL (list) - choose from available Grapho API servers
* Database (list) - choose from available graph databases (per server)
* Refresh API (button) - re-run query. Useful for network troubleshooting
* Mouse Sensitivity - for desktop mode only
* Movement Speed - for desktop mode only
* Teleport Delay - increase delay to prevent accidentally use of teleport

Return to [Table of Contents](#table-of-contents).

# Grapho VM

Grapho VMs (aka "Grapho Virtual Machines") are Linux virtual machine containers that package Grapho online services to be used on-premise or on cloud platforms.

We use [packer](https://www.packer.io/) and [terragrunt](https://terragrunt.gruntwork.io/) to keep on-premise and cloud-hosted virtual machine variants in sync.

Supported virtual machine platforms

* Windows WSL2
* LXC
* AWS AMI
* Virtual Box
* VMWare

Our standard Linux operating system is Debian. Contact us for other format requests.

Return to [Table of Contents](#table-of-contents).

# Online Services

## Dashboard

Graph data front-ends custom built for specific use cases from popular frameworks.

Integrations

* Neodash
* Streamlit
* Wagtail

Contact us for requests.

Return to [Table of Contents](#table-of-contents).

## API

grapho-server is a sample python REST API service available to Grapho customers

This provides a thin abstraction layer to help manage vendor lock-in and provide data to Grapho applications in a consistent manner as part of a manageable pipeline.

Features
* OpenAPI compliant documentation
* REST API endpoints for graph database queries
* Mux database queries (e.g. CYPHER, SQL) with local config
* Support for running on local desktop, on-premise hosting and cloud platforms

Open source release COMING SOON

### demo.grapho.app

[Grapho XR](#GraphoXR) API
* Provides access to curated sample graph data sets from Neo4j and local configuration files.
* See https://demo.grapho.app/docs

Return to [Table of Contents](#table-of-contents).

## Integrations

* Neo4j
    * Community Edition - v4.4, v5
    * Enterprise Edition - v4.4, v5
    * Plugins
        * Bloom
      * GDS
      * APOC
    * Neodash
* Streamlit
* Gradio
* Jupyter
* Django
    * Wagtail

Return to [Table of Contents](#table-of-contents).

Formats

* JSON
* CSV
* VCF

Platforms

* Neo4j Aura
* Amazon AWS
* Google Cloud
* Microsoft Azure
* ZohoCRM
* Twitter
* Facebook
* Discord

Return to [Table of Contents](#table-of-contents).

# Troubleshooting

We're here to help. Contact your Grapho representative for any issues.

For general issues open issues here or add a New Issue

https://github.com/modprods/grapho-user-guide/issues

Return to [Table of Contents](#table-of-contents).

# Change Log

Return to [Table of Contents](#table-of-contents).





