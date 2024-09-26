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
| Handle  | Handles are core to Grapho and the starting point for your XR graph journey. As such they are rendered differently from all other nodes. Think of a Grapho Handle as a pointer or a bookmark to a particular place in your graph. Use Handles to create deep links into your graph, to support editorial process (handles play nicely with NEXT relationships for curated paths through your data) and help manage clutter. Handles can be saved to your database or generated on the fly from dynamic query logic. 

### properties

The following properties have specific implementations

| name | type | e.g. | description | 
| -----| ---- | ---- | ----------- |
| name | str | "My node" | used as default label
| colour OR color | str | "#ffffff" | override colour style | 
| voiceover_override | bool | | true | if true, voiceover is allowed to interrupt current voiceover, otherwise this is queued |
| voiceover_url | str | <URL> | plays voiceover when node opened  |
| image_url | str | <URL> | displays image when node opened  |
| subtitles_url | str | <URL>  | displays subtitles when node opened - if voiceover_url available |

## relationship

### properties

| name | type | e.g. | description | 
| -----| ---- | ---- | ----------- |
| colour OR color | string | "#ffffff" | override colour style | 


<!-- # Console Variables -->

# Grapho Machine

## Environment Settings

Grapho Machine tools are typically preset with credentials to your database instances in a .env file.

When building a Grapho Machine from scratch, copy the env.sample file in each component to .env and fill in your real credentials.



