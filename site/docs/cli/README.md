---
sidebar: auto
---

# Command Line

Taplo is available as a cross-platform[^1] command line utility.

## Installation

There are currently no pre-built native binaries available for download.

### Native

You can install Taplo with the following command:

`cargo install taplo-cli`

After which the `taplo` binary should be available.

### Node.js

The tool can be either installed via Yarn:

`yarn global add @taplo/cli`

Or with NPM:

`npm install -g @taplo/cli`

Or simply run it with NPX:

`npx @taplo/cli help`

## Features

- **Linting**
- **Validation (based on JSON schema)** 
- **Formatting**

## Usage

The tool has nice usage and error messages thanks to [clap](https://github.com/clap-rs/clap), to list all the available options, simply run

`taplo help`

An example usage

`taplo lint --schema taplo://cargo@Cargo.toml Cargo.toml`

This command will lint the `Cargo.toml` file with a [built-in schema](/configuration/#built-in-schemas) and report errors.

An example output:
<pre class="cli-output">
<b><span style="color:#d4462d">error</span></b><b>: </b><b>conflicting dotted keys</b><br/>  <b><span style="color:#1c74aa">--> </span></b>Cargo.toml:9:1<br/>  <b><span style="color:#1c74aa"> | </span></b><br/><b><span style="color:#1c74aa">9 </span></b><b><span style="color:#1c74aa"> | </span></b>some.meta.value = 2<br/>  <b><span style="color:#1c74aa"> | </span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b> <b><span style="color:#d4462d">conflicting keys here</span></b><br/>  <b><span style="color:#1c74aa"> | </span></b><br/>  <b><span style="color:#1c74aa">... </span></b>Cargo.toml:10:1<br/>  <b><span style="color:#1c74aa"> | </span></b><br/><b><span style="color:#1c74aa">10</span></b><b><span style="color:#1c74aa"> | </span></b>some.meta = "meta"<br/>  <b><span style="color:#1c74aa"> | </span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b><b><span style="color:#d4462d">^</span></b> <b><span style="color:#d4462d">already defined here</span></b><br/>  <b><span style="color:#1c74aa"> | </span></b><br/>  <b><span style="color:#1c74aa"> - </span></b>entries sharing dotted keys cannot fully define intermediate tables and values<br/>  <b><span style="color:#1c74aa"> - </span></b>make sure that the path consists of equal amount of keys to avoid conflicts<br/><b><span style="color:#d4462d">failure</span></b>: <b>processed 1 document with 1 error </b>
</pre>

## Configuration

The tool supports a configuration file [documented here](/configuration/#configuration-file).

[^1]: It has been tested on Linux only, but in theory it should work on all three major PC operating systems (Linux/iOS/Windows), anywhere where Rust compiles or Node.js is available. If this is not the case, please open an issue on [GitHub](https://github.com/tamasfe/taplo/issues)!
