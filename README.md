# grapho-user-guide

![graphobymod-black](img/graphobymod-black.png)

User guide for the Grapho data science + storytelling toolkit

# Table of Contents

- [Introduction](#introduction)
- [Quickstart](#quickstart)
- [Desktop](#desktop)
- [XR](#xr)
- [General Notes](#general-notes)
- [Troubleshooting](#troubleshooting)
- [Platform Specific Notes](#platform-specific-notes)
  - [PCVR](#pcvr)
  - [Oculus](#oculus)
    - [Installation](#installation)
  - [Vive](#vive)
- [Web Services](#web-services)
  - [Dashboard](#dashboard)
  - [Database](#database)
  - [API](#api)
  - [Utilities](#utilities)
  - [Importers](#importers)


# Introduction

Welcome to the user guide for Grapho - a toolkit for data science + storytelling.

In 2024 data science is having a moment with the explosion in generative AI fuelled by deep learning techniques and vast data collections. But the reality is that for all the technical advances, it comes back to humans. How are we collecting data? Why are we collecting it? What are our motivations for using it? How do we communicate? Getting to grips with modern data still requires that ancient skillset we've evolved - storytelling - and how we tell stories is changing. 

This toolkit is for anyone anyone working with graph data. It empowers users to create data stories and draw connections in real-time within immersive virtual worlds. Explore and query graphs using parameters relevant to you. Grapho producitivity tools make taking a deep dive into complex data sets more accessible and engaging. It brings connections to life.  

# Quickstart

* Choose your tool
 * [Grapho XR](#GraphoXR)
 * [Grapho Machine](#GraphoMachine) 
* Choose your platform - desktop, [PCVR](#pcvr) or [Mobile VR](#mobilevr)

# History

Grapho started life as a spatial knowledge graph interface for a VR documentary [A Clever Label](https://acleverlabel.com) released on Steam in 2021 using a Neo4j backend. This was then spun out as a white label tool  [Grapho XR](#GraphoXR) in 2022 for applied data science. Our first customer was [APNIC](https://www.apnic.net/). 

In 2024 a new ISO database language standard [Graph Query Language](https://www.iso.org/standard/76120.html) was published (the first in 37 years since SQL) that defines data structures and basic operations on property graphs largely.

# Roadmap

Grapho is available through Mod's SaaS and consulting service.

[Contact us](https://mod.studio/where/) for more information.

# Grapho XR

Grapho XR is a visualisation tool and a new way to manage and present graph data. It's an interactive experience that feels like Minority Report meets 60 Minutes. Grapho provides flexibility to switch between data sets and between visual themes, ensuring the look is right for your audience. Display and take control of your data. Share knowledge in a hands-on intuitive way. Use it on-set as an interactive in-camera VFX solution. 
 brow ser for manipulating graph data.

Grapho XR builds are available for the following platforms.

Desktop mode (Windows 10 or 11) is provided for backwards compatibility, accessibility, and testing only. We provide web browser tools base not recommend use of 3D visualisation on 2D displays for production use and . Browser For non-XR for Graph XR customers using VR devices. 

See our [XR Roadmap](https://trello.com/b/aIg9JRxM/grapho-roadmap-graphoapp) for more details


## System Requirements

### Windows 10 or 11
 * 16 GB RAM or better
 * Intel Core i7-3930K/AMD FX 8350 equivalent or better
 * NVIDIA GeForce GTX 970, AMD Radeon R9 290 equivalent or better
 * 1 GB available space
 * Oculus

### Oculus

* Oculus Quest 2 / Quest Pro / Quest 3
* Controllers

Hand tracking support on request. 

### HTC

* HTC Vive / Vive Pro / Vive Pro 2 / Vive Focus 3 / Vive Elite XR

### 

* Valve Index



## Dashboard

* Browser
* Dashboard


# Grapho VM

Grapho VMs (aka "Grapho Virtual Machines") are how we design, develop, deploy and operate graph services. 

We custom-build Grapho VMs for customers to use on-premise or on cloud platforms.

We use packer and terragrunt to keep on-premise and cloud hosted virtual machines in sync

Supported virtual machine formats

* Windows WSL2 - Debian
* LXC - Debian
* AWS EC2 - Debian

Contact us for other format requests.

# Mobile VR

## Oculus

## Vive

HTC Vive / Vive Pro / Vive Pro 2


# PCVR

# Web Services

## Dashboard

Integrations

* Neodash
* Streamlit

## Grapho Api

Custom REST API services for Grapho applications and tools

### demo.grapho.app

[Grapho XR](#GraphoXR) uses Grapho API 
* See https://demo.grapho.app/docs

## Tools

### Browser

Supported front-ends
*  Neo4j
 * Browser
 * Bloom
 * Neodash


### Importer

Formats

* JSON
* CSV
* VCF

Integrations

* AWS
* Google
* ZohOCRM
* Twitter
* Facebook
* iOS Contacts  
* Discord

## Database

* Neo4j
 * Community Edition - v4.4, v5
 * Enterprise Edition - v4.4, v5










