# grapho-developers-guide

![graphobymod-black](img/graphobymod-black.png)

Developers guide for the Grapho data science + storytelling toolkit

# Table of Contents

- [Grapho XR](#grapho-xr)
- [Grapho Machine](#grapho-machine)

# Grapho XR

See  [Grapho User Guide](README.md) for non-developer documentation.

# Properties

Grapho is designed around the power and simplicity of property graph databases. ie. where both database nodes and relationships (edges) can be assigned key / value properties. 

Your source data does not necessarily need to be stored in a graph database but if it is, you can take immediate advantage of Grapho tool features

The following table sets out the Grapho visualisation schema

## node

### labels

The following Label types have specific implementations

| Label | Description | 
| ----- | ----------- |
| Handle  | Handles are core to Grapho and the starting point for your XR graph journey. As such they are rendered differently from all other nodes. Think of a Grapho Handle as a pointer or a bookmark to a particular place in your graph. Use Handles to create deep links into your graph, to support editorial process (handles play nicely with NEXT relationships for curated paths through your data) and help manage clutter. Handles can be saved to your database or generated on the fly from dynamic query logic. See [Grapho XR UI documentation](https://docs.grapho.app/#user-interface)

### properties

The following properties have specific implementations

| name               | type  | e.g.      | description                                                                                                  |
|--------------------|-------|-----------|--------------------------------------------------------------------------------------------------------------|
| name               | str   | "My node" | used as default label                                                                                         |
| colour OR color    | str   | "#ffffff" | override colour style                                                                                        |
| voiceover_override | bool  | true      | if true, voiceover is allowed to interrupt current voiceover, otherwise this is queued                        |
| voiceover_url      | str   | https://d1pxeqjdb63hyy.cloudfront.net/media/media/test-ux.ogg | plays voiceover when node opened. Supports WAV, MP3, and OGG formats  |
| image_url          | str   | https://d1pxeqjdb63hyy.cloudfront.net/media/images/node_end-to-end-testing.original.png | displays image when node opened. Supports JPG, PNG  |
| subtitles_url      | str   | https://mod.studio/documents/64/test-ux.vtt | displays subtitles when node opened - if voiceover_url available. Supports VTT and SRT formats |


## relationship

### properties

| name | type | e.g. | description | 
| -----| ---- | ---- | ----------- |
| colour OR color | string | "#ffffff" | overrides colour style defined in the app | 


<!-- # Console Variables -->

# Grapho Machine

## Environment Settings

Grapho Machine tools are typically preset with credentials to your database instances in a .env file.

When building a Grapho Machine from scratch, copy the env.sample file in each component to .env and fill in your real credentials.

## grapho-server

grapho-server is a lightweight reference API server for the [GraphoXR](README.md#grapho-xr) spatial browser.

Source code and documentation is available at [https://github.com/modprods/grapho-server](https://github.com/modprods/grapho-server)

Features

* OpenAPI compliant documentation
* REST API endpoints for graph database queries
    * all - load all editorially curated paths (via their "handles") 
    * game - load a complete graph for offline use
* Mux database queries (e.g. CYPHER, SQL) with local config
* Support for running on local desktop, on-premise hosting and cloud platforms

Handles

"Handles" are the mechanism by which editorially curated paths through your graph data are served to Grapho clients like  [GraphoXR](README.md#grapho-xr). 

Use Handles to design, curate and manage your graph data experiences.

Handles are simply nodes with the label "Handle". They have special significence and are [rendered differently](README.md#handle) to other [nodes](README.md#node).

Use Handles to 
* The /all REST API method returns all Handles in the database
* By default, selecting a Grapho database in Grapho XR will spawn all Handles as [Tron-like disks](README.md#handle).
* [Opening a Handle](README.md#open-graph) in a Grapho client will reveal all nodes linked to this Handle. 
* Handles can be configured to serve any style of data
* By default Handles are configured to
 * Return the path of all nodes connected to me via the relationship NEXT
 * Return all nodes that are linked to this path by no more than 1 node (i.e. distance = 1) 

### grapho-server quickstart

To start exploring your own data, try creating a Handle linking to an existing node in your database.

Set up your own Grapho XR experience from scratch, all you need is a recent Meta Quest headset and the following free resources.

1) Run Neo4j Desktop

* On your desktop or laptop
    * Download and install Neo4j Desktop
    * Create and run a new Neo4j database
    * Open the database (with Browser)
    * Click Guides | :guide movie-graph | Next
    * Click the PLAY icon in the code block
    * Note the new  "Node labels" and "Relationship types" that appear under Database Information (left column)
    * Copy the following CYPHER query into the Browser prompt>

```
// Merge first handle
MERGE (n:Handle {label:'Enter the Matrix'})
SET n.name = n.label
WITH n
MATCH (o:Movie {title:a'The Matrix'})
MERGE (n)-[:NEXT]->(o)
RETURN n, o
```
    * Click the RUN icon (blue arrow to the right of prompt)

2) Run grapho-server container in Docker Desktop

* On your desktop or laptop
    * Download and install Docker Desktop
    * Run a Docker container of grapho-server (see separate instructions)
    * Connect to your running container and update the .env configuration file to match your Neo4j database and LAN IP settings

```
# Neo4J FQHN
NEO4J_HOST = "host.docker.internal"
NEO4J_USER = "neo4j"
NEO4J_PASSWORD = "<INSERT PASSWORD>"
NEO4J_PORT_HTTP = 7474
NEO4J_PORT_BOLT = 7687
# uncomment next line to ignore dynamic db parameter and hardcode this
#NEO4J_DATABASE = "neo4j"
PUBLIC_URL = "http://<YOUR SERVER LAN IP>:5042"
QUERY_LIMIT = 300
INCLUDE_FIXED_QUERIES = False
```

    * Run the server

```
pipenv run python api.py
```
    * Confirm the server is running locally by checking PUBLIC_URL in your browser
```
i.e.
http://<YOUR SERVER LAN IP>:5042
```

3) Run Grapho XR Demo on Meta Quest HMD

* Open Browser
* Confirm you can access grapho-server URL (you may need to give permission for "unsafe" URL)

```
i.e.
http://<YOUR SERVER LAN IP>:5042
```
* Copy URL
* Install and run the free [Grapho XR Demo](README.md#grapho-xr-demo) from Meta Store
* Press SETTINGS button (three vertical lines) on left controller
* Click "Paste" button under API_ROOT_URL
* Select your database name under Database
* Press SETTINGS button to close panel
* <the "Enter the Matrix" handle should spawn>
* Use GRAB button to grab handle and flip it over to open

You now have your own Grapho service equivalent to [demo.grapho.app](README.md#demographoapp) 

See [Properties](#properties) for how to prepare your graph for use in Grapho. 


